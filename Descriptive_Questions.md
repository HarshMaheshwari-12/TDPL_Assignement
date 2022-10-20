Q1. Can we nest the Scaffold widget? Why or Why not?
Ans. No we should not use the nested Scaffold because the Scaffold was designed to be the single top level container for a MaterialApp and it's typically not necessary to nest scaffolds.Although in some scenarios where embedded flutetr content is used there we can use the nested Scaffold Widget.For the tabbed or nested navigations we should use the single Scaffoled widget.So as a conclusion we should use only one Scaffold with widgets such as TabController or IndexedStack to navigate the content inside the body of a single screen.

Q2. How to reduce the rebuilding of the widget?
Ans2. There are many ways we can reduce the rebuilding of the widgets.
1. We can use the proper state management techniques like Provider, Getx or Bloc to stop the rebuilding of  widgets.
2.We can create a child Stateful class to create a UI using any widget.
3. We should not use the set state many times in a widget because it reloads the whole Widget.
4. We should make our build method pure so that the child widgets should be build less in the widget tree.
5. When the instance of a widget stays the same. Flutter purposefully won't rebuild children. It implies that you can cache parts of your widget tree to prevent unnecessary rebuilds.


Q3. How can I access platform(iOS or Android) specific code from Flutter?
Ans3. We can use the Method Channel package to work on the platform specific code. We can also use the pigeon package available i.e use to make the communication between the ios and android side platform and it's type-safe, easier and faster.

Q4. What is BuildContext? What is its importance?
Ans 4. BuildContext is the locator or path use in the widget tree that gives the location of the widget defined in the widget tree.It serves as the bridge for changes in the widget world and updates in the rendering world.When called, each widget you create has a context that becomes the widget's parent. Build Context is passed at many places like in the theme class refrence , In calling of the other classes also in any application.

Importance of Build Context- There are many reasons because of which Build Context is important. it's used to interact with the render objects the context makes all of these interactions possible.Whether you are using a state management solution like flutter_bloc or provider, every reputable state management library uses BuildContext under the hood to efficiently propagate information down the tree.In the core of this Build context Inherited widgts are used which is working as an internal class of the build Context. The method name is dependOnInheritedWidgetOfExactType which is a crucial method and it's responsibility is to find the nearest instance in the widget tree.