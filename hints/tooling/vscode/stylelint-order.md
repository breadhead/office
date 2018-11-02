# Stylelint-order и VS code

Для того, чтобы сортировать CSS-правила автоматически, мы используем stylelint-плагины [stylelint-order](https://github.com/hudochenkov/stylelint-order), [stylelint-config-recess-order](https://github.com/stormwarning/stylelint-config-recess-order) и задачи в VS code

---
## Задачи в VS code

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