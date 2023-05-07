# Go module Public

```sh
go mod init github.com/:username/:projectName
```

github.com/:username/:projectName 可以換成任意字串，因爲個人希望將 Go module 放置於 GitHub,

因此將模組名稱設定為 github.com/:username/:projectName

上述指令成功後，將會看到資料夾內出現 1 個檔案 go.mod :

```sh
module github.com/:username/:projectName

go 1.19
```

go.mod 用來紀錄 Go module 的名稱與所使用的 Go 版本，以及相依的 Go modules, 該檔案是 Go module 必備的檔案

相當於 package.json

## Create module

```sh
# 創建兩個檔案夾
mkdir greeting cli

# 創建兩個 go 檔
touch greeting/greeting.go cli/say.go
```

進行至此，資料夾結構應如下所示：

```sh
.
├── go.mod
├── cli
│   └── say.go
└── greeting
    └── greeting.go
```

```go
// greeting.go 是 1 個簡單的 package, 用以列印所傳入的字串；
package greeting

import "fmt"

func Say(s string) {
    fmt.Println(s)
}
```

```go
package main

import "github.com/:username/:projectName"

func main() {
    greeting.Say("Hello")
}
```

## Build

最後，試著編譯一次，正常的話不會有任何錯誤訊息：

```sh
go build ./...
```

## Publish to Public

```sh
git remote add ...
git push -u origin main
```
