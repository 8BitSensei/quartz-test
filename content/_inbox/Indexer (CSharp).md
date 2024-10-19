2023-07-04
Tags: #programming #csharp 

> Indexers allow instances of a class or struct to be indexed just like arrays. The indexed value can be set or retrieved without explicitly specifying a type or instance member. Indexers resemble [properties](https://learn.microsoft.com/en-us/dotnet/csharp/programming-guide/classes-and-structs/properties) except that their accessors take parameters.

```C#
class SampleCollection<T> 
{
	private T[] arr = new T[100]; 
	// Define the indexer to allow client code to use [] notation. 
	public T this[int i] 
	{ 
		get { return arr[i]; }
		set { arr[i] = value; }
	}
} 

class Program 
{ 
	static void Main() 
	{ 
		var stringCollection = new SampleCollection<string>();
		stringCollection[0] = "Hello, World";
		Console.WriteLine(stringCollection[0]);
	}
}
```

---
# References

https://learn.microsoft.com/en-us/dotnet/csharp/programming-guide/indexers/