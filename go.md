## reference
```go
go version
go run xxx
go build xxx
go fmt
go doc
go install
go fix
go test 

import runtime
runtime.Version()

$GOROOT
/usr/lib/go

注释
//
/*  */

包
package main

类型
int, float, bool, string
struct, array, slice, map, channel
interface
函数的返回类型

type IZ int

函数
func functionName(p1 type1, p2 type2) (ret1 type1, ret2 type2) {
}


```

## hello, world
```go
package main

func main() {
    println("hello", "world")
}
```

## Go运行时(runtime)
尽管 Go 编译器产生的是本地可执行代码，这些代码仍旧运行在 Go 的 runtime（这部分的代码可以在 runtime 包中找到）当中。这个 runtime 类似 Java 和 .NET 语言所用到的虚拟机，它负责管理包括内存分配、垃圾回收、栈处理、goroutine、channel、切片（slice）、map 和反射（reflection）等等。

$GOROOT/src/runtime

Go 的可执行文件都比相对应的源代码文件要大很多，这恰恰说明了 Go 的 runtime 嵌入到了每一个可执行文件当中。Go 不需要依赖任何其它文件，它只需要一个单独的静态文件，这样你也不会像使用其它语言一样在各种不同版本的依赖文件之间混淆。

## Go程序的一般结构

```go
package main

import (
    "fmt"
)

const c = "C"
var v int = 5
type T struct{

}

func init() {

}

func main() {
    var a int
    Func1()
    fmt.Println(a)
}

func (t T) Method1() {

}

func Func1() {

}
```

