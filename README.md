# go-zendesk
[![Actions Status](https://github.com/nukosuke/go-zendesk/workflows/test/badge.svg)](https://github.com/nukosuke/go-zendesk/actions)
[![Build status](https://ci.appveyor.com/api/projects/status/ce4p1mswjkdftv6o/branch/master?svg=true)](https://ci.appveyor.com/project/nukosuke/go-zendesk/branch/master)
[![Coverage Status](https://coveralls.io/repos/github/nukosuke/go-zendesk/badge.svg?branch=master)](https://coveralls.io/github/nukosuke/go-zendesk?branch=master)
[![Go Report Card](https://goreportcard.com/badge/github.com/nukosuke/go-zendesk)](https://goreportcard.com/report/github.com/nukosuke/go-zendesk)
[![GoDoc](https://godoc.org/github.com/zenform/go-zendesk?status.svg)](https://pkg.go.dev/github.com/nukosuke/go-zendesk/zendesk)
[![FOSSA Status](https://app.fossa.io/api/projects/git%2Bgithub.com%2Fnukosuke%2Fgo-zendesk.svg?type=shield)](https://app.fossa.io/projects/git%2Bgithub.com%2Fnukosuke%2Fgo-zendesk?ref=badge_shield)

Zendesk API client library for Go

- [Reference](https://pkg.go.dev/github.com/nukosuke/go-zendesk/zendesk)

## Installation

``` shell
$ go get github.com/nukosuke/go-zendesk
```

## Usage

```go
package main

import (
    "context"

    "github.com/nukosuke/go-zendesk/zendesk"
)

func main() {
    // You can set custom *http.Client here
    client := zendesk.NewClient(nil)

    // example.zendesk.com
    client.SetSubdomain("example")

    // Authenticate with API token
    client.SetCredential(zendesk.NewAPITokenCredential("john.doe@example.com", "apitoken"))

    // Authenticate with agent password
    client.SetCredential(zendesk.NewBasicAuthCredential("john.doe@example.com", "password"))

    // Create resource
    client.CreateGroup(context.Background(), zendesk.Group{
        Name: "support team",
    })
}
```

## Want to mock API?
go-zendesk has a [mock package](https://pkg.go.dev/github.com/nukosuke/go-zendesk/zendesk/mock) generated by [golang/mock](https://github.com/golang/mock).  
You can simulate the response from Zendesk API with it.

## Authors
- [nukosuke](https://github.com/nukosuke)
- [tamccall](https://github.com/tamccall)

## License

MIT License.

See the file [LICENSE](./LICENSE).


[![FOSSA Status](https://app.fossa.io/api/projects/git%2Bgithub.com%2Fnukosuke%2Fgo-zendesk.svg?type=large)](https://app.fossa.io/projects/git%2Bgithub.com%2Fnukosuke%2Fgo-zendesk?ref=badge_large)
