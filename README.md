# Golang GraphQL Client

![GitHub release](https://img.shields.io/github/release/Laisky/graphql.svg)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Commitizen friendly](https://img.shields.io/badge/commitizen-friendly-brightgreen.svg)](http://commitizen.github.io/cz-cli/)
[![Go Report Card](https://goreportcard.com/badge/github.com/Laisky/graphql)](https://goreportcard.com/report/github.com/Laisky/graphql)
[![GoDoc](https://godoc.org/github.com/Laisky/graphql?status.svg)](https://godoc.org/github.com/Laisky/graphql)
[![Build Status](https://travis-ci.org/Laisky/graphql.svg?branch=master)](https://travis-ci.org/Laisky/graphql)
[![codecov](https://codecov.io/gh/Laisky/graphql/branch/master/graph/badge.svg)](https://codecov.io/gh/Laisky/graphql)


Fully compatibility with <https://github.com/shurcooL/graphql> v0.0.0-20181231061246-d48a9a75455f

You can simply replace `github.com/shurcooL/graphql` --> `github.com/Laisky/graphql` to access new features.

## New Features

### Set Headers & Cookies

```go
cli := NewClient(
    "url",
    httpClient,
    graphql.WithCookie("cookieName", "cookieVal"),
    graphql.WithHeader("headerName", "headerVal"),
)
```
