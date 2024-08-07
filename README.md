# HashMap Implementation in C++

This repository contains a custom implementation of a HashMap using separate chaining in C++. The HashMap is implemented as a templated class allowing it to store values of any type.

## Overview

The HashMap implementation includes:
- Basic HashMap operations: `insert`, `getValue`, `remove`
- Dynamic resizing with rehashing when the load factor exceeds 0.7
- Separate chaining to handle collisions

## Features

- **Hash Function**: Implements a hash function to distribute keys across the hash table.
- **Rehashing**: Automatically resizes the table when the load factor exceeds 0.7.
- **Collision Handling**: Uses separate chaining (linked lists) to handle hash collisions.

## Files

- `random.cpp`: Contains the implementation of the HashMap, including the `MapNode` and `MyMap` classes. It also includes a `main` function demonstrating usage with different data types (`int`, `string`, `double`).

## How to Compile and Run

To compile and run the code, follow these steps:

1. **Compile**: Use a C++ compiler like `g++` to compile the source file.
    ```bash
    g++ random.cpp -o hashmap
    ```

2. **Run**: Execute the compiled program.
    ```bash
    ./hashmap
    ```

## Example Usage

The `main` function in `random.cpp` demonstrates the usage of the `MyMap` class with different types:

- **Integer Values**:
    ```cpp
    MyMap<int> mp;
    mp.insert("abc1", 10);
    cout << mp.getValue("abc1") << endl;
    ```

- **String Values**:
    ```cpp
    MyMap<string> mps;
    mps.insert("abc1", "value1");
    cout << mps.getValue("abc1") << endl;
    ```

- **Double Values**:
    ```cpp
    MyMap<double> mpd;
    mpd.insert("key1", 3.14);
    cout << mpd.getValue("key1") << endl;
    ```

## Detailed Description

### `MapNode` Class

- Represents each node in the linked list used for separate chaining.
- Stores the key-value pair and a pointer to the next node.

### `MyMap` Class

- Manages an array of linked lists for collision handling.
- Provides methods to insert, remove, and retrieve values.
- Includes a hash function to map keys to bucket indices.
- Handles resizing with `rehash` when the load factor exceeds a threshold.

## Notes

- Ensure you have a C++ compiler installed to build the project.
- The `rehash` function doubles the size of the table and rehashes all existing entries to balance the load.

