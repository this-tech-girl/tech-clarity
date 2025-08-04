# 💥 “Why your code keeps breaking?”  
It’s probably not SOLID enough.

---

## ✅ What is SOLID? (Explain like I’m 5)

📘 **SOLID = 5 rules to write better code**

- **S** → Single Responsibility Principle  
- **O** → Open/Closed Principle  
- **L** → Liskov Substitution Principle  
- **I** → Interface Segregation Principle  
- **D** → Dependency Inversion Principle

They help your code stay clean, change-friendly, and testable 🧼

---

## ✅ What does it do & why it matters

❌ **Without SOLID**  
- Small changes break everything  
- Hard to test, scale, and debug  
- New devs avoid your code like a haunted house 👻

✅ **With SOLID**  
- Each class has a clear purpose  
- You can add features without rewriting old code  
- Code becomes a team player — not a time bomb 💣

---

## ✅ Real-Life Analogy

🏗️ Imagine building a LEGO house  

- 🧱 **S**: Each block has one job (a door is just a door)  
- 🧩 **O**: Want to expand? Add more blocks, don’t touch old ones  
- 🔁 **L**: Replace a block with a similar one — it still fits  
- 🎚️ **I**: Don’t give all features to every block  
- 🔌 **D**: Use connectors — not glue — so things are swappable

👉 **SOLID = Your code becomes modular, reusable, and fun to build.**

---

## ✅ Java Code Examples

### S — Single Responsibility Principle

```java
public class Invoice {
    public double calculateTotal() {
        // calculation logic
        return 0.0;
    }
}

public class InvoicePrinter {
    public void print(Invoice invoice) {
        // printing logic
    }
}
```

---

### O — Open/Closed Principle

```java
public interface Discount {
    double apply(double price);
}

public class NewCustomerDiscount implements Discount {
    public double apply(double price) {
        return price * 0.90;
    }
}

public class BlackFridayDiscount implements Discount {
    public double apply(double price) {
        return price * 0.75;
    }
}
```

> Add new discount types without modifying existing ones ✅

---

### L — Liskov Substitution Principle

```java
public class Bird {
    public void fly() {
        System.out.println("Bird is flying");
    }
}

public class Sparrow extends Bird {}

public class Ostrich extends Bird {
    @Override
    public void fly() {
        throw new UnsupportedOperationException("Ostrich can't fly!");
    }
}
```

❌ Violates Liskov — Ostrich shouldn’t extend Bird if it can’t behave like one  
✅ Fix: Create a `FlightBird` and `NonFlightBird` hierarchy instead

---

### I — Interface Segregation Principle

```java
public interface Printer {
    void print();
}

public interface Scanner {
    void scan();
}

public class AllInOnePrinter implements Printer, Scanner {
    public void print() { /*...*/ }
    public void scan() { /*...*/ }
}

public class SimplePrinter implements Printer {
    public void print() { /*...*/ }
}
```

✅ Don’t force classes to implement more than they need.

---

### D — Dependency Inversion Principle

```java
public interface Keyboard {
    void type();
}

public class WiredKeyboard implements Keyboard {
    public void type() {
        System.out.println("Typing with wired keyboard");
    }
}

public class WirelessKeyboard implements Keyboard {
    public void type() {
        System.out.println("Typing with wireless keyboard");
    }
}

public class Computer {
    private final Keyboard keyboard;

    public Computer(Keyboard keyboard) {
        this.keyboard = keyboard;
    }

    public void typeSomething() {
        keyboard.type();
    }
}
```

✅ High-level module `Computer` depends on abstraction `Keyboard`, not on concrete implementation.

---

## 🧠 Summary

**SOLID helps you build clean, flexible, bug-resistant code.**  
Each principle solves a real-world problem developers face when working with large systems.

---

## Follow me for more such content at @this.tech.girl 📩
