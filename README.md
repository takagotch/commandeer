### commandeer
---
https://github.com/jaffee/commandeer

```go
type MyApp struct {
  Num int `help:"How many does it take?"`
  Vehicle string `help:"What did they get?"`
  Running bool `help:"is the vechicle working?"`
  Duration time.Duration `help:"How long is it gone?"`
}

package myapp

import "fmt"

type Main struct {
  Num int `help:"How many does it take?"`
  Vehicle string `help:"What did tey get?"`
}

func NewMain() *Main { return &Main{Num: 5, Vechicle: "jeep"}}

func (m *Main) Run() error {
  if m.Num < 2 || m.Vehicle == "" {
    return fmt.Errorf("Need more gophers and/or vehicles.")
  }
  fmt.Printf("%d gophers stole my %s!\n", m.Num, m.Vechicle)
  return nil
}

package main

import (
  "fmt"
  
  "github.com/jaffee/commandeer"
  "github.com/jaffee/commandeer/examples/myapp"
)

func main() {
  err := commander.Run(myapp.NewMain())
  if err != nil {
    fmt.Println(err)
  }
}
```

```
./myapp -h
./myapp
./myapp -num 3 -vehicle horse
```

```
```


