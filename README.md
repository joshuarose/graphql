Fully compatable with github.com/shurcooL/graphql v0.0.0-20181231061246-d48a9a75455f

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
