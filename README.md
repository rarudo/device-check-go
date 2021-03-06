# device-check-go

![golang](https://img.shields.io/badge/golang-1.11-blue.svg?style=flat)
![GitHub release](https://img.shields.io/github/release/snowman-mh/device-check-go.svg?colorB=7E7E7E)
[![GoDoc](https://godoc.org/github.com/snowman-mh/device-check-go?status.svg)](https://godoc.org/github.com/snowman-mh/device-check-go)
[![Build Status](https://travis-ci.org/snowman-mh/device-check-go.svg?branch=master)](https://travis-ci.org/snowman-mh/device-check-go)
[![codecov.io](https://codecov.io/github/snowman-mh/device-check-go/coverage.svg?branch=master)](https://codecov.io/github/snowman-mh/device-check-go?branch=master)
[![Go Report Card](https://goreportcard.com/badge/github.com/snowman-mh/device-check-go)](https://goreportcard.com/report/github.com/snowman-mh/device-check-go)
[![MIT License](http://img.shields.io/badge/license-MIT-blue.svg?style=flat)](LICENSE)

iOS DeviceCheck SDK for Go - query and modify the per-device bits

## Installation

```bash
go get github.com/snowman-mh/device-check-go
```

## Get started

### Query two bits

```go
import "github.com/snowman-mh/device-check-go"

cred := devicecheck.NewCredentialFile("/path/to/private/key/file")
cfg := devicecheck.NewConfig("ISSUER", "KEY_ID", devicecheck.Development)
client := devicecheck.New(cred, cfg)

result := devicecheck.QueryTwoBitsResult{}
err := client.QueryTwoBits("DEVICE_TOKEN_FROM_CLIENT", &result)
```

### Update two bits

```go
import "github.com/snowman-mh/device-check-go"

cred := devicecheck.NewCredentialFile("/path/to/private/key/file")
cfg := devicecheck.NewConfig("ISSUER", "KEY_ID", devicecheck.Development)
client := devicecheck.New(cred, cfg)

err := client.UpdateTwoBits("DEVICE_TOKEN_FROM_CLIENT", true, true)
```

### Validate device token

```go
import "github.com/snowman-mh/device-check-go"

cred := devicecheck.NewCredentialFile("/path/to/private/key/file")
cfg := devicecheck.NewConfig("ISSUER", "KEY_ID", devicecheck.Development)
client := devicecheck.New(cred, cfg)

err := client.ValidateDeviceToken("DEVICE_TOKEN_FROM_CLIENT")
```

## Apple documentation

- [iOS DeviceCheck API for Swift](https://developer.apple.com/documentation/devicecheck)
- [HTTP commands to query and modify the per-device bits](https://developer.apple.com/documentation/devicecheck/accessing_and_modifying_per-device_data)
