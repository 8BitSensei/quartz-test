2023-08-09
Tags: #containerisation 

- Build a dockerfile based on a windows image that has powershell, in my most recent test I used `stefanscherer/openssh-windows:latest`, this is based off of `mcr.microsoft.com/windows/servercore:ltsc2019-amd64` which works, so does `ltsc2022-amd64`, so does `ltsc2022` . This does not work in the nanoserver even after installing powershell, the remote tools setup fails, and if you manually add the debugger, nothing happens.
- Expose the port you will use to connect to the debugger. There are many ports that the debugger might be using, I need to test which ones are needed and which ones aren't.
- Run the image exposing the port `-p 4020:4020/tcp` and inside it follow the next steps (it seems to work without doing this!)
- Download remote tools for VS 2022:
```powershell
Invoke-WebRequest -OutFile c:\rtools_setup_x64.exe -Uri https://download.visualstudio.microsoft.com/download/pr/89f2306b-0dcc-47af-b67f-47011cb5ee43/57daedc11766b189092e93222d3fc39bf27b38cfd6a2b7ac08902ddd032dc6c8/VS_RemoteTools.exe
```

- Run the install tools (/quiet is required, I think that it tries to do UI stuff without it)
``` powerhsell
.\rtools_setup_x64.exe /install /quiet
```

- Navigate to the debugger at `C:\Program Files\Microsoft Visual Studio 17.0\Common7\IDE\Remote Debugger\x64`
- Run the debugger with (default port should be 4026 for vs 2022)
``` powershell
.\msvsmon /noauth /anyuser /silent 
```
- If it has worked you should see the port being listened to in `netstat -ab`
- In VS 2022 open the attach to process menu with `Ctrl + Alt + p`
- Using connection type `Remote (no authentication)` connect to `<hostname>`


### Automation proposal

Add a PORTS command to mythctl application files so that we can specify what container ports to open, this will allows us to open port 4026

Get the debugger into the streamer image and then specify it needs to be copied onto the streamer container 

 Create powershell script that starts msvsmon and then does all the other pre launch steps

Pass this script to the prelaunch argument on the injector, it currently can only take a single exe so multiple steps have to be in a single script

The session service will open up the debugging port and pass back the mapped port to the client, do we need to make a change to any data models or the Gateway to do this?

At this point we need input from the streamer, with new information being passed to the client they need a way to surface that for the developer

They will also need to build debug specific versions of the streamer image that turns msvsmon on, we cannot have that present in production

Upload Mythctl and then upload streamer release pipeline at https://polystream.visualstudio.com/Github/_releaseDefinition?definitionId=39&_a=definition-tasks&environmentId=46

We can download the remote tools in the above script and copy it in

The biggest issue with this is that we're limited to one version of the debugger