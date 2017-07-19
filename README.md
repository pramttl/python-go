# Python -> Go: Reference README

Note: **Work In Progress**

The goal of this repository is to draw some random language/syntax similarities betwen Python and Go to help get myself and other Python developers get familar with Go. This package does not discuss performance, etc. In each of these cases, the first example is Python example and the second example is the Go example.

### Basic Similarities / Differences

* Use `python helloworld.py` to invoke a python program and `go run helloworld.py` to run a go program.

* Python uses dynamic types. Go is a strongly typed language.

* Python will not complain about unused variables. Go is strict in that if a variable is defined but not used then it will result in a complie time error. Even unused imports will throw an error and the rest of the code will not run.

* Semicolon at the end of lines are optional in both Python and Go.

* Variables need to be declared in Go unless using the `:=` assign equal operator in which Go is lenient for once when the variable is first being assigned. It tries to infer the type of the RHS and associates that data type with the variable name. Python is dynamically typed and the same variable can hold any data type.


### Strings

Go does not allow single-quite strings unlike Python but allows double quite strings. Since in most of the programming languages double quotes string is the standard it's wise to get used to them.

```
string_python = "Hello"
```

```
string_go := "Hello"
```

#### Printing

```
print("Hello from Python")
```

```
fmt.Println("Hello from Go")
```


### Arrays

```
# Python
nums = [1, 2, 3, 4, 5]
```

```
// Go
nums := []float64 {1, 2, 3, 4, 5}
```

#### Slicing

Slicing in Python and Go work the same way.

```python
pyslice = nums[3:5]
# [4,5]
```

```go
goslice := nums[3:5]
// [4,5]
```

### Hashmaps

#### Adding keys
```
# Python
d = {}
d["key"] = "value"
```

```
// Go
d := make(map[string] string)
d["key"] = "value"
```

#### Deleting keys

```
del d["key"]        # Python
```

```
delete(d, "key")    # Go
```

## Advanced

### Module Exports

In Python all in the global objects unless prefixed by an `_` are exported by default. Example: If you have a file `hello.py` that defines functions such as `foo` and `bar`. Then if in another file in the same directory you write, `from hello import *` then it will import `foo` and `bar` from the `hello` package.

In Go, a name is exported only if it begins with a capital letter. That's why `fmt.Println` has a capital `P`.

So, in short, exports are implicit in Python and expicitly done in Go.


### Closures (Differences)

 In Python, if you write a function (inner) within a function (outer) then, inner has read-only access to variables of outer (Read only access to non-local variables unless they are mutable variables which are passed by reference and can get modified.)

```
# Python
def outer():
  x = 1
  def inner():
    print x
  inner()

# outer() -> 1
```

```
# Python
def outer():
  x = 1
  def inner():
    x += 1
    print x
  inner()

# outer() -> UnboundLocalError: local variable 'x' referenced before assignment
```

In Go, inner functions have read-write access to outer functions variables.

```
func outer() {
    n := 1
    inner := func() {
        n += 1
        return
    }
    inner()
    fmt.Println(n)
}

// Run this and you'd see it prints 2
```

## Suggestions

This README is very loosely written, and may contain errors. These are kind of like personal notes, if you have spotted any errors please do let me know via email or by sending a PR.