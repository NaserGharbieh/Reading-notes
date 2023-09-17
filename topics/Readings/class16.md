# Class 16 reading: Spring security. 

# Authentication and Authorization

Authentication and authorization are fundamental concepts in security and access control for applications:

## Authentication

Authentication is the process of verifying the identity of a user, device, or system trying to access a resource or perform an action within an application. It answers the question, "Who are you?" When a user logs in, they typically provide credentials (such as a username and password), and the system checks these credentials to ensure that the user is who they claim to be.

## Authorization

Authorization, on the other hand, comes after authentication and involves determining what actions or resources a user is allowed to access or perform within the application. It answers the question, "What are you allowed to do?" Authorization is based on the user's identity and their associated permissions or roles. It ensures that authenticated users can only access the parts of the system they are authorized to use.

## AuthenticationManager's authenticate() Method Outcomes

The `authenticate()` method of an `AuthenticationManager` can have three possible outcomes:

- **Return an Authenticated User**: If the provided credentials (e.g., username and password) are valid and match what's stored in the system, the `authenticate()` method returns an authenticated user. This means the user is successfully authenticated, and they can proceed with their intended actions.

- **Throw an AuthenticationException**: If the provided credentials are invalid, expired, or there are other issues with authentication, the `authenticate()` method can throw an `AuthenticationException`. This signals that the authentication process has failed, and the user's identity could not be verified.

- **Return null**: In some cases, the `authenticate()` method might return null. This typically happens when it cannot make a determination regarding the authentication status. This might occur when, for example, the provided credentials are incomplete or ambiguous.

These outcomes are crucial for the security of an application because they dictate whether a user gains access to protected resources or not. Successful authentication is a prerequisite for authorization, which then controls what actions a user can perform within the application based on their identity and roles.

# Spring Auth Cheat Sheet

## Step 1: Set Up a User Model and Repo

- Create a user model class and repository for managing user data.

## Step 2: Create a Controller for That Model

- Develop a controller to handle HTTP requests related to user actions, such as registration and login.

## Step 3: UserDetailsServiceImpl Implements UserDetailsService

- Implement `UserDetailsServiceImpl`, a class that implements the Spring Security `UserDetailsService` interface.
- This class is responsible for retrieving user details from the database based on their username.
- Ensure your repository has a method to retrieve users by username efficiently.

## Step 4: ApplicationUser Implements UserDetails

- Implement the `ApplicationUser` class, which should implement the `UserDetails` interface.
- Ensure that the required methods are properly implemented, and the boolean methods return `true`.

## Step 5: WebSecurityConfig Extends WebSecurityConfigurerAdapter

- Create the `WebSecurityConfig` class, a configuration class that extends `WebSecurityConfigurerAdapter`.
- Configure security settings in this class, including defining a `UserDetailsService` bean and a `passwordEncoder` bean.
- In the `configure(AuthenticationManagerBuilder)` method, configure user authentication using the `userDetailsService` and specify the password encoder.
- In the `configure(HttpSecurity)` method, configure various security settings:
  - Enable or disable CORS and CSRF protection.
  - Define URL matchers for allowed endpoints.
  - Set up login and signup URLs.
  - Configure form login and specify logout behavior.
- Override the `authenticationManagerBean()` method to expose the `AuthenticationManager` as a bean.

## Step 6: Registration Page

- Create a registration page with a user registration form.
- Ensure that the form submits data to an endpoint handled by your controller.
- Verify that user data is correctly saved in the database.
- Optionally, consider implementing auto-login after successful registration.

## Step 7: Login Page

- Create a login page with a user authentication form.
- Make sure the form posts data to the route specified in your web configuration (`configure(HttpSecurity)`).
- Test the login functionality.
- Optionally, add information about the authenticated user (Principal) to your application's templates.

This cheat sheet provides a structured approach to implementing user authentication and authorization in a Spring application. Customize these steps to fit your application's specific requirements.