# Practical-3: Implicit and Explicit Intent

## Aim
To create an Android application that demonstrates the use of **Implicit Intent** and **Explicit Intent** for performing different actions such as making a phone call, opening a URL, accessing the call log and gallery, setting an alarm, opening the camera, and navigating to another Activity.

## Tools Required
- Android Studio
- Android SDK
- Kotlin
- Android Emulator or Android device

## Practical Objectives

### 3.1 Make Call to Specific Number
Use an Intent with the `tel:` URI scheme to open the phone dialer or initiate a call to a specified phone number.

Concepts used:
- Implicit Intent
- `Intent.ACTION_DIAL`
- `Uri.parse()`
- `tel:`

### 3.2 Open Specific URL
Use an implicit Intent to open a specific website in the device's default web browser.

Concepts used:
- `Intent.ACTION_VIEW`
- `Uri.parse()`
- URL

### 3.3 Open Call Log
Use an Intent to open the device's call log.

Concepts used:
- `Intent.ACTION_VIEW`
- `CallLog.Calls.CONTENT_TYPE`

Appropriate permissions may be required depending on the Android version and the operation being performed.

### 3.4 Open Gallery
Use an Intent to open the device gallery and allow the user to select an image.

Concepts used:
- `Intent.ACTION_GET_CONTENT`
- `Intent.setType()`
- `"image/*"`

### 3.5 Set Alarm
Use an Intent to open the Android Alarm application and set an alarm.

Concepts used:
- `Intent.ACTION_SET_ALARM`
- Intent extras
- Implicit Intent

### 3.6 Open Camera
Use an Intent to open the device camera application.

Concepts used:
- `MediaStore.ACTION_IMAGE_CAPTURE`
- Implicit Intent
- Runtime permission handling where required

### 3.7 Open Login Activity
Use an **Explicit Intent** to navigate from the current Activity to a Login Activity within the same application.

Concepts used:
- Explicit Intent
- `Intent(this, LoginActivity::class.java)`
- `startActivity()`

## Types of Intent

### Implicit Intent
An implicit Intent does not specify the exact application or Activity that should handle the request. Android determines an appropriate application based on the requested action.

Examples:
- Opening a website
- Opening the dialer
- Opening the gallery
- Opening the camera

### Explicit Intent
An explicit Intent specifies the exact Activity or component that should be launched.

Example:

```kotlin
val intent = Intent(this, LoginActivity::class.java)
startActivity(intent)
```

## Important Intent Actions

Some commonly used Intent actions in this practical are:

| Intent Action | Purpose |
|---|---|
| `Intent.ACTION_VIEW` | View a resource such as a URL or call log |
| `Intent.ACTION_DIAL` | Open the phone dialer |
| `Intent.ACTION_GET_CONTENT` | Select content such as an image |
| `Intent.ACTION_SET_ALARM` | Create an alarm |
| `MediaStore.ACTION_IMAGE_CAPTURE` | Open the camera |
| Explicit Intent | Open a specific Activity |

## Important Intent Methods

### `setData()`
Sets the data URI associated with an Intent.

```kotlin
intent.setData(Uri.parse("tel:1234567890"))
```

### `setType()`
Specifies the MIME type of the data that an Intent should handle.

```kotlin
intent.setType("image/*")
```

### `Uri.parse()`
Converts a URI string into a `Uri` object.

```kotlin
Uri.parse("https://www.google.com")
```

### `startActivity()`
Starts an Activity using an Intent.

```kotlin
startActivity(intent)
```

## Buttons and Layouts

Create buttons for each operation and arrange them using Android layouts such as:

- `ConstraintLayout`
- `CoordinatorLayout`

Each button triggers its corresponding Intent when clicked.

## Permissions

Some Android operations require permissions to be declared in the `AndroidManifest.xml` file and, for dangerous permissions, requested at runtime.

Important concepts include:

```kotlin
ContextCompat.checkSelfPermission()
```

and

```kotlin
ActivityCompat.requestPermissions()
```

These APIs are used to check and request runtime permissions when required.

## ActivityResultContracts

Modern Android applications can use **Activity Result APIs** and `ActivityResultContracts` to receive results from other Activities or applications.

They provide a structured way to handle operations such as:
- Selecting images
- Requesting permissions
- Launching other Activities for results

## Important Resources and Constants

The following resources and constants are relevant to this practical:

- `ContactsContract.Contacts.CONTENT_TYPE`
- `CallLog.Calls.CONTENT_TYPE`
- `"image/*"`
- `"tel:"`
- `Uri.parse()`

## Expected Learning Outcomes

After completing this practical, the student will be able to:

1. Understand the concept of Android Intents.
2. Differentiate between Implicit and Explicit Intents.
3. Use different Intent actions.
4. Use `Intent.setData()` and `Intent.setType()`.
5. Use `Uri.parse()` for specifying Intent data.
6. Open websites, dialers, call logs, galleries, cameras, and alarm applications.
7. Navigate between Activities using Explicit Intent.
8. Use `startActivity()` to launch Activities.
9. Understand Android permissions and runtime permission handling.
10. Understand the use of `ActivityResultContracts`.
11. Work with buttons and Android layouts such as `ConstraintLayout` and `CoordinatorLayout`.

## Conclusion
This practical demonstrates how Android applications communicate with Activities and other applications using **Implicit and Explicit Intents**. It provides hands-on experience with Intent actions, URI data, MIME types, Activity navigation, permissions, and Activity Result APIs.
