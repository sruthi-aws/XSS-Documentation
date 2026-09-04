    # XSS Lab Documentation

## Overview

This documentation presents six XSS lab exercises, each demonstrating a different type of cross-site scripting vulnerability and how it can occur in a web application.

---

## Level 1 -- Hello, world of XSS

This level demonstrates a common cause of cross-site scripting where user input is directly included in the page without proper escaping.

**Objective:**
To inject a script to pop up a JavaScript `alert()` in the frame below.

**Script Injected:**

```html
<script>alert('XSS')</SCRIPT>
```

**Vulnerability Type:**
Reflected Cross-Site Scripting (XSS)

---

## Level 2 -- Persistence is key

This level shows how easily XSS bugs can be introduced in complex apps.

**Objective:**
Inject a script to pop up an `alert()` in the context of the application.

**Script Injected:**

```html
<img src=x onerror=alert(1)>
```

**Vulnerability Type:**
Stored Cross-Site Scripting (Stored XSS)

---

## Level 3 -- That sinking feeling...

In this level, some common JavaScript functions are execution sinks, which means that they will cause the browser to execute any scripts that appear in their input. Sometimes this fact is hidden by higher-level APIs that use one of these functions under the hood.

The application on this level is using one such hidden sink.

**Objective:**
To inject a script to pop up a JavaScript `alert()` in the app.

**Script Injected:**

```text
https://xss-game.appspot.com/level3/frame#1'/><script>alert(1)</script>
```

**Vulnerability Type:**
DOM-based Cross-Site Scripting (DOM XSS)

---

## Level 4 -- Context Matters

Every bit of user-supplied data must be correctly escaped for the context of the page in which it will appear.

**Objective:**
To inject a script to pop up an `alert()` in the application.

**Vulnerability Type:**
DOM-based reflected XSS

---

## Level 5 -- Breaking Protocol

Cross-site scripting isn't just about correctly escaping data. Sometimes, attackers can do bad things even without injecting new elements into the DOM.

**Objective:**
Inject a script to pop up an `alert()` in the context of the application.

**Script Injected:**

```text
https://xss-game.appspot.com/level5/frame/signup next=javascript:alert("1")
```

**Vulnerability Type:**
Open redirect with JavaScript protocol Injection (XSS)

---

## Level 6 -- Follow the...

Complex web applications sometimes have the capability to dynamically load JavaScript libraries based on the value of their URL parameters or part of the location or hash.

Allowing user input to influence the URL when loading scripts or other potentially dangerous types of data such as XML Http Request often leads to serious vulnerabilities.

**Objective:**
To find a way to make the application request an external file which will cause it to execute an `alert()`.

**Script Injected:**

```text
https://xss-game.appspot.com/level6/frame#data:text/javascript,alert(1);
```

**Vulnerability Type:**
DOM-Based XSS

---

## Summary

| Level | Topic                   | Vulnerability Type                                     |
| ----- | ----------------------- | ------------------------------------------------------ |
| 1     | Hello, world of XSS     | Reflected Cross-Site Scripting (XSS)                   |
| 2     | Persistence is key      | Stored Cross-Site Scripting (Stored XSS)               |
| 3     | That sinking feeling... | DOM-based Cross-Site Scripting (DOM XSS)               |
| 4     | Context Matters         | DOM-based reflected XSS                                |
| 5     | Breaking Protocol       | Open redirect with JavaScript protocol Injection (XSS) |
| 6     | Follow the...           | DOM-Based XSS                                          |

---

## Lab Exercise

This repository documents the six XSS lab exercises, including the objectives, scripts used during the exercises, and the vulnerability type demonstrated at each level.

