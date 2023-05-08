# @ObservedObject vs @EnvironmentObject
The roles of the two are very similar to each other. You can use one of them when you need to subscribe to a state object variable in a SwiftUI view.
<br>
The only difference between them is the way how they carry the object into subviews in terms of hierarchy.

### ☑️ @ObservedObject:
You need to pass the object as an initializing parameter through all the parent views after views till the last one where you want to subscribe the object in.
<br>
Imagine three views A, B, and C where C is one of the subviews of B, and B is one of the subviews of A. Then all A, B, and C will have to have @ObservedObject for the identical object even if A or B doesn't need it.

![teamwork](https://user-images.githubusercontent.com/123972077/236865738-78d6a33e-066a-4ef8-a214-2414cf26aa89.gif)

### ☑️ @EnvironmentObject:
Unlike to above, you don't need to pass the object through the parent views. You can use it anywhere you need regardless of hierarchy.

As such, @EnvironmentObject is much more useful than @ObservedObject in any case.
<br>
But why do you still need @ObservedObject?

References:
<br>
https://stackoverflow.com/questions/63343819/what-is-the-difference-between-environmentobject-and-observedobject
<br>
https://swiftwithmajid.com/2020/07/02/the-difference-between-stateobject-environmentobject-and-observedobject-in-swiftui/
<br>
https://www.hackingwithswift.com/quick-start/swiftui/whats-the-difference-between-observedobject-state-and-environmentobject
