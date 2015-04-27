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
