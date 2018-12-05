# Использовать Enum как ключи в типе

Вот так

```ts
type ModalsMap = { [key in keyof typeof MyEnum]: string }
```
