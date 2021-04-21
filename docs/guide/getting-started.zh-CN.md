---
order: 0
nav:
  title: 指南
  path: /guide
  order: 0
---

# 快速上手

dodenHOOKS 是一个扩展 React Hooks 的库，致力于提供常用且高质量的 Hooks。

> 在开始之前，你需要掌握 React 及 React Hooks 的基础用法。访问[链接](https://zh-hans.reactjs.org/docs/hooks-intro.html)学习 React Hooks 官方文档。

## 第一个例子

这是一个最简单的 dodenHOOKS 示例。

```
import React from 'react';
import { useToggle } from '@doden/hooks';

export default (): JSX.Element => {
  const [state, { toggle }] = useToogle();

  return (
    <div>
      <p>当前布尔值：{String(state)}</p>
      <p>
        <button onClick={() => toggle()}>Toggle</button>
      </p>
    </div>
  );
};
```

## 按需加载

你可以通过以下的写法来按需加载 dodenHOOKS。

```
import useToggle from '@doden/hooks/es/useToggle';
```

> 注意：dodenHOOKS 默认支持基于 ES module 的 tree shaking，对于 JavaScript 部分，直接引入 `import { useToggle } from '@doden/hooks` 也会有按需加载的效果。

如果你使用了 babel，那么可以使用 [babel-plugin-import](https://github.com/ant-design/babel-plugin-import) 来进行按需加载，加入这个插件后，你可以仍然这么写：

```
import { useToggle } from '@doden/hooks';
```

插件会帮你转换成 `@doden/hooks/es/useToggle` 的写法。

## 社区互助

如果你在使用的过程中遇到任何问题，可以通过下面几个途径寻求帮助，同时我们也鼓励大佬通过下面的途径给萌新提供帮助。

通过 GitHub Discussions 提问时，建议使用 `Q&A` 标签。

通过 Stack Overflow 活着

## 贡献者

- DodenMate
- Keven
