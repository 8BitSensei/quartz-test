---
date: 2023-03-16
draft: false
tags:
  - CompSci
  - DesignPattern
  - creational-pattern
---
Allows us to step by step create different complex objects, using the same construction code.

This pattern is used in scenarios where we may want to produce many complex variants of a single type of object, for example, we may begin with an object `House`, but later need a house with more floors, a garage, a garden, a pool, detached, semi-detached etc. Rather than creating many subclasses of the object `House`, or creating a constructor with a monstrous number of options, we can implement a Builder.

The pattern demands that we take the object construction code out of its own class and move it to separate objects called *builders*. We can produce a `HouseBuilder` that implements each step of the object construction, for example:
- `buildWalls()`
- `buildDoors()`
- `buildWindows()`
- `buildRoof()`
- `buildPool()`

With this builder, we now only need to call the construction steps we need, and can hide away the construction code from the client. We can extend this further and provide multiple builders if some steps require different implementations, e.g. `GlassHousebuilder`, `LogHouseBuilder`, or `CastleHouseBuilder`. We can provide these all with a common interface `IHouseBuilder` so that the client code can handle them all.

This pattern allows us to go even further and define a `Director` class, this has an internal `Builder` property and methods to change that internal `Builder`, and direct that `Builder` to produce an object following a pre-defined routine. This means hides the details of the construction routine away from the client code.

#### Implementation

```go:iBuilder.go
package main  
  
type IBuilder interface {  
   setWindowType()  
   setDoorType()  
   setNumFloor()  
   getHouse() House  
}  
  
func getBuilder(builderType string) IBuilder {  
   if builderType == "normal" {  
      return newNormalBuilder()  
   }  
  
   if builderType == "igloo" {  
      return newIglooBuilder()  
   }  
   return nil  
}
```

```go:house.go
package main  
  
type House struct {  
   windowType string  
   doorType   string  
   floor      int  
}
```

```go:iglooBuilder.go
package main  
  
type IglooBuilder struct {  
   windowType string  
   doorType   string  
   floor      int  
}  
  
func newIglooBuilder() *IglooBuilder {  
   return &IglooBuilder{}  
}  
  
func (b *IglooBuilder) setWindowType() {  
   b.windowType = "Ice"  
}  
  
func (b *IglooBuilder) setDoorType() {  
   b.doorType = "Ice"  
}  
  
func (b *IglooBuilder) setNumFloor() {  
   b.floor = 1  
}  
  
func (b *IglooBuilder) getHouse() House {  
   return House{  
      doorType:   b.doorType,  
      windowType: b.windowType,  
      floor:      b.floor,  
   }  
}
```


```go:normalBuilder.go
package main  
  
type NormalBuilder struct {  
   windowType string  
   doorType   string  
   floor      int  
}  
  
func newNormalBuilder() *NormalBuilder {  
   return &NormalBuilder{}  
}  
  
func (b *NormalBuilder) setWindowType() {  
   b.windowType = "Wooden"  
}  
  
func (b *NormalBuilder) setDoorType() {  
   b.doorType = "Wooden"  
}  
  
func (b *NormalBuilder) setNumFloor() {  
   b.floor = 2  
}  
  
func (b *NormalBuilder) getHouse() House {  
   return House{  
      doorType:   b.doorType,  
      windowType: b.windowType,  
      floor:      b.floor,  
   }  
}
```

```go:director.go
package main  
  
type Director struct {  
   builder IBuilder  
}  
  
func newDirector(b IBuilder) *Director {  
   return &Director{  
      builder: b,  
   }  
}  
  
func (d *Director) setBuilder(b IBuilder) {  
   d.builder = b  
}  
  
func (d *Director) buildHouse() House {  
   d.builder.setDoorType()  
   d.builder.setWindowType()  
   d.builder.setNumFloor()  
   return d.builder.getHouse()  
}
```

```go:main.go
package main  
  
import (  
   "fmt"  
)  
  
func main() {  
   normalBuilder := getBuilder("normal")  
   iglooBuilder := getBuilder("igloo")  
  
   director := newDirector(normalBuilder)  
   normalHouse := director.buildHouse()  
  
   fmt.Printf("Normal House Door Type: %s\n", normalHouse.doorType)  
   fmt.Printf("Normal House Window Type: %s\n", normalHouse.windowType)  
   fmt.Printf("Normal House Num Floor: %d\n", normalHouse.floor)  
  
   director.setBuilder(iglooBuilder)  
   iglooHouse := director.buildHouse()  
  
   fmt.Printf("\nIgloo House Door Type: %s\n", iglooHouse.doorType)  
   fmt.Printf("Igloo House Window Type: %s\n", iglooHouse.windowType)  
   fmt.Printf("Igloo House Num Floor: %d\n", iglooHouse.floor)  
}
```

---
# References

https://refactoring.guru/design-patterns/builder