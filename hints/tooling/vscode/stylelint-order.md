# Stylelint-order и VS code

Для того, чтобы сортировать CSS-правила автоматически, мы используем 

1. [stylelint](https://github.com/stylelint/stylelint)
2. [stylelint-order](https://github.com/hudochenkov/stylelint-order)
3. [stylelint-config-recess-order](https://github.com/stormwarning/stylelint-config-recess-order)
4. Задачи в VS code

---
1. stylelint

```yarn add -D stylelint```

2. stylelint-order

```yarn add -D stylelint-order```

### .stylelintrc
```
{
  "plugins": ["stylelint-order"],

}
```

3. stylelint-config-recess-order

```yarn add -D stylelint-config-recess-order```

### .stylelintrc
```
{
  "extends": ["stylelint-config-recess-order"],
  "plugins": ["stylelint-order"],

}
```

4. Задачи в VS code

### package.json

Добавляем скрипт для линтинга и исправления стилей

```"lint:style": "stylelint './**/*.css' --fix"```

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

### vscode/tasks.json

Создаем задачу в VS code 

```
{
  // See https://go.microsoft.com/fwlink/?LinkId=733558
  // for the documentation about the tasks.json format
  "version": "2.0.0",
  "tasks": [
    {
      "label": "fix styles",
      "type": "npm",
      "script": "lint:style",
      "problemMatcher": []
    }
  ]
} 
```

### keybindings.json

Привязываем сочетание клавиш к задаче

```[
  ...
  {
    "key": "alt+s",
    "command": "workbench.action.tasks.runTask",
    "args": "fix styles"
  }
]```

Теперь у нас есть возможность использовать комбинацию клавиш ```alt+s```, чтобы исправить порядок CSS-правил во всем проекте