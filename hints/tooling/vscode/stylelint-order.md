# Stylelint-order и VS code

Для того, чтобы сортировать CSS-правила автоматически, мы используем [CSS-codestyle](../../../../code/css.md) и задачи в VS code

## Настройка

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
]
```


## Использование

С помощью комбинации клавиш  ```alt+s``` исправляем порядок стилей во всем проекте