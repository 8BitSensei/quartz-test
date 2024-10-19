2023-03-23
#programming #go-lang 

#### Errors on deferred calls

We can wrap whatever we want to handle in a `func` which is deferred
```go
defer func() {
		if _, err = store.Shutdown(false); err != nil {
			if errors.Is(err, storage.ErrLayerUsedByContainer) {
				options.Logger.Infof("failed to shutdown storage: %q", err)
			} else {
				options.Logger.Warnf("failed to shutdown storage: %q", err)
			}
		}
	}()
```

---
# References
