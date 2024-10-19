2024-02-11
Tags: #ReactiveUI #AvaloniaUI #dotNet #csharp 

##### Principle of Revealed Functionality
Features and functions only become available (or visible) once they are valid. For example, I submit button on a form may be greyed out until form input is considered valid. This ensures that a user is properly guided through the UI.

##### ReactiveCommand - Basic
`ReactiveCommand` is a type which allows us to create a delegate method for it to hold e.g:

```c#
public ReactiveCommand<TParam, TResult> SubmitCommand { get; }

SubmitCommand = ReactiveCommand.Create(() => {
	Debug.WriteLine("Hello World!");
});
```

Any UI element bound to `SubmitCommand` such as a Button will call the delegate method supplied in the create method.

`TParam` and `TResult` allow us to define a required input and output parameter, e.g:

```c#
public ReactiveCommand<string, string> SubmitCommand { get; }

SubmitCommand = ReactiveCommand.Create((string x) => {
	return $"Hello {x}!";
});
```

##### ReactiveCommand - Async
This is the recommended method! You should bever be doing ViewModel logic synchronously with the UI thread! To do this we can use `CreateFromTask()` instead of `Create()`, this will execute a C# TPL Task, allowing us to use async/await operators. We can also use `CreateFromObservable()` which is apparently asynchronous, but I don't understand observables yet!

```C#
CancelCommand = ReactiveCommand.CreateFromTask<string, string>(CancelCommandImpl);

public Task<string> CancelCommandImpl(string x)
{
    return Task.FromResult(x);
}
```

##### ReactiveCommand - Checking whether we can execute
As mentioned before one of our principle sis that features and functions only become available (or visible) once they are valid, this can't easily be done with vanilla method binding, that's why ReactiveCommands are so great. We can pass a second parameter, an `IObservable<bool>` which will constantly check a Boolean condition, and if true enable our method, and if false prevent it's execution. This means we can check if the inputted form data is valid, and if it is not, our button will appear greyed out!

``` C#
IObservable<bool> isValidObservable = this.WhenAnyValue(
    x => x.Description,
    x => !string.IsNullOrWhiteSpace(x));

OkCommand = ReactiveCommand.CreateFromTask(() => Task.FromResult(new ToDoItem { Description = Description }), isValidObservable);
```

---
# References

https://docs.avaloniaui.net/docs/concepts/reactiveui/reactive-command