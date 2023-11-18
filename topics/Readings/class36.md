# Class 35 Reading :
# Amplify Auth Setup

## Where to Check Auth Session

You should check the current auth session at a relevant point in your application, often during the initialization phase or when the user is interacting with features that require authentication. 
 
[This Amplify Auth Setup Article](https://docs.amplify.aws/android/build-a-backend/auth/set-up-auth/) suggested checking the current auth session in the `onCreate` method of your `MainActivity` for testing purposes.

## Command to Push Changes to Cloud

The command used to push your changes to the cloud is **`amplify push`.**
This command deploys your backend resources, including any changes you made, to the cloud.

## What Amplify Auth Does

Amplify Auth provides an interface for authenticating users in your application. It handles the necessary authorization behind the scenes for other Amplify categories.

 Amplify Auth supports various authentication providers and comes with default support for Amazon Cognito User Pool and Identity Pool. 

Amplify Auth enables your application to authenticate users securely, allowing you to implement features like sign-in, sign-up, and user sessions.



