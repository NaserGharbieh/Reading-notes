# Class 38 Reading

# Intent Filters

## Three Criteria for an Activity's Intent Filter

An activity's intent filter must fulfill the following three criteria for a system to send an intent to that activity:

- **Action:** Describes the general action to be performed, such as `ACTION_VIEW` for viewing data or `ACTION_SEND` for sending data.
  
- **Data:** Specifies the type of data to be acted upon, such as a specific MIME type, URI, or a certain data scheme.
  
- **Category:** Represents additional information about the kind of component that should handle the intent, such as `CATEGORY_LAUNCHER` for the main entry point of the application.

## Retrieving the Intent

An activity in Android can retrieve the intent that started it by calling the `getIntent()` method. This method returns the Intent that started the activity.

## Explaining Intents

Explaining intents to a non-technical friend: Think of an intent as a message or a request that one part of an Android app (or even different apps) sends to another part. It’s like asking another component to perform a specific action or provide some information. For example, when you tap on an email app icon, it sends an intent to the activity responsible for composing emails, telling it to open up and let you write a new email.

## Implicit vs. Explicit Intents

### Explicit Intents:

- Specify the target component (activity, service, etc.) by its class name.
  
- Used for intra-application communication.
  
- Directly invoke a specific component within the app.

### Implicit Intents:

- Do not specify the target component’s name.
  
- Used for inter-application communication.
  
- Describe a general action, and the Android system determines the appropriate component to fulfill that action based on the device’s installed apps and their declared intent filters.

## Primary Information Contained within an Intent

- **Action:** Describes what to do, like opening a web page or dialing a phone number.
  
- **Data:** Specifies the type of data on which the action should be performed, such as a URL or a contact.
  
- **Extras:** Additional information passed as key-value pairs, providing more details for the action.
  
- **Component:** For explicit intents, the target component (e.g., the class name of an activity).
