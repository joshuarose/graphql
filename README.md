# Golang GraphQL Client

![GitHub release](https://img.shields.io/github/release/joshuarose/graphql.svg)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Commitizen friendly](https://img.shields.io/badge/commitizen-friendly-brightgreen.svg)](http://commitizen.github.io/cz-cli/)
[![Go Report Card](https://goreportcard.com/badge/github.com/joshuarose/graphql)](https://goreportcard.com/report/github.com/joshuarose/graphql)
[![GoDoc](https://godoc.org/github.com/joshuarose/graphql?status.svg)](https://godoc.org/github.com/joshuarose/graphql)
[![Build Status](https://travis-ci.org/joshuarose/graphql.svg?branch=master)](https://travis-ci.org/joshuarose/graphql)
[![codecov](https://codecov.io/gh/joshuarose/graphql/branch/master/graph/badge.svg)](https://codecov.io/gh/joshuarose/graphql)


Fully compatible with <https://github.com/shurcooL/graphql> v0.0.0-20181231061246-d48a9a75455f

You can simply replace `github.com/shurcooL/graphql` --> `github.com/joshuarose/graphql` to access new features.


* [GraphQL 学习笔记](https://blog.joshuarose.com/p/graphql/)

## New Features

### Cache friendly

use HTTP GET when request graphql query,
use HTTP POST when request graphql mutation.


### Set Headers & Cookies

```go
cli := NewClient(
    "url",
    httpClient,
    graphql.WithCookie("cookieName", "cookieVal"),
    graphql.WithHeader("headerName", "headerVal"),
)
```

## Usage

```go
package test

import (
	"context"
	"net/http"
	"testing"

	"github.com/joshuarose/graphql"
)

type gcpLockQuery struct {
	Lock struct {
		Name      graphql.String `graphql:"name"`
		ExpiresAt graphql.String `graphql:"expires_at"`
	} `graphql:"Lock(name: $name)"`
}

func TestQueryWithHTTPGet(t *testing.T) {
	ctx := context.Background()
	httpClient := http.DefaultClient
	query := new(gcpLockQuery)
	vars := map[string]interface{}{
		"name": graphql.String("joshuarose.123"),
	}
	gracli := graphql.NewClient(
		"https://blog.joshuarose.com/graphql/query/",
		httpClient,
	)
	if err := gracli.Query(ctx, query, vars); err != nil {
		t.Fatalf("%+v", err)
	}

}
```
