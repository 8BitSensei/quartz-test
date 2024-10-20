---
date: 2023-03-16
draft: false
tags:
  - CompSci
  - DesignPattern
  - creational-pattern
---
*Allows us to ensure that a class only ever has a single instance with a global access point.*

There are instances where we want to ensure that only one instance of a class exists at a time, for example controlling access to a shared resource, e.g. a database or a file. We would also like that instance to be accessible from anywhere, but protected from being overwritten by whomever is accessing it.

The singleton pattern solves these problems, this is probably *the* simplest pattern, only consisting of at least these two steps:
- A private default constructor to preventing other objects calling `new` on the class.
- A static creation method that acts as our constructor which saves the internal object to a local property, all further calls to this method just returns that property.

#### Implementation

```go:singleton.go
package main  
  
import (  
   "fmt"  
   "sync")  
  
var lock = &sync.Mutex{}  
  
type singleton struct{}  
  
var singleInstance *singleton  
  
func getInstance() *singleton {  
   if singleInstance == nil {  
      lock.Lock()  
      defer lock.Unlock()  
      if singleInstance == nil {  
         fmt.Println("Creating singleton instance")  
         singleInstance = &singleton{}  
      } else {  
         fmt.Println("Singleton instance already exists")  
      }  
   } else {  
      fmt.Println("Singleton instance already exists")  
   }  
  
   return singleInstance  
}
```

```go:main.go
package main  
  
import "fmt"  
  
func main() {  
   for i := 0; i < 30; i++ {  
      go getInstance()  
   }  
  
   fmt.Scanln()  
}
```


---
# References
