# Memory Unit in a Computer

## 1. The Big Picture: Memory Hierarchy

A computer needs to store data and feed it to the processor. No single device is both very fast and very cheap, so computers use several memory levels:

```txt
        Fastest, smallest, most expensive
   ┌─────────────────────────────────────────┐
   │  CPU Registers                          │  bytes
   ├─────────────────────────────────────────┤
   │  Cache (L1, L2, L3)                     │  KBs to MBs
   ├─────────────────────────────────────────┤
   │  RAM (Main Memory)                      │  GBs
   ├─────────────────────────────────────────┤
   │  HDD (Secondary Memory)                 │  TBs
   └─────────────────────────────────────────┘
        Slowest, largest, least expensive
```

## 2. Processor (CPU)

The processor, also called the microprocessor or CPU, is the brain of the computer. It is built with **semiconductor technology** and is very fast. It executes instructions, but it can only work on data that is already available to it.

## 3. Hard Disk Drive (HDD)

The **Hard Disk Drive (HDD)** is the computer's permanent storage. It:

- supplies the processor with the data it needs, and
- stores the output when it must be kept.

## 4. The Bus

A **bus** is a set of wires that carries information between units of the system.

```txt
   HDD  ◄────►  Bus  ◄────►  Processor
```

Data moves from the HDD to the processor, and results move back, over the bus.

## 5. Why the HDD Is Slow

An HDD is an **electro-mechanical device**. It uses **magnetic technology**: a spinning magnetic disk and a moving read/write head. Moving parts take time, so the HDD is much slower than the processor.

## 6. Speed Mismatch

The processor is far faster than the HDD. If the processor had to wait for the HDD for every piece of data, most of its time would be spent idle. This **speed mismatch** reduces the efficiency of the whole system.

```txt
Processor:  ██████████████████████████  (very fast)
HDD:        ██                          (much slower)
            └── processor waits here ──┘
```

## 7. Disadvantages of the HDD

- **Slow** compared to the processor and other internal units
- **Bulky** because the drive needs physical space for its spinning disks and moving head
- **Noisy** because of spinning disks and moving heads

## 8. Random Access Memory (RAM)

**RAM** is built with **semiconductor technology**, like the processor. It is much faster than the HDD, which reduces the speed mismatch. It is the **temporary working memory** where programs and data are kept while they are in use.

## 9. Advantages of RAM

- **Fast:** much faster than the HDD
- **Compact:** small in size
- **Quiet:** no moving parts, so no noise

## 10. Disadvantages of RAM

- **Volatile:** it needs continuous power. If the power goes off, even for a fraction of a second, all data in RAM is lost.
- **Expensive:** it costs more per GB than an HDD.

## 11. Advantages of the HDD

- **Non-volatile:** data is kept even when the power is off.
- **Inexpensive:** it costs less per GB than RAM.

## 12. How the Three Units Work Together

```txt
   HDD  ◄──── Bus ────►  RAM  ◄──── Bus ────►  Processor
  (stores)            (works)               (processes)
```

Data is always moved through RAM. The processor does not read files directly from the HDD.

- **Loading:** copying data from HDD to RAM.
  _Example:_ opening a document copies it from the HDD into RAM.
- **Saving:** copying data from RAM to HDD.
  _Example:_ clicking _Save_ writes the document from RAM to the HDD.

## 13. Units of Storage

| Location     | Unit of storage           | Description                                                         | Example           |
| ------------ | ------------------------- | ------------------------------------------------------------------- | ----------------- |
| **HDD**      | **File**                  | A named collection of data stored on the disk                       | `report.docx`     |
| **RAM**      | **Byte**                  | Each byte has its own address, and the processor reads or writes it | `1 byte = 8 bits` |
| **Register** | **Small fixed-size slot** | Tiny storage inside the CPU where the processor does its work       | `EAX` (32 bits)   |

## 14. Main Memory and Secondary Memory

- **RAM** is called **Main Memory**, because the processor works with it directly.
- **HDD** is called **Secondary Memory**, because it is used for long-term storage and is not accessed directly by the processor.

## 15. Factors That Affect Performance

Speed and capacity are two different things:

- **Speed of RAM:** how quickly data moves between RAM and the processor. Faster RAM means the processor gets its data sooner.
- **Capacity of RAM:** how much data RAM can hold at once. More capacity lets more applications run together. When RAM is full, the computer slows down or "hangs" because it must move data to and from the HDD.

> Adding RAM does not make the processor itself faster. It helps the computer avoid waiting for the HDD.

## 16. Cache Memory

**Cache** is a very small, very fast memory that sits between the processor and RAM.

```txt
   CPU  ◄────►  Cache  ◄────►  RAM  ◄────►  HDD
```

- **Size:** very small, from KBs (L1) to tens of MBs (L3).
- **Control:** you cannot store anything in the cache manually. The hardware manages it automatically.
- **Purpose:** it keeps the data and instructions the processor uses most often.

**Example:**

```txt
1st time you open a video editor:   data comes from HDD ──► RAM ──► CPU
Later, while still using it:        frequently used data is copied into cache
                                    CPU ──► Cache   (faster, no RAM access needed)
```

Because the cache is small, the processor can find the needed data there very quickly. Data that is used again and again is kept in the cache, so the processor avoids the slower RAM.
