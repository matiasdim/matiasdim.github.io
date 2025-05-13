---
layout: post
title: "SOLID Principles of Object-Oriented Programming"
date: 2025-05-13
categories: [programming, solid]
tags: [SOLID, OOP, Swift]
author: "Matias Gil"
---

# SOLID Principles of Object-Oriented Programming

## “Swifty” explained

- **S**: Single Responsibility Principle
- **O**: Open-Closed Principle
- **L**: Liskov Substitution Principle
- **I**: Interface Segregation Principle
- **D**: Dependency Inversion Principle

These are design principles to always keep in mind when coding to make better software. They make software more maintainable, flexible, and testable.

---

## Single Responsibility Principle

This is about the separation of concerns. A class should only have a single responsibility.  
Another way to define this is that "a class or module should have one, and only one, reason to be changed". This is because the class is supposed to have, as mentioned, only one responsibility. This will lead us to have a better understanding of objects' responsibilities, it will be easier to find bugs, and also our code will be way less error-prone when changes have to be done.

**SRP Violation:**

```swift
class Employee {
    var name: String
    var email: String

    func validateEmail() -> Bool {
        // Validation Logic
    }

    func showInfo() {
        // Show employee info
    }
}
```

Above we can see that `Employee` not only has the responsibility to show its info but also to validate the format for some of its attributes. We are adding extra responsibility to the class, thus violating SRP.

**SRP Compliant:**

```swift
class Email {
    var address: String

    func isValid() -> Bool {
        // Validation Logic
    }
}

class Employee {
    var name: String
    var email: Email

    func showInfo() {
        // Show employee info
    }
}
```
Now `Employee` is free of the responsibility to validate the email, and Email is the one doing that. We clearly separated responsibilities.
