# 🚀 Object-Oriented Programming (OOPs) - Complete Revision Notes

> Based on LLD (Low Level Design) Lecture Notes
> Beginner Friendly + Interview Oriented + Revision Ready

---

# 📚 Table of Contents

1. History of Programming
2. Why OOPs Was Introduced
3. Real World Modeling
4. Object, Class, Characteristics & Behavior
5. Procedural Programming vs OOP
6. OOP Ideology
7. Four Pillars of OOP
8. Abstraction
9. Encapsulation
10. Abstraction vs Encapsulation
11. Interview Questions
12. Quick Revision Sheet

---

# 🏛️ Evolution of Programming Languages

```text
Machine Language
      ↓
Assembly Language
      ↓
Procedural Programming
      ↓
Object Oriented Programming
```

---

## 1️⃣ Machine Language

### Example

```text
0101011010101010
1101010101010101
```

### Problems

❌ Difficult to read

❌ Error prone

❌ Not scalable

❌ Hardware dependent

❌ Impossible to build large applications

---

## 2️⃣ Assembly Language

### Example

```assembly
MOV A, 61H
```

### Advantages

✅ Introduced Mnemonics

✅ Easier than Machine Code

### Problems

❌ Hardware dependent

❌ Difficult maintenance

❌ Low scalability

❌ Complex for large systems

---

## 3️⃣ Procedural Programming

### Examples

* C Language
* Pascal

### Introduced

✅ Functions

✅ Loops

✅ Conditional Statements

```c
if(condition){
   ...
}

for(int i=0;i<n;i++){
   ...
}
```

### Limitation

Could solve small problems but struggled with:

* Large systems
* Real world modeling
* Reusability
* Scalability

---

# 🤔 Why OOPs Was Needed?

Procedural Programming had 3 major problems.

```text
+----------------------+
| Procedural Problems |
+----------------------+
          |
          +--> No Real World Modeling
          |
          +--> Poor Data Security
          |
          +--> Poor Reusability
                     &
               Scalability
```

---

# 🌍 Real World Modeling

Real World contains:

```text
Objects
   ↓
Interact with each other
```

Examples:

* Car
* Owner
* Mobile
* Laptop
* Camera

Everything is an Object.

---

# 🏎️ Understanding Object

Every Object has:

```text
Object
│
├── Characteristics (Properties)
│
└── Behaviors (Actions)
```

---

## Example: Car

### Characteristics (State)

```text
Brand
Model
Engine
Wheels
Color
```

### Behaviors (Methods)

```text
Start()
Stop()
ShiftGear()
Accelerate()
Brake()
```

---

# 🏗️ Class & Object

### Class

Blueprint of an Object.

```java
class Car {

}
```

### Object

Real instance of Class.

```java
Car myCar = new Car();
```

---

# ⚔️ Procedural Programming vs OOP

---

## Procedural Approach

```java
String brand;
String model;
boolean isEngineOn;

start();
stop();
shiftGear();
```

### Problems

❌ Too many variables

❌ Too many functions

❌ Difficult relationships

❌ Difficult maintenance

❌ Duplicate code

---

## OOP Approach

```java
class Car {
    String brand;
    String model;

    void start(){}
    void stop(){}
}
```

```java
class Owner {
    String name;
    Car car;

    void drive(){}
}
```

### Benefits

✅ Real world representation

✅ Easy maintenance

✅ Reusability

✅ Scalability

---

# 🎯 Core Philosophy of OOP

> Programming should behave exactly like the real world.

Real World:

```text
Objects ↔ Objects
```

Programming:

```text
Objects ↔ Objects
```

---

# 🏛️ Four Pillars of OOP

```text
          OOP
           │
 ┌─────────┼─────────┐
 │         │         │
 ▼         ▼         ▼
Abstraction
Encapsulation
Inheritance
Polymorphism
```

(Current lecture covered first two)

---

# 1️⃣ Abstraction

---

## Real World Example

### Driving a Car

You know:

```text
Start Engine
Shift Gear
Accelerate
Brake
```

You DON'T know:

```text
How engine works internally
How gearbox works internally
How fuel combustion works
```

Yet car works perfectly.

---

## Definition

> Hide unnecessary implementation details and expose only required functionality.

---

## Diagram

```text
User
  │
  ▼
Interface
(Car Controls)
  │
  ▼
Complex Internal Logic
(Hidden)
```

