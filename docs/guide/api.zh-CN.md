---
order: 2
nav:
  title: 指南
  path: /guide
  order: 0
---

# API 规范

这是 dodenHOOKS 的 API 规范文档。

## 返回值

### 1. 无输出

允许 Hooks 无输出，一般常见于生命周期类 Hooks。

```ts
useMount(() => {});
```

### 2. value 型

Hooks 输出仅有一个值。

```ts
const documentVisibility = useDocumentVisibility();
```

### 3. value-setValue 型

输出值为 value 和 setValue 类型的，结构为 `[value, setValue]`。

```ts
cosnt [state, setState] = useLocalStorageState(...);
```

### 4. value-actions 型

输出值为单 value 与多 actions 类型的，结构为 `[value, actions]`。

```ts
const [current, { inc, dec, set, reset }] = useCounter(...);
```

### 5. values 型

输出值为多 value 类型的，结构为 `{...values}`。

```ts
const { text, left, right, ... } = useTextSelection();
```

### 6. values-actions 型

输出值为多 value 与多 actions 类型的，结构为 `{...values, ...actions}`。

```ts
const { data, error, loading, run } = useRequest(...);
```

## 参数

原则上不允许超过两个参数。

### 1. 无参数

允许 Hooks 无参数。

```ts
const documentVisibility = useDocumentVisibility();
```

### 2. 单输入

单参数无论是否必填直接输入。

```ts
const size = useSize(dom);
```

### 3. 多必选参数

必选参数小于 2 个，应平级输入。

```ts
const ref = useKeyPress(keyFilter, eventHandler);
```

如果多余 2 个，应以 `Object` 形式输入。

### 4. 多非必选参数

多非必选参数以 `Object` 形式输入。

```ts
const result = useDrop({ onText, onFiled, onURI, onDOM });

const result = useRequest(service, {
  manual,
  initialData,
  onSuccess,
});
```

### 5. 必选参数 + 非必须参数

必选参数在前，非比选参数在后。

```ts
const result = useTextSelection(items, defaultSelected?);
```
