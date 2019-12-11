# Golang GraphQL Client

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
