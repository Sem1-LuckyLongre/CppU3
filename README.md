# 🖥️ Object-Oriented Programming (OOP) Concepts in C++

Welcome to the **Object-Oriented Programming (OOP)** concepts repository in C++! This guide aims to explain fundamental OOP concepts in-depth, with easy-to-understand examples, and a touch of fun! 🎉

In this repository, you’ll find detailed explanations and C++ code examples for the following core OOP principles:

- **Abstraction**  
- **Encapsulation**  
- **Class Creation & Objects**  
- **Access Modifiers**  
- **Constructors & Destructors**  
- **Inheritance**  
- **Polymorphism**  
- **Template Functions & Classes**

---

## Table of Contents

1. [🧠 Abstraction](#abstraction)
2. [🔒 Encapsulation](#encapsulation)
3. [🏗️ Class Creation & Objects](#class-creation--objects)
4. [🔑 Access Modifiers](#access-modifiers)
5. [🔧 Constructors & Destructors](#constructors--destructors)
6. [👨‍👩‍👧‍👦 Inheritance](#inheritance)
7. [🌀 Polymorphism](#polymorphism)
8. [🛠️ Template Functions & Classes](#template-functions--classes)

---

## 🧠 1. Abstraction

**Abstraction** is the concept of hiding the complex reality and only exposing the necessary details to the user. It allows users to focus on what an object does, without worrying about how it does it.

Think of it like driving a car 🚗: You press the gas pedal to accelerate without needing to know how the engine works under the hood.

### Example:

```cpp
class Car {
public:
    void accelerate() {
        cout << "Car is accelerating." << endl; // Simplified operation exposed to user
    }
};
```

In the example above, the car's internal mechanisms are hidden, and only the **accelerate** method is exposed, keeping the implementation simple for the user.

---

## 🔒 2. Encapsulation

**Encapsulation** involves grouping related data and methods into a single unit called a class and restricting access to some of the object's components. This keeps the object safe from unwanted changes and helps manage complexity.

### Example:

```cpp
class BankAccount {
private:
    double balance; // The balance is encapsulated within the class

public:
    void deposit(double amount) {
        balance += amount; // Modify balance safely through a method
    }

    double getBalance() {
        return balance; // Access balance through a method
    }
};
```

🔒 **Why encapsulation?**  
- It helps protect the internal state of the object (the `balance` in this case) by restricting direct access to it.
- Data is modified only in controlled ways (e.g., through `deposit()`).

---

## 🏗️ 3. Class Creation & Objects

A **class** is a blueprint for creating objects. Objects are instances of classes and can hold data and methods. It’s like a cookie-cutter (class) that makes cookies (objects) of the same shape but with different properties.

### Example:

```cpp
class Dog {
public:
    string name;
    int age;

    void bark() {
        cout << name << " is barking!" << endl;
    }
};

Dog myDog; // Creating an object of type Dog
myDog.name = "Rex";
myDog.age = 3;
myDog.bark(); // Output: Rex is barking!
```

🦴 **Objects** are individual instances created from the `Dog` class, and each object has its own `name` and `age`.

---

## 🔑 4. Access Modifiers

Access modifiers control the visibility and accessibility of class members (attributes and methods). C++ offers three main modifiers: `public`, `private`, and `protected`.

- **Public**: Members are accessible from anywhere.
- **Private**: Members are accessible only within the class.
- **Protected**: Members are accessible within the class and its derived classes.

### Example:

```cpp
class Example {
private:
    int secret; // Accessible only inside the class

public:
    void setSecret(int value) {
        secret = value; // Access and modify secret inside the class
    }

    int getSecret() {
        return secret; // Return the value of secret safely
    }
};
```

🔑 **Key takeaway:** Using `private` and `public`, you can protect the internal workings of the class and provide controlled access to its data.

---

## 🔧 5. Constructors & Destructors

- **Constructors** are special functions that initialize an object when it's created.
- **Destructors** are special functions called when an object is destroyed, typically to clean up resources.

### Constructor Example:

```cpp
class Book {
public:
    string title;
    int pages;

    // Constructor to initialize values when object is created
    Book(string t, int p) {
        title = t;
        pages = p;
    }
};
```

### Destructor Example:

```cpp
class Book {
public:
    string title;

    Book(string t) {
        title = t;
    }

    // Destructor
    ~Book() {
        cout << "Destroying " << title << endl; // Clean up resources when the object is destroyed
    }
};
```

🔧 **Constructors** initialize objects, while **destructors** clean up when objects are no longer needed.  

---

## 👨‍👩‍👧‍👦 6. Inheritance

**Inheritance** allows a class (child or subclass) to inherit properties and methods from another class (parent or base class). It’s like having a child who inherits traits from their parents.

### Example:

```cpp
class Animal {
public:
    void eat() {
        cout << "Eating..." << endl; // Base class method
    }
};

class Dog : public Animal { // Dog inherits from Animal
public:
    void bark() {
        cout << "Barking..." << endl; // Dog-specific method
    }
};
```

🐶 **Inheritance in action**:  
`Dog` inherits the `eat()` method from `Animal`, so `Dog` objects can `eat()` without needing to define this method themselves.

---

## 🌀 7. Polymorphism

**Polymorphism** allows methods to take different forms based on the object type. This is useful when you want to use a single interface for multiple object types.

### Example:

```cpp
class Animal {
public:
    virtual void sound() {
        cout << "Animal sound" << endl;
    }
};

class Dog : public Animal {
public:
    void sound() override {
        cout << "Bark" << endl;
    }
};

class Cat : public Animal {
public:
    void sound() override {
        cout << "Meow" << endl;
    }
};

int main() {
    Animal* animal;

    Dog dog;
    Cat cat;

    animal = &dog;
    animal->sound();  // Output: Bark

    animal = &cat;
    animal->sound();  // Output: Meow
}
```

🌀 **Polymorphism in action**:  
Even though we treat both `Dog` and `Cat` as `Animal` pointers, their `sound()` method behaves differently based on the actual object type. This is a great way to write flexible and extensible code!

---

## 🛠️ 8. Template Functions & Classes

**Templates** allow you to write functions and classes that can operate on any data type. It's like creating a generic tool that works with any material (data type).

### Template Function Example:

```cpp
template <typename T>
T add(T a, T b) {
    return a + b;
}
```

### Template Class Example:

```cpp
template <typename T>
class Box {
private:
    T value;

public:
    void setValue(T v) {
        value = v;
    }

    T getValue() {
        return value;
    }
};
```

🛠️ **Template magic**:  
Templates make your code **generic** and **reusable** for different data types, reducing redundancy and enhancing flexibility.

---

## Conclusion

🎉 Congratulations! You’ve now learned the core principles of **Object-Oriented Programming (OOP)** in C++:

- **Abstraction**: Hide the complexity, show only necessary details.
- **Encapsulation**: Keep data safe and accessible only through controlled methods.
- **Class Creation & Objects**: Create blueprints (classes) and instances (objects).
- **Access Modifiers**: Control access to class members.
- **Constructors & Destructors**: Manage initialization and cleanup.
- **Inheritance**: Reuse and extend functionality from parent classes.
- **Polymorphism**: Use the same method to work with different object types.
- **Template Functions & Classes**: Write reusable code for any data type.

By understanding and applying these concepts, you will be able to write more modular, maintainable, and reusable C++ code. Happy coding! 🚀
