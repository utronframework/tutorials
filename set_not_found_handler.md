# Setting up a not found handler in utron

Custom rendering of `404` status page is easy in utron.

Utron App provides a method ` SetNotFoundHandler(h http.Handler) error` which you can use it as follows.

First we define our handler function 

```go
func NotFound(w http.ResponseWriter, r *http.Request) {
	w.Write([]byte("we found nothing"))
}
```

And then we register it like this

```go
	app := utron.NewApp()
	app.SetNotFoundHandler(http.HandlerFunc(NotFound))
```

Enjoy
