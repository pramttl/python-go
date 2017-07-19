# Python -> Go: Reference Document

Note: **Work In Progress**

The goal of this repository is to draw some random language/syntax similarities betwen Python and Go to help get myself and other Python developers get familar with Go. This package does not discuss performance, etc. In each of these cases, the first example is Python example and the second example is the Go example.

### Typing

Python uses dynamic types. Go is a strongly typed language.

### Unused Variables

Python will not complain about unused variables. Go is strict in that if a variable is defined but not used then it will result in a complie time error.


### Running / Compiling


```
$ python helloworld.py
```

```
$ go run helloworld.py
```

### Strings

Go does not allow single-quite strings unlike Python but allows double quite strings. Since in most of the programming languages double quotes string is the standard it's wise to get used to them.

```
s = "Hello"
```

```
s := "Hello"
```

#### Printing

```
print("Hello")
```

```
fmt.Println("Hello")
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
slice = nums[3:5]
# [4,5]
```

```go
slice := nums[3:5]
// [4,5]
```

### Hashmaps

#### Adding keys
```
d = {}
d["key"] = "value"
```

```
d := make(map[string] string)
d["key"] = "value"
```

#### Deleting keys

```
del d["key"]
```

```
delete(d, "key")
```