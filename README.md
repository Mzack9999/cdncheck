# cdncheck
Helper library that checks if a given IP belongs to known CDN ranges (akamai, cloudflare, incapsula and sucuri).
The library can be used by importing `github.com/projectdiscovery/cdncheck`. here follows a basic example:


```go
package main

import (
    "log"
    "net"
    "github.com/projectdiscovery/cdncheck"
)

func main() {
    client, err := cdncheck.New()
    if err != nil {
        log.Fatal(err)
    }
    if found, err := client.Check(net.ParseIP("173.245.48.12")); found && err == nil {
        log.Println("ip is part of cdn")
    }
}
```