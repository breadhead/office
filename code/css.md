# CSS code style

Мы используем [stylelint](https://github.com/stylelint/stylelint) с плагинами для линтинга и форматирования стилей

## Установка

```yarn add -D stylelint stylelint-order stylelint-config-recess-order```


## Использование

```yarn lint:style```

## Config

### package.json

```
{
  "name": "app",
  "version": "1.0.0",
  "scripts": {
    ...
    "lint:style": "stylelint './**/*.css' --fix",
    ...
  },
  "dependencies": {
   ...
  },
  "devDependencies": {
    ...
  }
}
```

### .stylelintrc

```
{
  "extends": ["stylelint-config-recommended", "stylelint-config-recess-order"],
  "plugins": ["stylelint-order"],
}
```