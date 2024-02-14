# InSales Code Style Guide

Пока здесь обитают только правила для `rubocop`.

## Rubocop

Для использования в `.rubocop.yml` в проекте надо добавить:
```yaml
inherit_from:
  - https://raw.githubusercontent.com/insales/code_style/master/ruby/НУЖНЫЙ_ФАЙЛ
```

Правила разделены на три группы:
- общие правила, лежат в файле `rubocop.yml`;
- правила для rails, лежат в файле `rubocop_rails.yml` (также включают правила для `rspec`);
- правила для rspec, лежат в файле `rubocop_rspec.yml`.

Их можно подключать в проекты по необходимости.
Например, `rails` не нужен в проектах без rails или в гемах: он может ругаться, что вы не используете `delegate`, которого нет в базовом ruby.

Базовый `.rubocop.yml` сейчас выглядит так:
```yaml
inherit_from:
  - https://raw.githubusercontent.com/insales/code_style/master/ruby/rubocop.yml
  - https://raw.githubusercontent.com/insales/code_style/master/ruby/rubocop_rails.yml

# У нас есть файлы с общими правилами для всех проектов на https://github.com/insales/code_style.
# Сюда вносим только те изменения, которые по каким-то причинам не хотим вносить во все проекты.
AllCops:
  TargetRubyVersion: 3.2
  TargetRailsVersion: 7.1

```
