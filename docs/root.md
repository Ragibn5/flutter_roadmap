### Index

1. **Introduction to Programming & Dart**
2. **Setup development environment**
3. **Basic Flutter Development**
4. **Intermediate Flutter Development**
5. **Advanced Flutter Development**
6. **Performance Optimization**
7. **Testing and Debugging**
8. **Architectural Principles**
9. **Deployment and Maintenance**

---

#### 1. Introduction to Programming & Dart

- **Basic Programming Concepts**
    - Variables, Data Types, and Operators
    - Control Flow (if, else, switch)
    - Loops (for, while, do-while)
    - Functions and Methods
    - Basic Data Structures (Lists, Sets, Maps)

- **Object-Oriented Programming (OOP)**
    - Classes and Objects
    - Inheritance
    - Polymorphism
    - Encapsulation
    - Abstraction

- **SOLID Principles**
    - Single Responsibility Principle
    - Open/Closed Principle
    - Liskov Substitution Principle
    - Interface Segregation Principle
    - Dependency Inversion Principle

**Books & Resources:**

- "Dart: Up and Running" by Kathy Walrath and Seth Ladd (For basic dart)

---

#### 2. Setup development environment

- **Setup Android Studio**
    - If you are running a MackBook, you should have XCode installed.
    - Download and install android studio with default configuration.
    - After installation, install the following
        - FVM
        - Plugins:
            - Dart
            - Flutter
            - Flutter Intl
            - BLOC (Will be used later)
            - Dart data Class (Optional)
    - Create and open your first flutter project. It may take a long time for the first project
      to complete initialization as it will download many platform specific components and other
      things. This is one time and won't happen in subsequent projects.
    - After project initialization finishes, go to terminal (integrated in the IDE) and run the
      following commands to select the desired flutter and dart runtime. Currently the 3.16.5 is a
      good choice. You'll also need to set some paths in IDE settings.
        - `fvm use 3.16.5` (To install version 3.10.6).
        - To use different version, first run `fvm releases` to see the list of all available
          versions. Then run the same command with the desired version name. For example to use
          version 3.10.6, run `fvm use 3.10.6`.
        - It may take a long time if ypu are running `fvm use <version>` on a version that is not
          available locally. To see the locally available versions, run `fvm list`.
        - Afterwards, go to Android studio Settings >> Languages & Frameworks >> Flutter, and set
          the "Flutter sdk path" to *<FVM-Installation-Path>/versions/<Version>*. For example, if we
          followed the previous guide, the path will be */Users/ragib/fvm/versions/3.16.5*. This
          will vary on your computer.
    - Update the XCode/related components if asked.
    - Now you have a proper setup for flutter development. You may want to restart the IDE after
      this just to make sure everything is working.

#### 3. Basic Flutter Development

