# CSS code style

Мы используем 

1. [stylelint](https://github.com/stylelint/stylelint) для линтинга и форматирования стилей
2. [stylelint-config-recommended](https://github.com/stylelint/stylelint-config-recommended) для линтинга стилей
3. [stylelint-order](https://github.com/hudochenkov/stylelint-order) и [stylelint-config-recess-order](https://github.com/stormwarning/stylelint-config-recess-order) для единообразного порядка CSS-правил


---
1. stylelint

```yarn add -D stylelint```

2. stylelint-config-recommended
### .stylelintrc

```
{
  "extends": ["stylelint-config-recommended"],
}
```

3. stylelint-order

```yarn add -D stylelint-order```

### .stylelintrc
```
{
  "extends": ["stylelint-config-recommended"],
  "plugins": ["stylelint-order"],
}
```

3. stylelint-config-recess-order

```yarn add -D stylelint-config-recess-order```

### .stylelintrc
```
{
  "extends": ["stylelint-config-recommended", "stylelint-config-recess-order"],
  "plugins": ["stylelint-order"],
}
```