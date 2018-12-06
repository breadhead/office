# Conventional Commits

# Глобальные пакеты

`npm i -g commitizen`

# Локальные пакеты

`yarn add --dev cz-customizable husky @commitlint/cli`

# Локальная конфигурация

```js
// ./git/commitizen.js

"use strict";

module.exports = {
  types: [
    { value: "build",    name: "build:     Сборка проекта или изменения внешних зависимостей" },
    { value: "ci",       name: "ci:        Настройка CI и работа со скриптами" },
    { value: "docs",     name: "docs:      Обновление документации" },
    { value: "feat",     name: "feat:      Добавление нового функционала" },
    { value: "fix",      name: "fix:       Исправление ошибок" },
    { value: "perf",     name: "perf:      Изменения направленные на улучшение производительности" },
    { value: "refactor", name: "refactor:  Правки кода без исправления ошибок или добавления новых функций" },
    { value: "revert",   name: "revert:    Откат на предыдущие коммиты" },
    { value: "style",    name: "style:     Правки по кодстайлу (табы, отступы, точки, запятые и т.д.)" },
    { value: "test",     name: "test:      Добавление тестов" }
  ],

  scopes: [
    { name: "global" },
    // ... другие области в проекте
  ],

  messages: {
    type: "Какие изменения вы вносите?",
    scope: "\nВыберите ОБЛАСТЬ, которую вы изменили (опционально):",
    subject: "Напишите КОРОТКОЕ описание в ПОВЕЛИТЕЛЬНОМ наклонении:\n",
    body: 'Напишите ПОДРОБНОЕ описание (опционально). Используйте "|" для новой строки:\n',
    breaking: "Список BREAKING CHANGES (опционально):\n",
    footer: "Место для мета данных (тикетов, ссылок и остального). Например: SECRETMRKT-700, SECRETMRKT-800:\n",
    confirmCommit: "Вас устраивает получившийся коммит?"
  },

  allowCustomScopes: false,
  allowBreakingChanges: false,
  footerPrefix: "META:",
  subjectLimit: 72
}
```

```js
// ./git/commitlint.js

module.exports = {
  rules: {
    "body-leading-blank": [2, "always"],
    "footer-leading-blank": [2, "always"],
    "header-max-length": [2, "always", 72],
    "scope-case": [2, "always", "lower-case"],
    "subject-empty": [2, "never"],
    "subject-full-stop": [2, "never", "."],
    "type-case": [2, "always", "lower-case"],
    "type-empty": [2, "never"],
    "type-enum": [
      2,
      "always",
      [
        "build",
        "ci",
        "docs",
        "feat",
        "fix",
        "perf",
        "refactor",
        "revert",
        "style",
        "test"
      ]
    ]
  }
}
```

```json
// package.json
{
  ...
  "config": {
    "commitizen": {
      "path": "node_modules/cz-customizable"
    },
    "cz-customizable": {
      "config": "git/commitizen.js"
    }
  },
  "husky": {
    "hooks": {
      "commit-msg": "commitlint -E HUSKY_GIT_PARAMS -g './git/commitlint.js'"
    }
  }
  ...
}
```

# Автоматическая генерация сообщений коммита
`git cz`
