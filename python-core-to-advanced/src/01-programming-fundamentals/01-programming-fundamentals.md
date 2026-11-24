# Programming Fundamentals

## 1. Components of a Computer

A computer is a set of hardware parts working together:

| Component                         | Role                                               | Example                               |
| --------------------------------- | -------------------------------------------------- | ------------------------------------- |
| **CPU** (Central Processing Unit) | Executes instructions and performs calculations    | Intel Core, AMD Ryzen, Apple M-series |
| **Memory (RAM)**                  | Temporarily holds programs and data while they run | 16 GB RAM                             |
| **Storage**                       | Keeps data permanently                             | SSD, HDD                              |
| **Input devices**                 | Send data into the computer                        | Keyboard, mouse                       |
| **Output devices**                | Show results from the computer                     | Monitor, speaker                      |
| **Motherboard**                   | Connects all components together                   | Main circuit board                    |

```txt
 Input devices ──► CPU ◄──► RAM
 (keyboard)         │
                    ▼
 Output devices ◄── Storage (SSD/HDD)
 (monitor)
```

## 2. The CPU: The Brain of the Computer

The CPU is a **semiconductor device**. A semiconductor is a material (usually silicon) whose electrical conductivity can be controlled, which makes it possible to build switches that turn on and off billions of times per second.

The basic building block of the CPU is the **transistor**.

## 3. Transistor Types: NPN and PNP

A transistor is a tiny electronic switch with three terminals: **Base**, **Collector**, and **Emitter**. The two common types are:

| Type    | Turns ON when...                                           | Common use                               |
| ------- | ---------------------------------------------------------- | ---------------------------------------- |
| **NPN** | Base is given a positive voltage (relative to the Emitter) | Switching a load to ground               |
| **PNP** | Base is pulled lower than the Emitter                      | Switching a load from the supply voltage |

**Example:** A transistor works like a light switch controlled by a small signal.

```txt
   NPN transistor as a switch

   Base = HIGH (1)  ──►  Transistor ON   ──►  Current flows  ──►  LED glows
   Base = LOW  (0)  ──►  Transistor OFF  ──►  No current     ──►  LED off
```

## 4. Binary: Low Voltage (0) and High Voltage (1)

A CPU understands only two states, represented by two voltage levels:

| Voltage         | Binary digit (bit) | Meaning |
| --------------- | ------------------ | ------- |
| **0 V** (low)   | `0`                | OFF     |
| **+5 V** (high) | `1`                | ON      |

> In modern chips the exact voltage is lower (for example, about 1 V), but the idea is the same: two distinct levels, one for `0` and one for `1`.

**Example:** The number 5 stored as bits:

```txt
Decimal:  5
Binary:   0 0 0 0 0 1 0 1
          │ │ │ │ │ │ │ │
          ▼ ▼ ▼ ▼ ▼ ▼ ▼ ▼
Voltage:  0V 0V 0V 0V 0V 5V 0V 5V   (each bit is one voltage level)
```

## 5. The Processor Is Dumb Without Instructions

The processor cannot think or decide on its own. It only follows **instructions** given to it. Its input must be in a form it understands: **Machine Level Language (MLL)**.

## 6. Machine Level Language (MLL)

MLL is the language made only of `0`s and `1`s. Every instruction the CPU can execute has a unique binary code.

**Example** (x86 processor, shown in hexadecimal and binary):

```txt
Instruction: put the number 5 into register AX
Machine code: B8 05 00
Binary:       10111000 00000101 00000000
```

Writing programs this way is difficult for humans, and mistakes are easy to make.

## 7. Program: A Set of Instructions

A **program** is a set of instructions stored together in one place, executed in order by the CPU.

```txt
Program = Instruction 1 + Instruction 2 + Instruction 3 + ...
```

## 8. Why MLL Is Not Human-Friendly

- Humans read words and symbols, not long strings of bits.
- A single wrong bit can break the program.
- Finding and fixing bugs is very slow.

So programmers needed a more readable way to write instructions.

## 9. Assembly Level Language (ALL)

**Assembly Level Language (ALL)** writes each machine instruction as a short word called a **mnemonic**. It is more readable than MLL, but it still maps closely to the CPU's instructions.

```txt
Assembly (ALL)        Machine code (MLL)
MOV AX, 5      ──►    B8 05 00
ADD AX, 3      ──►    05 03 00
```

## 10. Assembler: Converts ALL to MLL

The CPU cannot understand assembly code directly. An **assembler** is system software that converts ALL into MLL.

```txt
  ALL (assembly code)  ──►  [ Assembler ]  ──►  MLL (machine code)  ──►  CPU
```

## 11. High Level Language (HLL)

**High Level Language (HLL)** uses English-like words, symbols, and commands. It is independent of any specific CPU and is easy for humans to read and write.

**Examples:** C, C++, Java, Python etc.

```c
int result = 5 + 3;
printf("%d", result);
```

The same logic in Python:

```python
result = 5 + 3
print(result)
```

## 12. Compiler: Converts HLL to MLL

A **compiler** is system software that translates a whole HLL program into MLL before it runs.

```txt
  HLL (C / C++)         ──►  [ Compiler ]  ──►  MLL (machine code)  ──►  CPU
```

> Java compiles to _bytecode_, which the Java Virtual Machine (JVM) then runs. Python uses an interpreter or a bytecode compiler with a virtual machine, so the pipeline differs slightly, but the goal is the same: turn human-readable code into instructions the CPU can execute.

## Summary: From Code to Execution

```txt
 Human writes         Translator              CPU executes
 ─────────────        ──────────────          ─────────────
 HLL (C, C++)    ──►  Compiler        ──►     MLL (0s and 1s)
 ALL (Assembly)  ──►  Assembler       ──►     MLL (0s and 1s)
```
