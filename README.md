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

- `func (file *File) Write(b []byte) (n int, err error)`

### Named result parameters

- Named result parameters are initialized to the zero values when the function begins.

- A return statement with no arguments returns, also known as unadorned return statement, the current values of the result parameters.

### Defer

- Defferred function calls are executed immediately before the enclosing function returns

- The arguments of a defer function is evaluated immediately, i.e. any variables of the enclosing scope will have the values when the `defer` function is called, when the deferrd functions are executed.

```go

func foo() {
    i := 1

    defer fmt.Println(i)

    i := 10
}

# print 1 instead of 10

```

- Deferred functions are called in LIFO order

- Deferring a call to a function such as Close has two advantages. First, it guarantees that you will never forget to close the file, a mistake that's easy to make if you later edit the function to add a new return path. Second, it means that the close sits near the open, which is much clearer than placing it at the end of the function. - I find these are not convincing.

- TODO: For programmers accustomed to block-level resource management from other languages, defer may seem peculiar, but its most interesting and powerful applications come precisely from the fact that it's not block-based but function-based. In the section on panic and recover we'll see another example of its possibilities.

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

- This is a pecularity: When the value is addressable, the language takes care of the common case of invoking a pointer method on a value by inserting the address operator automatically.

## Interfaces and other types

### Interfaces

### Conversions

### Interface conversions and type assertions

### Generality

### Interfaces and methods

## The blank identifier

- `_` is known as the blank identifier

### The blank identifier in multiple assignment

- When a value is not used, e.g.

```go
for _, value := range array {
    // the index is not used
}
```

### Unused imports and variables

- Use `_` to silence unused imports

```go
import (
    "fmt"
)

var _ = fmt.Printf

_ = fd

```

### Import for side effect

- For example, import a database driver

```go
import (
    _ "github.com/go-sql-driver/mysql"
)
```

### Interface checks

- TODO: to be distilled after interfaces and type conversions

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