---

## Key Idea

Show:

```text
What to do
```

Hide:

```text
How it is done
```

---

# Abstraction in Code

## Abstract Class

```java
abstract class Car {

    abstract void startEngine();

    abstract void shiftGear(int gear);

    abstract void accelerate();

    abstract void brake();

    abstract void stopEngine();
}
```

---

## Concrete Implementation

```java
class SportsCar extends Car {

    @Override
    void startEngine() {
        System.out.println("Engine Started");
    }

    @Override
    void accelerate() {
        System.out.println("Accelerating");
    }
}
```

---

## Usage

```java
Car car = new SportsCar();

car.startEngine();
car.accelerate();
```

---

## What User Sees

```java
car.startEngine();
```

## What User Doesn't See

```java
Fuel Injection
Combustion
Piston Movement
Crankshaft Rotation
```

---

## Real Life Examples

| Object | Interface        |
| ------ | ---------------- |
| TV     | Remote           |
| Car    | Steering, Pedals |
| Mobile | Touch Screen     |
| ATM    | ATM Screen       |

---

# 📌 Abstraction Formula

```text
Hide Complexity
+
Expose Essentials
=
Abstraction
```

---

# 2️⃣ Encapsulation

---

## Meaning

Encapsulation = Wrapping Data + Methods together

Like a capsule containing medicine.

---

## Diagram

```text
+------------------+
|      Car         |
|------------------|
| brand            |
| model            |
| speed            |
|------------------|
| start()          |
| stop()           |
| accelerate()     |
+------------------+
```

Everything related to Car remains inside Car.

---

# Definition

> Binding data and behavior together into a single unit and protecting sensitive data.

---

## Encapsulation Has Two Parts

### Part 1

Data + Methods Together

```java
class Car {

   String brand;

   void start(){}
}
```

---

### Part 2

Data Security

Protect important data.

---

# Real World Example

## Odometer

You cannot directly do:

```text
15000 km
↓
5000 km
```

because it is protected.

---

## Speed

Wrong:

```java
car.speed = 500;
```

Correct:

```java
car.accelerate();
```

---

# Access Modifiers

```text
Access Control
│
├── Public
├── Private
└── Protected
```

---

## Public

Accessible everywhere.

```java
public String brand;
```

---

## Private

Accessible only inside class.

```java
private int speed;
```

---

## Protected

Accessible in child classes.

```java
protected int speed;
```

---

# Encapsulation Example

```java
class SportsCar {

    private int speed;

    public void accelerate() {
        speed += 20;
    }
}
```

---

## Wrong Usage

```java
myCar.speed = 500;
```

❌ Compile Time Error

---

## Correct Usage

```java
myCar.accelerate();
```

✅ Controlled Access

---

# Getters and Setters

---

## Getter

Used to Read Data

```java
public int getSpeed() {
    return speed;
}
```

---

## Setter

Used to Update Data

```java
public void setTyre(String tyre) {
    this.tyre = tyre;
}
```

---

# Why Setters Are Useful?

Validation

```java
public void setTyre(String tyre){

    if(isValidTyre(tyre)){
        this.tyre = tyre;
    }
}
```

Benefits:

✅ Validation

✅ Security

✅ Flexibility

✅ Future changes

---

# ⚡ Abstraction vs Encapsulation

| Abstraction                               | Encapsulation                   |
| ----------------------------------------- | ------------------------------- |
| Hides Complexity                          | Protects Data                   |
| Focus on What                             | Focus on How Secure             |
| Interface Level                           | Implementation Level            |
| User Convenience                          | Data Safety                     |
| Achieved using Abstract Class / Interface | Achieved using Access Modifiers |

---

## Easy Interview Answer

### Abstraction

```text
Hide unnecessary details.
Show only what is required.
```

### Encapsulation

```text
Wrap data and methods together.
Protect sensitive data.
```

---

# 🎤 Interview Questions

### Q1. Why OOP was introduced?

Answer:

```text
Real World Modeling
Reusability
Scalability
Data Security
Maintainability
```

---

### Q2. Difference between Class and Object?

Class → Blueprint

Object → Instance

---

### Q3. What is Abstraction?

Hide implementation details and expose only necessary functionality.

---

### Q4. What is Encapsulation?

Wrapping data and methods together and securing sensitive data.

---

### Q5. Difference between Data Hiding and Data Security?

