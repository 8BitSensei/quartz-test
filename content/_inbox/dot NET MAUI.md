2023-03-05
#programming 

Multi-Platform App UI (MAUI), is a [[dot NET|.NET]] cross-platform framework for creating native mobile and desktop apps using [[C Sharp (Language)|C#]] and [[XAML]].

Unifies Android, iOS, and Windows APIs into a single API .

.NET 6 or greater provides specific frameworks for platforms. For Android, iOS, and macOS the runtime is [[Mono]], on Windows the runtime is [[Common Language Runtime|CLR]].

MAUI provides a common framework for Android, iOS, macOS, and Windows, this way we don't have to maintain separate codebases.

## Architecture

> One of the most important decisions when creating a .NET MAUI enterprise app is whether to place business logic in code-behind files, or whether to create a clean separation of concerns between the user interface controls and their logic, in order to make the app more maintainable and testable.

> Choosing between platform provided eventing and loosely coupled message-based communication between components that are inconvenient to link by object and type references

> The [[Model-view-viewmodel (MVVM) pattern]] helps cleanly separate an application’s business and presentation logic from its user interface (UI). Maintaining a clean separation between application logic and the UI helps address numerous development issues and makes an application easier to test, maintain, and evolve. It can also significantly improve code re-use opportunities and allows developers and UI designers to collaborate more easily when developing their respective parts of an app.

#### Project structure

**Resources\\**
This folder has all of our fonts, images, and raw assets for the entire project.

**Platforms\\**
Handles all of the project set-up for different platforms, a lot of boiler plate, but if we need platform specific stuff it would go here.

#### Shell

The base of the application, there by default. Enables URI based navigation, allows flyout items, menus, tabs etc.

#### Page

Root of everything on the screen, pages exists inside of a shell. Each page is a `ContentPage` which holds a single visual element e.g. `Control`, `Layout` (`Layout`s can have multiple elements inside of them), so we usually have a `ContentPage` with a `Layout` element, which then holds multiple elements for what ever we need.

#### Element behaviours

Each element has a bunch of behaviours, or events. 

#### Connecting view models to views

View models are connected to views by using the BindingContext and the data-binding capabilities of .NET MAUI. 

**View first composition**
The app is conceptually composed of views that connect to the view models they depend on. Makes it easy to construct loosely coupled apps because the *view models have no dependence on the views*. Structure is also easy to follow visually rather than tracking code execution.

> view first construction aligns with the Microsoft Maui’s navigation system that’s responsible for constructing pages when navigation occurs, which makes a view model first composition complex and misaligned with the platform

**View model first composition**
The app is conceptually composed of view models, with a service responsible for locating the view for a view model. The view creation can be abstracted awa, allowing us to focus on the non-UI logic. It also allows view models to be created by other view models, however this approach is often more complex and hard to understand.

The view's principle dependency should be to a property in the data source. Don't reference view types from view models.

#### Declarative view models

A view should declaratively instantiate its corresponding view model in XAML. When the view is constructed the corresponding view model object will also be constructed:

``` XAML
<ContentPage xmlns:local="clr-namespace:eShop">
	<ContentPage.BindingContext>
		<local:LoginViewModel />
	</ContentPage.BindingContext>
	...
</ContentPage>
```

This will create an instance of the `LoginViewModel` when the `ContentPage` is created and set as the view's `BindingContext`.

This requires a parameterless ctor in the view model.

#### Creating a view model programmatically

A view can have code in the code-behind file. We can use this to bind the view model to the `BindingContext` in the ctor:

```C#
public LoginView()
{
	InitializeComponent();
	BindingContext = new LoginViewModel(navigationService);
}
```

This is very simple, this allows us to have a ctor on our view model  with parameters, meaning we would need to implement [[Dependency Injection]].

#### Updating views in response to changes in the view model or model

*All view model and model classes that are accessible to a view should implement the INotifyPropertyChanged interface.* This interface in a view model or model class allows the class to provide change notifications to data-bound controls in the view.

There are some requirements apps should meet to correctly use property change notifications:

- Raise a `PropertyChanged` event if a public property's value changes
- Do not assume that raising the `PropertyChanged` event can be ignored
- Raise a `PropertyChanged` event for any calculated properties used by other properties in the view model or model
- Raise a `PropertyChanged` event at the end of the method that makes a property change, or when the object is in a safe state
- Never raise a `PropertyChanged` event if the property does not change, so, compare the new and old values before hand to test it has changed
- Never raise a `PropertyChanged` event during a view model's constructor if you are initialising a property
- Never raise more than one `PropertyChanged` event with the same property within a single synchronous public method of a class



## Tools

##### [CommunityToolkit/Maui](https://github.com/CommunityToolkit/Maui)

Community run toolkit to provide a collection of elements that developers tend to replicate across multiple apps.

Add it to the project by adding it to the `MauiAppBuilder` with the extension `.UseMauiCommunityToolkit()`

###### [mono/SkiaSharp](https://github.com/mono/SkiaSharp)

Cross-platform 2D graphics API for .NET based on the Skia Graphics Library. Can be used across mobile, server, and desktop models to render images (this can be used to make a PDF viewer).




---
# References

https://learn.microsoft.com/en-us/dotnet/maui/what-is-maui?view=net-maui-7.0