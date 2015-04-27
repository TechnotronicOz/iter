# iter
Slice iteration meta-code for goast. 

If you're looking for something like Underscore or LoDash for Go, this is a start.

Currently supported operations

* `All(func(T) bool) bool`
* `Any(func(T) bool) bool`
* `Count(func(T) bool) bool`
* `Each(func(T))`
* `All(func(T) bool) bool`
* `Extract(func(T) bool) []T`
* `First(func(T) bool) (T, bool)`
* `Fold(T, func(T, T) T) T`
* `FoldR(T, func(T, T) T) T`
* `Where(func(T) bool) []T`
* `Zip(...[]T) []T`


### Usage 

Install the [`goast`](https://github.com/go-goast/goast) utility.

Add the following `go:generate` annotation to any file that contains any type definition that defines a type of slice, and run the `go generate` command

`//go:generate goast write impl goast.net/x/iter`

#### Example

```go
package main

import (
	"fmt"
)

//go:generate goast write impl goast.net/x/iter

type Ints []int

func main() {
	var list Ints = []int{1, 2, 3, 4, 5, 6, 7, 8, 9, 10}
	evens := list.Where(func(i int) bool { return i%2 == 0 })
	evens.Each(func(i int) {
		fmt.Printf("%d\n", i)
	})
}

```

