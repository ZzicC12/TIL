## css

- css prop을 사용하기 위해서 babel 설정 OR 추가 설정 필요
- `babel.config.json`
  - presets: ['@emotion/babel-preset-css-prop'],
  - plugin 사용을 위해 craco OR eject 필요
- `tsconfig.json`
  - "jsxImportSource": "@emotion/react"
  - `/** @jsxImportSource @emotion/react */`

### object style

```html
<div css={{ color: "red" }}>hello</div>
```

### string style

```javascript
/** @jsxImportSource @emotion/react */
import { css } from "@emotion/react";
<div
  css={css`
    color: red;
  `}
>
  hello
</div>;
```

## jsx

- s
