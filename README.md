# AppLogger

A utility library for structured and customizable logging in Dart and Flutter applications. This library provides static logging methods and an extension to make logging easier and more convenient for any object.

---

### Developer Information
- **Name:** Md. Shamsuzzaman
- **GitHub:** [zamansheikh](https://github.com/zamansheikh)

---

## Features
- **Customizable PrettyPrinter:** Includes method call depth, colorful output, emojis, and date-time formatting.
- **Log Levels:** Supports different log levels (Debug, Info, Warning, Error, Fatal).
- **Object Extension:** Adds logging methods directly to objects using Dart extensions.
- **Stack Trace Support:** Logs errors with stack traces when provided.

---

## Installation

Add the `logger` package as a dependency in your `pubspec.yaml` file:
```yaml
dependencies:
  logger: ^1.3.0 # Replace with the latest version
```

Then, include the `AppLogger` class in your project.

---

## Usage

### 1. Static Logging
You can log messages directly using the static methods of `AppLogger`.

```dart
AppLogger.d("This is a debug message.");
AppLogger.i("This is an informational message.");
AppLogger.w("This is a warning message.");
AppLogger.e("This is an error message.", Exception("Sample exception"));
AppLogger.f("This is a fatal error message.");
```

### 2. Logging with Object Extension
Use the `Loggable` extension to log messages directly from any object.

```dart
"A debug message".logD();
123.logI();
Exception("An error occurred").logE();
```

### 3. Stack Trace Logging
Include stack traces and error details for better debugging.

```dart
try {
  throw Exception("Simulated exception");
} catch (e, stack) {
  AppLogger.e("Caught an exception", e, stack);
}
```

---

## Code Example
Here’s a full example to demonstrate `AppLogger` in a Flutter application:

```dart
import 'package:flutter/material.dart';
import 'app_logger.dart'; // Replace with the actual path of your logger file

void main() {
  runApp(MyApp());
}

class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    AppLogger.i("Application started.");

    return MaterialApp(
      home: Scaffold(
        appBar: AppBar(title: Text('AppLogger Example')),
        body: Center(
          child: ElevatedButton(
            onPressed: () {
              try {
                throw Exception("Sample exception");
              } catch (e, stack) {
                AppLogger.e("Button click error", e, stack);
              }
            },
            child: Text('Trigger Error'),
          ),
        ),
      ),
    );
  }
}
```

---

## Features in Detail

| Method      | Description                            | Parameters                                                                 |
|-------------|----------------------------------------|---------------------------------------------------------------------------|
| `d`         | Logs a debug message                  | `message`: required, `error` and `stackTrace`: optional                   |
| `i`         | Logs an informational message         | `message`: required, `error` and `stackTrace`: optional                   |
| `w`         | Logs a warning message                | `message`: required, `error` and `stackTrace`: optional                   |
| `e`         | Logs an error message                 | `message`: required, `error` and `stackTrace`: optional                   |
| `f`         | Logs a fatal error message            | `message`: required, `error` and `stackTrace`: optional                   |

---

## License

This project is open-source and available under the [MIT License](LICENSE).

---

### Contact
Feel free to reach out or contribute to the project!
- GitHub: [zamansheikh](https://github.com/zamansheikh)
```

### Key Features of the Documentation
1. **Introduction:** Briefly explains the purpose of `AppLogger`.
2. **Installation Instructions:** Guides the user on setting up dependencies.
3. **Usage Examples:** Covers both static methods and extensions.
4. **Code Example:** Demonstrates integration into a Flutter application.
5. **Detailed API Documentation:** Explains available methods and their parameters.
6. **Developer Information:** Includes your name and GitHub profile for proper attribution.
