# Unit Testing in Flutter

## What is Unit Testing?
Unit testing is a software testing method where you test individual functions or components (called "units") in isolation — meaning the unit is tested without relying on any UI, databases, or external systems.

In Flutter, this means testing Dart functions like validators, calculators, or business logic separately, to make sure they return the correct output for given inputs.

## Types of Tests in Flutter
Flutter has three main types of tests:

### 1) Unit Tests
Test a single function, method, or class in isolation.</br>
Example: Validating an email string.

### 2) Widget Tests
Test a single widget’s UI and interactions.</br>
Example: Tapping a button should trigger a specific action.

### 3) Integration Tests
Test the complete app or a large part of it, including UI, backend, and navigation.</br>
Example: Login flow from typing to redirection.

## AAA Pattern (Arrange–Act–Assert)
This is the most common structure used in writing tests:

- **Arrange:** Set up the input, dependencies, or conditions.

- **Act:** Execute the function or behavior you're testing.

- **Assert:** Check the output or result to confirm it behaves as expected.

```dart
test("Valid email should return true", () {
  // Arrange
  final email = "example@gmail.com";

  // Act
  final result = isValidateEmail(email);

  // Assert
  expect(result, true);
});
```

You’ll see this structure followed in the example above to keep tests clean, readable, and consistent.

---

This repository contains a basic example of **unit testing** in Flutter, focused on testing an email validation function.

### 📁 Project Structure

```bash
lib/
└── email_validator.dart      # Contains the email validation logic

test/
└── unit_test.dart            # Contains unit tests for the validator
```

### Email Validator Test

```dart
// Email validator test
bool isValidateEmail(String email) {
  return email.contains('@');
}
```

### Unit Testing

```dart
import 'package:flutter_test/flutter_test.dart';
import 'package:flutter_testing/email_validator.dart';

void main() {
  // Test case for valid email
  test("Valid email should return true", () {
    final result = isValidateEmail("shahzainahmed57@gmail.com");
    print('Result for valid email: $result');
    expect(result, true);
  });

  // Test case for invalid email
  test("Invalid email should return false", () {
    final result = isValidateEmail("shahzainahmed57gmail.com");
    print('Result for invalid email: $result');
    expect(result, false);
  });
}

```

## How to Run Tests

```bash
flutter test
```

You’ll see output similar to:

```makefile
00:03 +2: All tests passed!
```
