2024-04-15
Tags: #programming #go-lang 

go routines
channels
select

#### Go Routine
In Go a routine is a thread of execution.

Normally functions run synchronously, so that if I call `a()` then `b()`, `a()` will run and then `b()` will run. But we can use the `go` command when calling a method, to fork a new process off that will run asynchronously:

``` Go
func main() {
	go a()
	go b()
}
```

If we fire and forget these go routines we will probably never see the results as the main routine will immediately finish, we are responsible for joining the results back to the main thread.

Go uses a Fork and Join model.

#### Channels
Channels are fundamentally queues that multiple routines can read, this allows them to communicate with each other.

We can write to a channel with the `<-` operator where we:
``` go
myChannel <- "data"
```

And to read off the channel we do the same from the channel to a variable
``` go
msg := <- myChannel
```

Note that this is also a blocking call, so the above will wait until a message has been added to the channel. If no message will ever be added, this creates a deadlock error and our code won't build.

#### Select
Select is basically a switch statement, but in Go it allows us to wait on multiple channels, and then continue when we receive at least one channel. If we receive two at the same time it picks one at random;

``` go
select {  
case msgFromChannel := <-myChannel:  
   fmt.Println(msgFromChannel)  
case msgFromAnotherChannel := <-anotherChannel:  
   fmt.Println(msgFromAnotherChannel)  
}
```

#### For-Select loop



---
# References

https://rogerwelin.github.io/golang/go/concurrency/2018/09/04/golang-concurrency-fundamentals.html

https://www.youtube.com/watch?v=qyM8Pi1KiiM&ab_channel=KantanCoding