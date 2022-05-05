---
layout: post
title: "Go Discrete Skills"
date:  2022-05-05 10:11:53 +0800
categories: Go
---

这里记录一些平时学到的一些离散的Golang技巧。

1. 当搞不清把Slice变量当参数应该传它的指针还是值的时候，看看下面这段代码：
```go
package main

import "fmt"

func main() {
    s := []string{"a", "b"}
    fmt.Println(testPassValue(s))    // [b]
    fmt.Println(s)                   // [a b]
    fmt.Println(testPassAddress(&s)) // [b]
    fmt.Println(s)                   // [b]
}

func testPassValue(s []string) []string {
    s = s[1:]
    return s
}

func testPassAddress(s *[]string) []string {
    *s = (*s)[1:]
    return *s
}
```

2. 当用copy函数进行两个slice赋值的时候，应该先为目标slice分配和源slice一样大小的数组空间：
```go
// copy x to y, type of both x and y is []int
y = make([]int, len(x), cap(x))
copy(y, x)
```

3. map 类型的变量使用前应该用map literal或者make初使化：
```go
var m map[string]int

m = map[string]int{ ... }  // keys is requried

m = make(map[string]int) // make
```

以上。