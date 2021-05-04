# Basic
- `CalendarModule` allow to access Android's calendar APIs from JS
- Call `CalendarModule.createCalendarEvent('Dinner Party', 'My house');` at the end
- `const { CalendarModule } = ReactNative.NativeModules;` to access the native module in JS
- All native module methods meant to be invoked from JavaScript must be annotated with `@ReactMethod`.
- invoked in JS through `CalendarModule.createCalendarEvent()`
- Register the module: add your native module to a `ReactPackage` and register the `ReactPackage` with React Native.
  - To add your Native Module to `ReactPackage`, first create a new Java Class named `MyAppPackage.java` that implements ReactPackage
- To register the `CalendarModule` package, you must add `MyAppPackage` to the list of packages returned in ReactNativeHost's `getPackages()` method.
# Beyond a Calendar Native Module
- Better Native Module Export: Export modules to files
- Exporting Constants: method `getConstants()` which is available in JS
- Callbacks: Native modules also support a unique kind of argument: a callback. Callbacks are used to pass data from Java to JavaScript for asynchronous methods. They can also be used to asynchronously execute JavaScript from the native side.
- Promises
- Sending Events to JS: Native modules can signal events to JavaScript without being invoked directly. For example, you might want to signal to JavaScript a reminder that a calendar event from the native Android calendar app will occur soon.
- Getting Activity Result from `startActivityForResult`: You'll need to listen to `onActivityResult` if you want to get results from an activity you started with `startActivityForResult`
- Listening to Lifecycle Events: Listening to the activity's LifeCycle events such as `onResume`, `onPause` etc. is very similar to how `ActivityEventListener` was implemented.
- Threading: 
