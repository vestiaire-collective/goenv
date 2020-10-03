# goenv

a small package for reading env vars by type

---

### example

```go
package main

import (
	"github.com/chaseisabelle/goenv"
	"os"
)

func main() {
	println(goenv.String("STRING", "fart")) //<< should be fart
	println(goenv.Bool("BOOL", false)) //<< should be false
	println(goenv.Bytes("BYTES", []byte("foo"))) //<< should be foo

	f32, err := goenv.Float32("FLOAT32", 0)

	if err != nil {
		panic(err)
	}

	f64, err := goenv.Float64("FLOAT64", 0)

	if err != nil {
		panic(err)
	}

	i, err := goenv.Int("INT", 0)

	if err != nil {
		panic(err)
	}

	i32, err := goenv.Int32("INT32", 0)

	if err != nil {
		panic(err)
	}

	i64, err := goenv.Int64("INT64", 0)

	if err != nil {
		panic(err)
	}

	u, err := goenv.Uint("UINT", 0)

	if err != nil {
		panic(err)
	}

	u8, err := goenv.Uint8("UINT8", 0)

	if err != nil {
		panic(err)
	}

	u16, err := goenv.Uint16("UINT16", 0)

	if err != nil {
		panic(err)
	}

	u32, err := goenv.Uint32("UINT32", 0)

	if err != nil {
		panic(err)
	}

	u64, err := goenv.Uint64("UINT64", 0)

	if err != nil {
		panic(err)
	}

	println(f32) //<< should be 0
	println(f64) //<< should be 0
	println(i) //<< should be 0
	println(i32) //<< should be 0
	println(i64) //<< should be 0
	println(u) //<< should be 0
	println(u8) //<< should be 0
	println(u16) //<< should be 0
	println(u32) //<< should be 0
	println(u64) //<< should be 0

	vars := map[string]string{
		"STRING":  "poop",
		"BOOL":    "1",
		"BYTES":   "bar",
		"FLOAT32": "420.69",
		"FLOAT64": "666.69",
		"INT":     "-420",
		"INT32":   "-69",
		"INT64":   "-666",
		"UINT":    "420",
		"UINT8":   "8",
		"UINT16":  "16",
		"UINT32":  "32",
		"UINT64":  "64",
	}

	for k, v := range vars {
		err := os.Setenv(k, v)

		if err != nil {
			panic(err)
		}
	}

	println(goenv.String("STRING", "fart")) //<< should be poop
	println(goenv.Bool("BOOL", false)) //<< should be true
	println(goenv.Bytes("BYTES", []byte("foo"))) //<< should be bar

	f32, err = goenv.Float32("FLOAT32", 0)

	if err != nil {
		panic(err)
	}

	f64, err = goenv.Float64("FLOAT64", 0)

	if err != nil {
		panic(err)
	}

	i, err = goenv.Int("INT", 0)

	if err != nil {
		panic(err)
	}

	i32, err = goenv.Int32("INT32", 0)

	if err != nil {
		panic(err)
	}

	i64, err = goenv.Int64("INT64", 0)

	if err != nil {
		panic(err)
	}

	u, err = goenv.Uint("UINT", 0)

	if err != nil {
		panic(err)
	}

	u8, err = goenv.Uint8("UINT8", 0)

	if err != nil {
		panic(err)
	}

	u16, err = goenv.Uint16("UINT16", 0)

	if err != nil {
		panic(err)
	}

	u32, err = goenv.Uint32("UINT32", 0)

	if err != nil {
		panic(err)
	}

	u64, err = goenv.Uint64("UINT64", 0)

	if err != nil {
		panic(err)
	}

	println(f32) //<< should be 420.69
	println(f64) //<< should be 666.69
	println(i) //<< should be -420
	println(i32) //<< should be -69
	println(i64) //<< should be -666
	println(u) //<< should be 420
	println(u8) //<< should be 8
	println(u16) //<< should be 16
	println(u32) //<< should be 32
	println(u64) //<< should be 64
}
```