- **Introduction to Flutter**
    - [Flutter Overview](https://flutter.dev)
    - [Understanding Flutter Architecture](https://docs.flutter.dev/resources/architectural-overview)

- **Create first screen**
    - AppBar
    - Scaffold
    - MaterialApp
      If you have created a flutter project, these should already be pre-filled for you.
    - But do have a look at what they are and why they are used.

- **Building layouts**
    - Flutter widgets (StatelessWidget, StatefulWidget, StatelessWidget vs StatefulWidget).
    - Basic built-in widgets
        - Text
        - Icon
        - Image
        - Center
        - SizedBox
        - Container
        - Placeholder
    - Flexbox layouts
        - Row
        - Column
        - Expanded
        - Flexible etc.
    - Stack and related widgets
        - Positioned and all its variants
            - Positioned
            - Positioned.filled etc.
    - Scrollable group views
        - SingleChildScrollview
        - ListView
        - GridView
    - There are lots of other widgets to explore later...

- **Handling User Input**
    - Buttons
        - TextButton
        - RaisedButton
        - FlatButton
        - IconButton
    - Custom user event detection using
        - GestureDetector (Preferred at beginning)
        - Inkwell (Preferred later when used to with theming and other UI concepts)

    - Text Fields
        - TextField
        - TextFormField

- **Notes**
    - Try to know what, when and why to use a particular widget.
    - Explore about every parameters of the above components and know when and why to use them.
      First start with basics and then plat with each parameters and see the behaviour to know them
      better.

- **Homework**
    1. Create a custom button widget using the above widgets & components.
        - Text should be in center with user defined text content (what to show in button, e.g.
          Close, Cancel, Next etc) font size, color, line count, overflow etc.
        - There will be two same sized (20) icons on left and right side of the text, provided by
          user (IconData). They should have a user defined color.
        - Icons and the text should be aligned center-horizontally with a certain gap in both sides
          of the text.
        - Text should expand as needed and should show a overflow character (...) at end if there is
          not enough room for the text.
          icons in left(user defined) and right(may be an arrow icon)
        - Should do something (may be print something in console, or show a snack).
    2. Create a simple List cell having user's circular image at left (you may use new properties of
       previously described widgets or use new widgets), and user's name at right. They should be
       aligned center-horizontally as well. Afterwards, use the newly created widget to populate
       ListView widget. Explore the performance for a large number of list cells in case of all the
       constructors of the ListView widget.
    3. Same as 2, but use a gridview. This time only see the user's circular image as cell.

    - **Proper Architecture and Best Practices:**
        - **OOP Principles:** Use proper OOP principles.
        - **SOLID Principles:** Create small, single-responsibility widgets. You may split the
          widgets into multiple pieces. You may either split into methods returning Widget class's
          instance, or make completely new widget class from them. Explore a bit to see which way is
          better.

---

#### 4. Intermediate Flutter Development

- **State Management**
    - Stateful widget & changing UI in realtime
    - InheritedWidget

- **Working with assets**
    - Updating pubspec.yaml to include assets in the project
    - Fonts
    - Images
    - Docs and other file types

- **Themed widgets**
    - Theme
    - Material widgets
    - Cupertino widgets
    - Using theme components using Theme.of(context)

- **Navigation & Routing**
    - Navigation between screens with built-in navigator.
    - Named routes & navigation using named routes.

- **Networking**
    - HTTP Requests
    - JSON Parsing
    - Communicating with apis using http package

- **Persistence**
    - Files.
    - Shared Preferences.
    - Understand structure of app-specific file system in each platform (iOS and Android for now).

---

#### 5. Advanced Flutter Development

- **(A)Synchronous programming**
    - General theories
        - Concurrency
        - Parallelism
        - Threads
        - Processes
        - Synchronous and Asynchronous programming
          A good summery on all about these can be
          found [here] (https://medium.com/swift-india/concurrency-parallelism-threads-processes-async-and-sync-related-39fd951bc61d).
        - [Reactive programming basics](https://www.baeldung.com/cs/reactive-programming#:~:text=Reactive%20programming%20is%20a%20declarative,or%20reactive%20systems%20in%20general.)

- **Async & reactive programming in dart**
    - **async**, **await**, **Future**.
    - **Streams** and its creation.
    - [RxDart](https://pub.dev/packages/rxdart)
    - FutureBuilder (Avoid whenever possible, use **StreamBuilder**)

- **Advanced State Management**
    - StreamBuilder
    - Bloc Pattern (**Used in our organization**)
    - Redux (Good to know)
    - Riverpod (Good to know)

- **Responsive Design**
    - MediaQuery
    - LayoutBuilder
    - Adaptive Widgets

- **Custom Widgets**
    - Creating custom widgets
    - Composition vs Inheritance in case of custom widgets building.
    - Adhering to OOP and SOLID principals while building custom widgets.

- **Design Principles**
    - Material Design
    - Cupertino Design
    - Custom Themes

- **Theming**
    - **Theme** widget.
    - Dynamic theme switching.

- **Animations**
    - Implicit Animations
    - Explicit Animations
    - Animation Controllers
    - Tween Animations
    - Curved Animations

- **Complex Widgets**
    - CustomPainter
    - CustomClipper

- **Localization**
    - [Adding localization in flutter](https://localizely.com/blog/flutter-localization-step-by-step)
    - **Localization** widget.
    - Dynamic localization switching.

---

#### 6. Performance Optimization

- **Performance Tools**
    - Flutter DevTools
    - Flutter Performance Overlay

- **Flutter internals**
    - Flutter inspector
    - Flutter outline
    - Memory allocation in flutter
    - Render objects.
    - 3 Trees in flutter (Widget, Render & Element trees).
    - Detailed immutability in flutter widgets.

- **Optimizing Widgets**
    - Avoiding Rebuilds
    - Efficient Widget Building by flutter tools

---

#### 7. Testing and Debugging

- **Unit Testing**
    - Writing Unit Tests
    - Mocking

- **Widget Testing**
    - Testing Widgets
    - Golden Tests

- **Integration Testing**
    - Writing Integration Tests

- **Debugging Tools**
    - Flutter DevTools
    - Dart Observatory

**Books & Resources:**

- "Test-Driven Development: By Example" by Kent Beck
- Flutter Documentation (Testing) (https://flutter.dev/docs/testing)

---

#### 8. Architectural Principles

- **App Architecture**
    - Project structure
        - [Feature first vs Layer first](https://codewithandrea.com/articles/flutter-project-structure/)
    - Module architecture
        - [Layered architecture basic)](https://www.baeldung.com/cs/layered-architecture)

- **Well known app architectures**
    - MVVM (Model-View-ViewModel)
    - MVC (Model-View-Controller)
    - MVP (Model-View-Presenter)

- **Recommended app architecture docs**
    - [Guide to app architecture](https://developer.android.com/topic/architecture)

**Books & Resources:**

- "Object Oriented Thought Process" by Matt WeisFeld (For basic OOP)
- "Head First Object-Oriented Analysis and Design" by Brett D. McLaughlin, Gary Pollice, Dave West (
  For advanced OOP)
- "Clean Code" by Robert C. Martin (SOLID principles and general development programming best
  practices)
- "Clean Architecture: A Craftsman's Guide to Software Structure and Design" by Robert C. Martin
- "Design Patterns: Elements of Reusable Object-Oriented Software" by Erich Gamma, Richard Helm,
  Ralph Johnson, John Vlissides (Design patterns)

---

#### 9. Deployment and Maintenance

- **Building and Releasing**
    - iOS (App Store)
    - Android (Play Store)

- **Continuous Integration/Continuous Deployment (CI/CD)**
    - Setting up CI/CD
    - Tools (GitHub Actions, CircleCI, Codemagic, Fast lane etc)

- **App Maintenance**
    - Bug Fixes
    - Updates and Versioning
    - [Git flow](https://www.atlassian.com/git/tutorials/comparing-workflows/gitflow-workflow)

**Books & Resources:**

- "Continuous Delivery: Reliable Software Releases through Build, Test, and Deployment Automation"
  by Jez Humble and David Farley
- Flutter Documentation (Release & Deploy) (https://flutter.dev/docs/deployment)

---

### Happy coding!