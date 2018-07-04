# PHP Code Style

Мы используем [EasyCodingStandard](https://github.com/Symplify/EasyCodingStandard) и набор правил [Symfony](https://github.com/Symplify/EasyCodingStandard/blob/master/config/symfony.yml) с некоторыми дополнениями.

## Установка

+ `composer require --dev symplify/easy-coding-standard`
+ добавьте `.ecs_cache` в `.gitignore`
+ создайте `easy-coding-standard.yml` с [конфигурацией](#config)

## Использование

+ `vendor/bin/ecs check .` для проверки
+ `vendor/bin/ecs check . --fix` для автоматического исправления

## Config

```yml
imports:
  - { resource: '%vendor_dir%/symplify/easy-coding-standard/config/symfony.yml' }

services:
  PhpCsFixer\Fixer\Operator\BinaryOperatorSpacesFixer:
    align_double_arrow: true
  PhpCsFixer\Fixer\ArrayNotation\ArraySyntaxFixer:
    syntax: short
  PhpCsFixer\Fixer\Operator\ConcatSpaceFixer:
    spacing: one

parameters:
  cache_directory: .ecs_cache
  exclude_checkers:
    - 'PhpCsFixer\Fixer\Phpdoc\PhpdocAnnotationWithoutDotFixer'
    - 'PhpCsFixer\Fixer\Phpdoc\PhpdocSummaryFixer'
    - 'PhpCsFixer\Fixer\ControlStructure\YodaStyleFixer'
  exclude_files:
    - '**/vendor/**/*'
```
