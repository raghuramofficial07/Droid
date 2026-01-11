<!-- GitHub Project Banner -->
<p align="center">
  <img src="https://github.com/user-attachments/assets/501c98ee-809c-4376-b32d-6d38ae07c489" alt="Project Banner" width="100%">
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Droid-black?logo=android&logoColor=white&labelColor=black&color=black">
  <img src="https://img.shields.io/badge/Built%20by-RaghuRam-black?labelColor=black&color=black">
</p>

# Android Development — Core Foundations

This document explains Android development fundamentals from a modern, Compose-first perspective.
The focus is not memorization, but understanding how data, state, and UI principles work together.

---

## » Data Types in Android (Kotlin)

Android development with Jetpack Compose is written in Kotlin.
Kotlin is strongly typed, meaning every value has a type and a defined behavior.

Data types exist to:
- define what kind of data you are working with
- control memory usage
- make UI predictable and safe

---

### » Primitive Data Types

#### Int
```kotlin
val age: Int = 21
```

#### Long
```kotlin
val distance: Long = 1_000_000L
```

#### Float
```kotlin
val rating: Float = 4.5f
```

#### Double
```kotlin
val price: Double = 99.99
```

#### Boolean
```kotlin
val isLoggedIn: Boolean = true
```

---

### » String

```kotlin
val username: String = "RaghuRam"
```

---

## » Variables: val vs var

```kotlin
val name = "Android"
var count = 0
```

---

## » State in Jetpack Compose

```kotlin
var counter by remember { mutableStateOf(0) }
```

---

## » Principle of UI Design — S.P.B.I

- S — Spacing
- P — Padding
- B — Behavior
- I — Interaction

---

## » Correct Layering

Surface → Presentation  
Box → Spacing  
TextField → Behavior  

---

## » Author Footer

Created By: Vemparala Sri Satya RaghuRam  
License: MIT  
Platform: Android (Jetpack Compose)
