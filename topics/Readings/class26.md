# Class 26 reading:
# Android Intents and Activities

## Android Intents

In Android, an Intent is a fundamental component used for communication between different parts of an application or between different applications. Essentially, it's a message that specifies an action to be performed. Intents are used to start activities, services, and broadcast receivers, making them a crucial part of Android's inter-component communication system.

### Examples of Using Intents

1. **Starting an Activity**: When you want to open a new screen or window in your Android app, you use an Intent to request this action. For instance, you might have a button in your app, and when the user taps it, you use an Intent to start a new activity to display more details.

2. **Broadcasting Events**: Intents can be used to send broadcast messages within an app or to other apps. For instance, an app can send an intent to notify other apps that the device's battery is low.

3. **Service Invocation**: If you want to start a background service to perform some task, you can use an Intent to initiate the service. For example, a music player app might use an Intent to start a service that plays music in the background.

4. **Implicit Intents**: These are used when you want to delegate a task to another app. For example, you might want the user to take a photo. Instead of writing your own camera functionality, you can use an Intent to ask the system to open a camera app.

## Activities

An Activity in Android is a fundamental building block of an app's user interface. It represents a single screen with a user interface. Think of it as a self-contained window where you can display and interact with the app's content. Each screen in an Android app is usually implemented as an Activity.

### Key Points about Activities

- **User Interface**: Activities manage the UI and user interactions. They represent what the end user sees and interacts with in an Android app.

- **Lifecycle**: Activities have a specific lifecycle. They are responsible for creating views, handling user input, and responding to events.

- **UI Components**: Activities are responsible for managing and displaying UI components, such as buttons, text fields, and images.

- **Variety**: Activities can vary from simple screens displaying static text to complex screens with web browsers, maps, or any other interactive elements.

In simple terms, an Activity is what the end user sees and interacts with in an Android app. It defines the visual representation of a single window or page of your app and handles the logic for that particular user interface.
