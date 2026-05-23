# Sonic

A fast, flexible JSON serializer/deserializer for Go, forked from [bytedance/sonic](https://github.com/bytedance/sonic).

[![Go Reference](https://pkg.go.dev/badge/github.com/your-org/sonic.svg)](https://pkg.go.dev/github.com/your-org/sonic)
[![Go Report Card](https://goreportcard.com/badge/github.com/your-org/sonic)](https://goreportcard.com/report/github.com/your-org/sonic)
[![License](https://img.shields.io/badge/license-Apache%202.0-blue.svg)](LICENSE)

## Features

- **High Performance**: Significantly faster than `encoding/json` for most workloads
- **Drop-in Replacement**: Compatible API with the standard `encoding/json` package
- **Cross-platform**: Supports amd64, arm64, and generic fallback for other architectures
- **Streaming**: Supports streaming encode/decode
- **Flexible**: Supports custom marshalers and unmarshalers

## Requirements

- Go 1.19 or later
- Supported OS: Linux, macOS, Windows
- Supported Arch: amd64 (optimized), arm64 (optimized), others (fallback)

## Installation

```bash
go get github.com/your-org/sonic
```

## Quick Start

```go
import "github.com/your-org/sonic"

// Marshal
data, err := sonic.Marshal(&MyStruct{})

// Unmarshal
err = sonic.Unmarshal(data, &MyStruct{})

// Use as a drop-in replacement for encoding/json
var json = sonic.ConfigDefault
```

## Configuration

Sonic provides several preset configurations:

```go
// Default configuration (compatible with encoding/json)
sonic.ConfigDefault

// Faster configuration (less validation)
sonic.ConfigFastest

// Standard configuration
sonic.ConfigStd
```

## Benchmarks

Benchmarks are run automatically via GitHub Actions. See [benchmark results](https://github.com/your-org/sonic/actions/workflows/benchmark.yml) for the latest performance data.

To run benchmarks locally:

```bash
go test -bench=. -benchmem ./...
```

## Compatibility

Sonic is tested against multiple Go versions and platforms. See the compatibility test workflows for details:
- [Linux/macOS](.github/workflows/compatibility_test.yml)
- [Windows](.github/workflows/compatibility_test-windows.yml)

## Contributing

Contributions are welcome! Please read our [Pull Request Template](.github/PULL_REQUEST_TEMPLATE.md) before submitting a PR.

For bugs, please use the [Bug Report](.github/ISSUE_TEMPLATE/bug_report.md) template.
For feature requests, please use the [Feature Request](.github/ISSUE_TEMPLATE/feature_request.md) template.

## License

This project is licensed under the Apache License 2.0 - see the [LICENSE](LICENSE) file for details.

## Acknowledgements

This project is a fork of [bytedance/sonic](https://github.com/bytedance/sonic). We are grateful to the original authors for their excellent work.
