# Golang Variables

## Overview
A variable in Go is a piece of storage that temporarily holds data for use within your program. Go is a statically typed language, meaning you need to specify the type of a variable when declaring it.

## Variable Declaration with Initialization
When you know the value of a variable at the time of declaration, you can declare and initialize it in one line.

### Example:
```go
package main

import "fmt"

func main() {
	var i int = 10
	var s string = "Canada"

	fmt.Println(i)
	fmt.Println(s)
}
```
Here:
- `i` is an `int` initialized to `10`.
- `s` is a `string` initialized to `"Canada"`.

## Variable Declaration without Initialization
Variables can be declared without initialization. When declared this way, they hold a zero value until assigned.

### Example:
```go
package main

import "fmt"

func main() {
	var i int
	var s string

	i = 10
	s = "Canada"

	fmt.Println(i)
	fmt.Println(s)
}
```
Here, `i` and `s` are declared first and then assigned values later.

## Variable Declaration with Type Inference
Go allows type inference, so you can omit the type if you initialize a variable with a value.

### Example:
```go
package main

import (
	"fmt"
	"reflect"
)

func main() {
	var i = 10
	var s = "Canada"

	fmt.Println(reflect.TypeOf(i)) // int
	fmt.Println(reflect.TypeOf(s)) // string
}
```
Go automatically infers `i` as `int` and `s` as `string`.

## Multiple Variable Declaration
You can declare and initialize multiple variables in one line.

### Example:
```go
package main

import (
	"fmt"
)

func main() {
	var fname, lname string = "John", "Doe"
	m, n, o := 1, 2, 3
	item, price := "Mobile", 2000

	fmt.Println(fname + " " + lname)
	fmt.Println(m + n + o)
	fmt.Println(item, "-", price)
}
```

## Short Variable Declaration
You can use the `:=` operator for a concise variable declaration and initialization.

### Example:
```go
package main

import (
	"fmt"
	"reflect"
)

func main() {
	name := "John Doe"
	fmt.Println(reflect.TypeOf(name)) // string
}
```

## Scope of Variables
The scope of a variable determines where it can be accessed within the code.

### Example:
```go
package main

import (
	"fmt"
)

var s = "Japan"

func main() {
	fmt.Println(s) // Global variable

	x := true // Local variable

	if x {
		y := 1 // Block-scoped variable
		fmt.Println(s)
		fmt.Println(x)
		fmt.Println(y)
	}
}
```

## Zero Value
If a variable is declared without initialization, Go assigns it a default "zero value."

### Example:
```go
package main

import "fmt"

func main() {
	var quantity float32
	var price int16
	var product string
	var inStock bool

	fmt.Println(quantity) // 0
	fmt.Println(price)    // 0
	fmt.Println(product)  // ""
	fmt.Println(inStock)  // false
}
```

## Variable Declaration Block
For better readability, you can group variable declarations into blocks.

### Example:
```go
package main

import "fmt"

var (
	product  = "Mobile"
	quantity = 50
	price    = 50.50
	inStock  = true
)

func main() {
	fmt.Println(quantity)
	fmt.Println(price)
	fmt.Println(product)
	fmt.Println(inStock)
}
```

## Naming Conventions
- A variable name must start with a letter and can contain letters and digits.
- Variable names are case-sensitive (`car`, `Car`, and `CAR` are different).
- Names starting with a capital letter are exported (accessible outside the package).
- Multiple words in a name should follow camelCase, like `empName` or `EmpAddress`.

---

This README covers the basic and advanced features of variables in Go, providing a comprehensive guide with practical examples.