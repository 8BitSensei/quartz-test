2023-03-02
#programming #go-lang

Very simple go-lang based build tool. Once installed, all you need to do is describe your build tasks in a YAML file called `Taskfile.yml`, you can then call your tasks from the terminal with the `task` command.

```YAML
version: '3'  
  
tasks:  
	hello:  
		cmds:  
		- echo 'Hello World from Task!'  
		silent: true
```

The above can be run with the command:
`task hello`

---
# References

https://taskfile.dev/