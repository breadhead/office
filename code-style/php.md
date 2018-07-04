# PHP Code Style

We use [EasyCodingStandard](https://github.com/Symplify/EasyCodingStandard) with some custom rules.

## Insatll

+ `composer require --dev symplify/easy-coding-standard`
+ add `.ecs_cache` to `.gitignore`
+ create `easy-coding-standard.yml` with [config](#config)

## Usage

+ `vendor/bin/ecs check .` for checking
+ `vendor/bin/ecs check . --fix` for fixing

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
