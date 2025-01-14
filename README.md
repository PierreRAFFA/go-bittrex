go-bittrex [![GoDoc](https://godoc.org/github.com/PierreRAFFA/go-bittrex?status.svg)](https://godoc.org/github.com/PierreRAFFA/go-bittrex)
==========

go-bittrex is an implementation of the Bittrex API (public and private) in Golang.

This version implement V1.1 Bittrex API and the new HMAC authentification.

## Import
	import "github.com/PierreRAFFA/go-bittrex"
	
## Usage

In order to use the client with go's default http client settings you can do:

~~~ go
package main

import (
	"fmt"
	"github.com/PierreRAFFA/go-bittrex"
)

const (
	API_KEY    = "YOUR_API_KEY"
	API_SECRET = "YOUR_API_SECRET"
)

func main() {
	// Bittrex client
	bittrex := bittrex.New(API_KEY, API_SECRET)

	// Get markets
	markets, err := bittrex.GetMarkets()
	fmt.Println(err, markets)
}
~~~

In order to use custom settings for the http client do:

~~~ go
package main

import (
	"fmt"
	"net/http"
	"time"
	"github.com/PierreRAFFA/go-bittrex"
)

const (
	API_KEY    = "YOUR_API_KEY"
	API_SECRET = "YOUR_API_SECRET"
)

func main() {
	httpClient := &http.Client{
		Timeout: time.Second * 10,
	}

	// Bittrex client
	bittrex := bittrex.NewWithCustomHttpClient(API_KEY, API_SECRET, httpClient)

	// Get markets
	markets, err := bittrex.GetMarkets()
	fmt.Println(err, markets)
}
~~~

See ["Examples" folder for more... examples](https://github.com/PierreRAFFA/go-bittrex/blob/master/examples/bittrex.go)

## Documentation
[![GoDoc](https://godoc.org/github.com/PierreRAFFA/go-bittrex?status.png)](https://godoc.org/github.com/PierreRAFFA/go-bittrex)


## Stay tuned
[Follow me on Twitter](https://twitter.com/poroot)

Donate
------

**PierreRAFFA** Original Maintainer  
![Donation QR](http://api.qrserver.com/v1/create-qr-code/?size=200x200&data=bitcoin:1HgpsmxV52eAjDcoNpVGpYEhGfgN7mM1JB%3Flabel%3DPierreRAFFA)

[1HgpsmxV52eAjDcoNpVGpYEhGfgN7mM1JB](http://tinyurl.com/mccsoez)

**PrettyBoyHelios** REST API V3 Upgrade

<a href="https://www.bitcoinqrcodemaker.com"><img src="https://www.bitcoinqrcodemaker.com/api/?style=bitcoin&amp;address=3HygqTcCGq7uT8FL5UguvFkeqV2CSto3eE" height="300" width="300" border="0" /></a>

BTC: 3HygqTcCGq7uT8FL5UguvFkeqV2CSto3eE 