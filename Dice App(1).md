<!-- GitHub Project Banner -->
<p align="center">
  <img src="https://github.com/user-attachments/assets/501c98ee-809c-4376-b32d-6d38ae07c489" alt="Project Banner" width="100%">
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Droid-black?logo=android&logoColor=white&labelColor=black&color=black">
  <img src="https://img.shields.io/badge/Built%20by-RaghuRam-black?labelColor=black&color=black">
</p>

# Dice Roller App — Learn by Building

This document guides you to build a Dice Roller app step by step using Jetpack Compose.
It is designed so that a user can follow along while reading the Droid documentation and build the app independently.

---

## » What the App Does

- Displays a dice image (1–6)
- Displays text showing the current dice value
- Contains a button labeled **Click Me**
- On button click:
  - Generates a random number
  - Updates both text and image automatically

---

## » Required Resources

Add the following images to:

app/src/main/res/drawable/

- dice_1.png
- dice_2.png
- dice_3.png
- dice_4.png
- dice_5.png
- dice_6.png

---

## » Core Concepts Used

- @Composable
- remember
- mutableStateOf
- State-driven UI
- Column layout
- Image composable
- Button interaction

---

## » Entry Point

```kotlin
class MainActivity : ComponentActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContent {
            DiceApp()
        }
    }
}
```

---

## » Dice App Composable

```kotlin
@Composable
fun DiceApp() {
```

This function represents the entire screen.

---

## » State Declaration

```kotlin
var diceValue by remember { mutableStateOf(1) }
```

State controls both the image and text. When the state changes, the UI updates automatically.

---

## » Dice Image Mapping

```kotlin
val diceImage = when (diceValue) {
    1 -> R.drawable.dice_1
    2 -> R.drawable.dice_2
    3 -> R.drawable.dice_3
    4 -> R.drawable.dice_4
    5 -> R.drawable.dice_5
    else -> R.drawable.dice_6
}
```

---

## » UI Layout

```kotlin
Column(
    modifier = Modifier
        .fillMaxSize()
        .padding(24.dp),
    verticalArrangement = Arrangement.Center,
    horizontalAlignment = Alignment.CenterHorizontally
) {
```

---

## » Dice Image

```kotlin
Image(
    painter = painterResource(id = diceImage),
    contentDescription = "Dice Image",
    modifier = Modifier.size(150.dp)
)
```

---

## » Dice Text

```kotlin
Text(
    text = "Dice Value: $diceValue",
    style = MaterialTheme.typography.headlineMedium
)
```

---

## » Button Interaction

```kotlin
Button(
    onClick = {
        diceValue = (1..6).random()
    }
) {
    Text("Click Me")
}
```

---

## » Complete Working Code

```kotlin
@Composable
fun DiceApp() {

    var diceValue by remember { mutableStateOf(1) }

    val diceImage = when (diceValue) {
        1 -> R.drawable.dice_1
        2 -> R.drawable.dice_2
        3 -> R.drawable.dice_3
        4 -> R.drawable.dice_4
        5 -> R.drawable.dice_5
        else -> R.drawable.dice_6
    }

    Column(
        modifier = Modifier
            .fillMaxSize()
            .padding(24.dp),
        verticalArrangement = Arrangement.Center,
        horizontalAlignment = Alignment.CenterHorizontally
    ) {

        Image(
            painter = painterResource(id = diceImage),
            contentDescription = "Dice Image",
            modifier = Modifier.size(150.dp)
        )

        Spacer(modifier = Modifier.height(16.dp))

        Text(
            text = "Dice Value: $diceValue",
            style = MaterialTheme.typography.headlineMedium
        )

        Spacer(modifier = Modifier.height(24.dp))

        Button(
            onClick = {
                diceValue = (1..6).random()
            }
        ) {
            Text("Click Me")
        }
    }
}
```

---

## » Design Principle Applied (S.P.B.I)

- Spacing → Spacer, Arrangement
- Padding → Modifier.padding
- Behavior → diceValue state
- Interaction → Button click
- Presentation → Image and Text

---

## » Final Note

This Dice App demonstrates the fundamentals of modern Android UI development using Jetpack Compose.
It avoids outdated patterns and focuses on clarity, state, and control.

---

## » Author Footer

Created By: Vemparala Sri Satya RaghuRam  
License: MIT  
Platform: Android (Jetpack Compose)
