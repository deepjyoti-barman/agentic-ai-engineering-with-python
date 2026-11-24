# Python Introduction

## What is Python?

Python is a **high-level, general-purpose, multi-paradigm** programming language. It was first released in **1991** and created by **Guido van Rossum**.

- **High-level:** it hides low-level machine details (registers, memory addresses) so you can focus on the logic.
- **General-purpose:** it can be used to build many kinds of software, not just one type.
- **Multi-paradigm:** it supports several styles of programming, described below.

## 1. Programming Paradigms in Python

A **paradigm** is a style or approach to organising code. Python supports the following:

```txt
Python paradigms
├── Procedural programming   : code as a sequence of steps (functions)
├── Structured programming   : code with clear control flow (if / for / while)
├── Object-oriented (OOP)    : code organised as objects that hold data and behaviour
└── Functional programming   : code built from functions that avoid changing data
```

### A. Object-Oriented Programming (OOP)

Code is organised into **classes** (blueprints) and **objects** (instances of those blueprints) that combine data and behaviour.

```python
class Dog:
    def __init__(self, name):
        self.name = name

    def bark(self):
        print(f"{self.name} says: Woof!")

dog = Dog("Tommy")
dog.bark()   # Tommy says: Woof!
```

### B. Functional Programming

Code is built from **functions** that take inputs and return outputs without changing existing data.

```python
numbers = [1, 2, 3, 4]
squares = list(map(lambda n: n * n, numbers))
print(squares)   # [1, 4, 9, 16]
```

### C. Structured Programming

Code relies mainly on **sequence, selection (if/else), and repetition (loops)** for control flow, which keeps it easy to follow.

```python
for age in [15, 20]:
    if age >= 18:
        print("Adult")
    else:
        print("Minor")
```

### D. Procedural Programming

Code is divided into **procedures (functions)** that are called to perform tasks. It is closely related to structured programming, and in Python the two are often used together.

```python
def add(a, b):
    return a + b

print(add(2, 3))   # 5
```

## 2. High-Level Language

Python is a **high-level language**. Its code reads close to plain English and is much simpler than C or C++.

**Hello, World! in C:**

```c
#include <stdio.h>

int main(void) {
    printf("Hello, World!\n");
    return 0;
}
```

**Hello, World! in Python:**

```python
print("Hello, World!")
```

The Python version needs no headers, no `main` function, and no type declarations.

## 3. General-Purpose Language

Python can be used to build many types of applications:

| Application type | Example                                |
| ---------------- | -------------------------------------- |
| Calculator       | Desktop or command-line calculator     |
| Web applications | Django, Flask                          |
| APIs             | FastAPI                                |
| Games            | Pygame                                 |
| AI applications  | Chatbots, machine learning, agents     |
| Automation       | Scripts that rename or process files   |

## 4. Why Python Is Popular

- **Beginner-friendly:** its simple syntax makes it one of the easiest languages to learn and use.
- **Large community:** millions of developers share tutorials, answers, and open-source projects.
- **Rich libraries:** a large standard library and hundreds of thousands of third-party packages on PyPI are available for almost any task.
- **Strong in AI:** major AI and machine learning libraries, such as TensorFlow, PyTorch, and scikit-learn, have Python as their main interface.
