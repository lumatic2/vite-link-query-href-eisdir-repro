# vite build fails with EISDIR on `<link rel="alternate" href="?md">`

`index.html` has one valid query-only relative URL:

```html
<link rel="alternate" type="text/markdown" href="?md">
```

```sh
npm install
npm run build
```

Expected: the build finishes and the href is left as-is (it is not a local asset).
Actual: `[vite:build-html] EISDIR: illegal operation on a directory, read`.

Seen on vite 7.3.7 and 8.3.4, on Windows 11 and Linux (WSL Ubuntu 24.04).
