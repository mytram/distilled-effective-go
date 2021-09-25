# Effective Go

## Introduction

### Examples

## Formatting

## Commentary

## Names

### Package names

### Getters

- Omit `Get` from getters, e.g. `o.Owner()` as opposed to `o.GetOwner()`

### Interface names

- By convention, one-method interfaces are named by the method name plus an -er suffix or similar modification, e.g. the `Reader` interface has a method named `Read`.

### MixedCaps

- `MixedCaps` or `mixedCaps`

## Semicolons

- Semicolons are inferred.

- Idiomatic Go programs have semicolons only in places such as for loop clauses, to separate the initializer, condition, and continuation elements.

- They are also necessary to separate multiple statements on a line, should you write code that way.

## Control structures

### If

```go

if x > 0 {
    return y
}

```

### Redeclaration and reassignment

### For

- `range` for array

```go

for index, value := range array {
    // ...
}

```

- `range` for map

```go

for key, value := range map {
    // ...
}
```

- parallel assignment: `i, j = i+1, j-1`

### Switch

### Type switch

## Functions

### Multiple return values

### Named result parameters

### Defer

## Data

### Allocation with new

### Constructors and composite literals

### Allocation with make

### Arrays

### Slices

### Two-dimensional slices

### Maps

### Printing

### Append

## Initialization

### Constants

### Variables

### The init function

## Methods

### Pointers vs. Values

## Interfaces and other types

### Interfaces

### Conversions

### Interface conversions and type assertions

### Generality

### Interfaces and methods

## The blank identifier

### The blank identifier in multiple assignment

### Unused imports and variables

### Import for side effect

### Interface checks

## Embedding

## Concurrency

### Share by communicating

### Goroutines

### Channels

### Channels of channels

### Parallelization

### A leaky buffer

## Errors

### Panic

### Recover

## A web server
