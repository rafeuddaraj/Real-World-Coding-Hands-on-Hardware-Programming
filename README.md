# Arduino Programming Basics

This document covers the fundamental concepts of Arduino programming. It is beginner-friendly and structured step-by-step.

---

## 1. Basic Syntax

- Each statement ends with a semicolon `;`
- Code blocks are enclosed in `{ }`
- `setup()` and `loop()` are the two main functions in every Arduino sketch

```cpp
void setup() {
  // initialization code
}

void loop() {
  // repeated code
}
```

---

## 2. Input and Output

### Serial Output

Use `Serial.begin()` and `Serial.print()` to print messages to your computer.

```cpp
void setup() {
  Serial.begin(9600);
}

void loop() {
  Serial.println("Hello from Arduino!");
  delay(1000);
}
```

### Serial Input

Read values from Serial Monitor.

```cpp
String input;

void setup() {
  Serial.begin(9600);
}

void loop() {
  if (Serial.available()) {
    input = Serial.readString();
    Serial.println("You typed: " + input);
  }
}
```

---


### Digital Output

Use `digitalWrite(pin, HIGH/LOW)` to turn something on or off.

```cpp
void setup() {
  pinMode(13, OUTPUT);
}

void loop() {
  digitalWrite(13, HIGH); // turn LED on
  delay(1000);
  digitalWrite(13, LOW);  // turn LED off
  delay(1000);
}
```

### Digital Input

Use `digitalRead(pin)` to read button state or sensor.

```cpp
void setup() {
  pinMode(2, INPUT);
  pinMode(13, OUTPUT);
}

void loop() {
  if (digitalRead(2) == HIGH) {
    digitalWrite(13, HIGH);
  } else {
    digitalWrite(13, LOW);
  }
}
```


## 3. Variables

Variables store data. Common types:

- `int` — Integer values
- `float` — Decimal numbers
- `char` — Single characters
- `String` — Text
- `bool` — True or false

```cpp
int ledPin = 13;
float voltage = 3.3;
char letter = 'A';
String name = "Arduino";
bool isOn = true;
```

---

## 4. Operators

Used for calculations and logic.

### Arithmetic
- `+`, `-`, `*`, `/`, `%`

### Comparison
- `==`, `!=`, `>`, `<`, `>=`, `<=`

### Logical
- `&&` (AND), `||` (OR), `!` (NOT)

```cpp
int a = 5 + 3;      // 8
bool result = a > 4 && a < 10;  // true
```

---

## 5. Conditions (if, else)

```cpp
if (digitalRead(2) == HIGH) {
  digitalWrite(13, HIGH);
} else {
  digitalWrite(13, LOW);
}
```

---

## 6. Loops

### `for` loop
```cpp
for (int i = 0; i < 10; i++) {
  Serial.println(i);
}
```

### `while` loop
```cpp
int i = 0;
while (i < 10) {
  Serial.println(i);
  i++;
}
```

---

## 7. Functions

Functions help organize code into reusable blocks.

```cpp
void blinkLED() {
  digitalWrite(13, HIGH);
  delay(1000);
  digitalWrite(13, LOW);
  delay(1000);
}
```

Call the function inside `loop()`:
```cpp
void loop() {
  blinkLED();
}
```

---

## 8. Arrays

Arrays store multiple values of the same type.

```cpp
int numbers[] = {1, 2, 3, 4, 5};

void loop() {
  for (int i = 0; i < 5; i++) {
    Serial.println(numbers[i]);
  }
}
```

---
