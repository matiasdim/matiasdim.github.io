---
layout: post
title: "Single Responsibility Principle"
date: 2025-05-13
categories: [programming, principles]
tags: [SOLID, OOP, Swift, srp]
author: "Matias Gil"
---

#### Go back to the [main SOLID blog post](/2025-05-13-SOLID-Principles-of-Object-Oriented-Programming/)

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
