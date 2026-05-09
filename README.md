# GOing - Go Language Learning Samples

A collection of Go samples written while learning the language. Samples are intentionally kept as isolated experiments and may include incomplete or buggy code preserved as learning artifacts.

## Suggested Learning Order

```
basics/ -> oop-ish/ -> concurrency/ -> io/ -> web/
```

## Structure

| Directory | Description |
|-----------|-------------|
| `basics/` | Core language concepts: functions, types, pointers, strings, collections |
| `oop-ish/` | Interfaces, reflection, and object-model patterns |
| `concurrency/` | Goroutines, channels, select, timers, race conditions, and concurrency patterns |
| `io/` | Files, encoding/charset conversion, and templates |
| `web/` | HTTP server and REST examples |
| `assets/` | Shared non-Go files |
| `test/` | Scratch/experimental files |

### concurrency/ subfolders

| Subfolder | Concept |
|-----------|---------|
| `goroutines/` | Basic goroutine launch and concurrency |
| `goroutine-sync/` | Simple goroutine-to-goroutine sync via channel |
| `channels/` | Bidirectional/directional channels, deadlock, select with timeout |
| `select/` | Select statement with timeout channel |
| `select-fanin/` | Select for first-result among racing goroutines |
| `timers/` | Reusable timer pattern |
| `bank/` | Bank account simulation with concurrent access |
| `loops/` | Goroutines in loops |
| `patterns/` | Rob Pike's Go Concurrency Patterns (fan-in, ping-pong, parallel search) |
| `race-conditions/` | Race condition demos with mutex and atomic fixes |

## Running a Sample

Each sample is designed to be run from its own directory:

```sh
cd basics/pointers && go run main.go
cd io/templates/simple && go run main.go
cd concurrency/bank && go run bank01.go
```

Do not attempt `go build ./...` from the repo root. Samples in the same directory often declare multiple conflicting `func main()` entries and were never intended to compile together.

## External Dependencies

Some samples import third-party packages. Run `go mod tidy` at the repo root before running these:

- `io/encoding/` - `github.com/saintfish/chardet`, `golang.org/x/text`
- `web/rest/` - `github.com/julienschmidt/httprouter`
- `io/templates/bindata-example/` - `github.com/julienschmidt/httprouter` + requires `go generate` to run `go-bindata-assetfs` before compiling
