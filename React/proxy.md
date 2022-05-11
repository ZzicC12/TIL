## CRA에서 proxy 사용법

### package.json에서 proxy 추가

```json
{
  "proxy": "http://localhost:8080"
}
```

### http-proxy-middleware 사용

- `setupProxy.js` 생성

```javascript
const { createProxyMiddleware } = require("http-proxy-middleware");

module.exports = function (app) {
  app.use(
    "/api",
    createProxyMiddleware({
      target: "http://localhost:8080",
      changeOrigin: true,
    })
  );
};
```

- /api/user/1 -> target + /api/user/1
