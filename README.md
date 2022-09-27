<div align="center">
    <a href="https://discord.gg/4qcXbeVehZ">
        <img alt="Discord" src="https://img.shields.io/discord/882288646517035028?label=%F0%9F%92%AC%20discord">
    </a>
    <a href="https://github.com/durudex/go-protobuf-type/blob/main/LICENSE">
        <img alt="License" src="https://img.shields.io/github/license/durudex/go-protobuf-type?label=%F0%9F%93%95%20license">
    </a>
    <a href="https://github.com/durudex/go-protobuf-type/stargazers">
        <img alt="GitHub Stars" src="https://img.shields.io/github/stars/durudex/go-protobuf-type?label=%E2%AD%90%20stars&logo=sdf">
    </a>
    <a href="https://github.com/durudex/go-protobuf-type/network">
        <img alt="GitHub Forks" src="https://img.shields.io/github/forks/durudex/go-protobuf-type?label=%F0%9F%93%81%20forks">
    </a>
</div>

<h1 align="center">Go Protobuf Types</h1>

# Setup

```
go get github.com/durudex/go-protobuf-type
```

If you use [buf.build](https://docs.buf.build/introduction) then you can add our proto files as follows:

```yml
deps:
  - buf.build/durudex/type
```

# Usage

```proto
import "durudex/type/timestamp.proto";

message Test {
    // Used custom timestamp type.
    durudex.type.Timestamp timestamp = 1;
}
```

```go
import (
    "fmt"

    "github.com/durudex/go-protobuf-type/pbtype"
)

func main() {
    // Creating a generated protobuf Test message structure.
    test := Test{Timestamp: pbtype.Now()}

    // Getting time.Time type.
    fmt.Println(test.Timestamp.AsTime()) // 2022-07-10 16:07:08.243878 +0000 UTC
}
```

## ⚠️ License
Copyright © 2022 [Durudex](https://github.com/durudex). Released under the MIT license.
