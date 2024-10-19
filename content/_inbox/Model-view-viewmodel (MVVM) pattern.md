2023-03-07
#programming #DesignPattern 


Three core components in the pattern: the model, the view, and the view model. Each has a distinct purpose. At a high level, the view 'knows about' the view model, and the view model 'knows about' the model, but no more. The view model isolates the view from the model and allows them to evolve independently.

#### View

The view defines the structure, layout, and appearance of what the user sees on the screen. Each view should be defined in XAML with limited code that does not contain any of the business logic. It may however contain UI logic that controls visual behaviour, such as animations.

In [[dot NET MAUI]] a view is usually derived from either the `Page` or `ContentView` class. But, a view can also be represented by a data template which specifies the UI elements to represent. A data template has no code behind and is designed to bind a specific view model type.

> Ensure that the view models are responsible for defining logical state changes that affect some aspects of the view’s display, such as whether a command is available, or an indication that an operation is pending. Therefore, enable and disable UI elements by binding to view model properties, rather than enabling and disabling them in code-behind

#### ViewModel

The view model implements properties and commands to which the view model can *data bind* to, and notifies the view of any state changes through *change notification events*. The properties and commands of the ViewModel define the functionality of a View, but the View defines how that is presented to the  user.

#### Model

Model classes are non-visual classes that encapsulate the app's data. in a way representing the app's domain model, which usually includes the data models along with business and validation logic. Model classes are usually used in conjunction with services or repositories that encapsulate data accessing.

---
# References
