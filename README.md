# Electronic-Arts-Sports-College-Football-Game

# 🏈 EA College Football – Dynamic Momentum System & Inventory Management Patch

## 📘 Project Summary

This project simulates the real-life experience of being a **Junior Software Engineer at EA Sports**, working on the **College Football game** series. The tasks progress through the **entire software development lifecycle**, including:

1. Proposing a new feature for the game.
2. Designing object-oriented systems using UML class diagrams.
3. Writing modular, header-based C++ code.
4. Debugging and patching issues found in live production.
5. Refactoring legacy code for better performance and maintainability.

This repository contains:
- A **Dynamic Crowd Momentum System** designed to enhance game immersion.
- A **bug-fixed inventory system** that models in-game item transactions for things like merch or boosters.
- Modern **C++ class implementations** using `std::vector` and `std::unique_ptr`.

---

## 🎮 Project Breakdown

### Phase 1: Feature Proposal

We begin by writing a **feature proposal** document for a new gameplay feature in College Football:

> **Feature Name:** Dynamic Crowd Momentum System  
> **Summary:** The feature links in-game crowd intensity and momentum to gameplay pressure, creating a more immersive and strategic environment for players.

#### Core Goals:
- Use color-coded momentum feedback to simulate pressure.
- Have crowd behavior (sound and animation) respond dynamically.
- Introduce momentum-based penalties on audibles, snap counts, and passes.

---

### 🧩 Phase 2: Object-Oriented Design

Next, we model the system using a **UML Class Diagram** with 10+ classes including:
- `MomentumManager`
- `CrowdController`
- `GameplayImpactController`
- `MomentumMeter`
- `MomentumEvent`
- `CrowdAudioController`, etc.

Each class has:
- Well-defined responsibilities (SRP)
- Clear relationships (composition, delegation)
- Public and private members for encapsulation
- Use of design patterns like **Strategy** and **Observer**

---

### 🧠 Phase 3: C++ Header File (`.h`)

We translate the class diagram into a single header file (`MomentumSystem.h`) that defines:
- All classes and method stubs
- Abstract interfaces for extensibility
- Member variable declarations
- Strategic use of forward declarations for modular design

---

### 🔧 Phase 4: C++ Implementation File (`.cpp`)

We then implement the system logic in a separate source file (`MomentumSystem.cpp`), with:
- Definitions of each class method
- Use of polymorphism, composition, and encapsulation
- Functional behavior for audio/visual crowd effects and momentum updates

---

### 🐞 Phase 5: Bug Fix – Yellow Ticket

While the momentum system is under review, a **live bug is discovered** in the College Football inventory system:
> When an item is sold to zero quantity, it remains in the inventory list with a quantity of 0.

This leads to a ticket:
- 📄 **Bugfix Task:** Fully remove items from the inventory when quantity reaches 0.
- 🔍 Investigation reveals a flawed C-style array (`Item* items[20]`) being used.

---

### 🔁 Phase 6: Code Refactoring & Patch

We refactor the inventory system as follows:

| Old Approach                    | New Approach                                  |
|--------------------------------|-----------------------------------------------|
| Fixed-size C-array             | ✅ `std::vector<std::unique_ptr<Item>>`       |
| Manual memory management       | ✅ Automatic cleanup via smart pointers       |
| Static item_count tracking     | ✅ Dynamic `items.size()` check               |
| No item removal on zero stock  | ✅ Full item removal using `vector::erase()`  |

Refactored methods include:
- `add_item()`
- `sell_item()`
- `remove_item()`
- `list_items()`

---

## 🔩 Features Implemented

### 🎯 Dynamic Momentum System
- Crowd intensity tied to game momentum.
- Pressure-based gameplay impacts.
- Scalable design using object-oriented patterns.

### 📦 Inventory System
- Add, sell, and list in-game items.
- Auto-remove items when quantity is 0.
- Fully dynamic, safe memory usage with vectors and smart pointers.

---

## 🛠 How to Run

1. Open the project in your C++ IDE (VS Code, CLion, Visual Studio).
2. Ensure **C++11 or higher** is enabled.
3. Compile and run `main()` from the `.cpp` file.
4. Follow the on-screen menu to test inventory actions.

---

## 📂 File Structure

``

CollegeFootballProject/
├── MomentumSystem.h # Header definitions for momentum classes
├── MomentumSystem.cpp # Full implementation of momentum system
├── InventorySystem.cpp # Refactored item inventory with bug fix
├── README.md # This file

``


---

## 📚 Key C++ Concepts Used

- Object-Oriented Programming (classes, access modifiers)
- Smart Pointers (`std::unique_ptr`)
- Dynamic Containers (`std::vector`)
- Design Patterns (Strategy, Observer)
- Memory safety and resource management
- Code refactoring and bug isolation

---

## ✨ Possible Enhancements

- Add restock or item merge functionality.
- Save/load inventory from file (persistence).
- Add categories/tags for inventory filtering.
- Unit tests for momentum logic or sell behavior.

---

## 👥 Author & Credits

This project simulates work by a **Junior Software Engineer at EA** and was created as part of a learning journey on system design, bug-fixing, and real-world C++ game development.

---

## 🧾 License

This project is intended for educational and training use only. No part of this system is owned by or distributed on behalf of EA Sports or Electronic Arts.


