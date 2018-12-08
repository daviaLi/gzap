# gzap

## Example

```go
package main

import (
	"fmt"
	"go.uber.org/zap"
	"github.com/gin-gonic/gin"
	"github.com/daviaLi/gzap"
)

func main() {
	r := gin.New()

	logger, _ := zap.NewProduction()

	r.Use(gzap.Logger(logger))

	// Example ping request.
	r.GET("/ping", func(c *gin.Context) {
		c.String(http.StatusOK, "pong")
	})

	// Listen and Server in 0.0.0.0:8080
	r.Run(":8080")
}
```