Data Hiding → Abstraction

Data Security → Encapsulation

---

### Q6. Why use Getters and Setters?

```text
Validation
Control
Security
Flexibility
```

---

# 📝 One Page Revision Sheet

```text
OOP =
Real World Modeling

Object =
Characteristics + Behaviors

Class =
Blueprint

Object =
Instance

Abstraction =
Hide Complexity

Encapsulation =
Data + Methods Together
+
Data Security

Access Modifiers =
Public
Private
Protected

Getter =
Read Data

Setter =
Update Data

Benefits of OOP =
Reusability
Scalability
Security
Maintainability
```

---

# 🎯 Final Takeaway

Think of OOP as:

```text
Real World
     ↓
Objects
     ↓
Classes
     ↓
Interactions
     ↓
Software
```


# 1️⃣ Abstraction

---

## 📖 Definition

> Abstraction means hiding implementation details and exposing only the necessary functionality to the user.

---

## 🧠 Mental Model

### Restaurant Example

```text
Customer
   │
   ▼
Places Order
   │
   ▼
Kitchen (Hidden)
```

Customer knows:

✅ Menu

✅ Price

✅ Food

Customer doesn't know:

❌ Recipe

❌ Cooking Process

❌ Ingredients Flow

This is Abstraction.

---

## 🚗 Car Example

You can:

* Start Car
* Brake
* Accelerate
* Shift Gear

You don't know:

* Fuel Injection Logic
* Gearbox Internals
* Engine Combustion

Still car works.

---

## 📐 UML Diagram

```text
+--------------------+
|       Car          |
+--------------------+
| brand : String     |
| model : String     |
+--------------------+
| startEngine()      |
| shiftGear()        |
| accelerate()       |
| brake()            |
+--------------------+
```

---

## ☕ Java Template

```java
public abstract class Car {

    public abstract void startEngine();

    public abstract void shiftGear(int gear);

    public abstract void accelerate();

    public abstract void brake();

    public abstract void stopEngine();
}
```

### Concrete Implementation

```java
public class SportsCar extends Car {

    @Override
    public void startEngine() {
        System.out.println("Engine Started");
    }

    @Override
    public void accelerate() {
        System.out.println("Accelerating...");
    }

    @Override
    public void brake() {
        System.out.println("Braking...");
    }

    @Override
    public void stopEngine() {
        System.out.println("Engine Stopped");
    }

    @Override
    public void shiftGear(int gear) {
        System.out.println("Gear : " + gear);
    }
}
```

---

## 🏢 Spring Boot Example

Payment Gateway System

```java
public interface PaymentProcessor {

    void processPayment(double amount);
}
```

```java
public class RazorpayProcessor
        implements PaymentProcessor {

    @Override
    public void processPayment(double amount) {
        System.out.println("Razorpay Payment");
    }
}
```

```java
public class StripeProcessor
        implements PaymentProcessor {

    @Override
    public void processPayment(double amount) {
        System.out.println("Stripe Payment");
    }
}
```

Controller never knows internal implementation.

This is Abstraction.

---

## 🎤 Interview Answer

"Abstraction is the process of hiding implementation details and exposing only required functionality. It reduces complexity and improves maintainability."

---

## 🚨 Common Mistake

❌ Abstraction = Private Variables

✅ Abstraction = Hiding Complexity

---

## 🔥 LLD Perspective

Without Abstraction

```text
OrderService
 ├─ Razorpay Logic
 ├─ Stripe Logic
 ├─ Paypal Logic
 └─ Bank Logic
```

Tightly Coupled

---

With Abstraction

```text
PaymentProcessor
        ▲
        │
 ┌──────┼──────┐
 │      │      │
 ▼      ▼      ▼

Razorpay
Stripe
Paypal
```

Loosely Coupled

Open/Closed Principle Followed

---

## 🎯 Homework

Create:

```java
abstract class Notification {

}
```

Implement:

* EmailNotification
* SMSNotification
* PushNotification

Apply Abstraction.

---

## ⚡ Revision Sheet

```text
Abstraction

Hide HOW
Show WHAT

Examples:

Car
ATM
TV Remote
Payment Gateway
Java Interface
Abstract Class
```


If you understand:

✔ Object

✔ Class

✔ Abstraction

✔ Encapsulation

Then Inheritance and Polymorphism become much easier.
