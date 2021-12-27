> # 如何使用 go mod 管理自己的项目？

> ## Step 1
检查 go 版本，1.11 以上的 go 版本才能使用 go modules
```
go version
```

> ## Step 2
设置环境变量
```
go env -w GO111MODULE=on
go env -w GOPROXY=https://goproxy.cn,direct
```
go env -w 会将配置信息写到环境变量 GOENV 中，可以用 `go env` 命令查看 go 的环境变量

> ## Step 3
在 main.go 的同级目录下执行：`go mod init project_name` ，可以生成该项目的 go.mod 文件，  go.mod 会自动对项目进行依赖管理

> ## 补充说明
1. 使用 go mod 管理项目时，依赖包存放在 `$GOPATH/pkg` 目录下，并且允许同一个依赖包有多个不同的版本存在
2. 多个项目可以共享 `$GOPATH/pkg` 目录下依赖包缓存
3. 在 windows 系统中，`$GOPATH/pkg` 目录的文件结构为：
    1. mod
    2. sumdb
    3. windows_amd64
    