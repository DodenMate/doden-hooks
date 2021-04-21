---
order: 3
nav:
  title: 指南
  path: /guide
  order: 0
---

# FAQ

以下是我们整理的一些 dodenHOOKS 社区常见的问题和官方答复，在提问之间建议找找有没有类似的问题。

## 浏览器的兼容性

部分 Hooks 会依赖一些 ES 的新特性，例如 `Set` / `Map` / `Promise`，如果需要兼容较低版本的浏览器（例如 IE <= 11），可以全局引入一些 polyfill，例如 [core-js](https://github.com/zloirock/core-js) 和 [babel-polyfill](https://babeljs.io/docs/en/babel-polyfill/)。
