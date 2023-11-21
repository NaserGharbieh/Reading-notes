# Class 37 Reading:

# Amazon S3 Overview

Amazon Simple Storage Service (S3) is a scalable, object storage service provided by Amazon Web Services (AWS). It is designed for storing and retrieving data ranging from gigabytes to petabytes at low costs. S3 finds applications in various scenarios, including web hosting, data lakes, backups, and disaster recovery.

## Key Features

1. **Storage Classes:** Offers different storage classes to optimize costs and performance.
2. **Storage Management:** Provides tools for efficient management of stored data.
3. **Access Management and Security:** Ensures secure access and management of stored objects.
4. **Data Processing:** Supports data processing directly within the storage service.

## Object Key

An object key is a unique identifier for an object in S3, consisting of a bucket name and an object name. For instance, "myBucket/myImage.jpg" identifies an object named "myImage.jpg" in the bucket "myBucket."

## S3 with Amplify

Amplify, an AWS framework, simplifies the integration of AWS features into mobile and web applications. The Storage category in Amplify facilitates interactions with S3.

## Dependencies for Amplify AWS S3 in Android Application

```gradle
dependencies {
    implementation 'com.amplifyframework:aws-storage-s3:2.14.5'
    implementation 'com.amplifyframework:aws-auth-cognito:2.14.5'
}
```

## Uploading Data to S3 with Amplify

To upload to S3, specify the key and data object. Here's an example using Amplify's Storage category:

```java
private void uploadFile() {
    File exampleFile = new File(getApplicationContext().getFilesDir(), "ExampleKey");

    try {
        BufferedWriter writer = new BufferedWriter(new FileWriter(exampleFile));
        writer.append("Example file contents");
        writer.close();
    } catch (Exception exception) {
        Log.e("MyAmplifyApp", "Upload failed", exception);
    }

    Amplify.Storage.uploadFile(
            "ExampleKey",
            exampleFile,
            result -> Log.i("MyAmplifyApp", "Successfully uploaded: " + result.getKey()),
            storageFailure -> Log.e("MyAmplifyApp", "Upload failed", storageFailure)
    );
}
```

After executing this code, you should see a new folder called "public" in your bucket containing a file named "ExampleKey" with the contents "Example file contents."

## Initializing Amplify Auth and Storage Categories

To initialize the Amplify Auth and Storage categories, call the `Amplify.addPlugin()` method for each category. Complete initialization by calling `Amplify.configure()`.

```java
public class MyAmplifyApp extends Application {
    @Override
    public void onCreate() {
        super.onCreate();

        try {
            Amplify.addPlugin(new AWSCognitoAuthPlugin());
            Amplify.addPlugin(new AWSS3StoragePlugin());
            Amplify.configure(getApplicationContext());

            Log.i("MyAmplifyApp", "Initialized Amplify");
        } catch (AmplifyException error) {
            Log.e("MyAmplifyApp", "Could not initialize Amplify", error);
        }
    }
}
```

Note: Because the storage category requires auth, configure guest access or sign in a user before using storage category features.




