# Cache-Lab

This repository provides an overview of a project designed for a class, where I implemented a simulated **Least Recently Used (LRU)** cache. The project focuses on understanding cache memory mechanisms by tracking hits, misses, evictions, and other cache-related flags using a structured approach.

> **Note:** The exact implementation code is not provided here, but if you're interested in discussing the project or seeing specific details, feel free to reach out to **anirudhm@andrew.cmu.edu**!

---

## Project Overview

Caches are critical for efficient memory access in computer systems. This project simulates an LRU cache, offering insights into how cache lines are managed and how various operations influence cache performance.

---

## Key Features

### Input Configuration
The simulation is driven by user-specified flags:

- **`s`**: Number of set index bits, which determines the number of cache sets (`2^s` sets).
- **`b`**: Number of block offset bits, specifying the size of each cache block (`2^b` bytes).
- **`e`**: Number of lines per set (associativity).
- **`t`**: Number of tag bits, representing the portion of the memory address used to identify unique blocks.

These parameters define the structure and behavior of the cache.

---

### Cache Operations
The simulation processes a binary string representing a memory address. The address is parsed to determine:

- **Set index**: Identifies the cache set to access.
- **Tag**: Used to verify if the data is already in the cache.
- **Block offset**: Indicates the specific byte within a block.

Based on this breakdown, the simulator tracks:
- **Hits**: When requested data is found in the cache.
- **Misses**: When requested data is not found, requiring a memory fetch.
- **Evictions**: When an existing cache line is replaced due to associativity constraints.

---

### Cache Line Representation
Each cache line is modeled as a structure containing:

- **Dirty bit**: Indicates whether the block was modified.
- **Valid bit**: Specifies if the cache line contains valid data.
- **Tag**: Identifies the memory block.

The cache itself is stored as a **2-D array** of these cache line structures:
- **Rows** represent sets.
- **Columns** represent lines within each set.

---

### Tracking Mechanism
A secondary structure is used to log the status of:
- Hits
- Misses
- Evictions

This provides a detailed analysis of cache performance.

---

## Implementation Details

- The project relies on **bit manipulation** and **logical operations** to parse memory addresses and simulate cache behavior.
- **LRU replacement logic** ensures that the least recently used cache line is evicted when a new line must be inserted.
- The simulation provides insights into cache efficiency by analyzing how different configurations (values of `s`, `b`, `e`, and `t`) impact performance.

---

## Acknowledgements

A special thanks to the instructors of my Computer Systems course for their invaluable guidance on this project.
