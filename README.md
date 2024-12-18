# Linux onboarding on MIPT
И ещё пример использования mkdocs.

mkdocs это утилита, позволяющая создавать статические сайты из файлов markdown, которые в основном используются для документации.

## Как использовать

Нужен Python и возможность устанавливать в него пакеты, то есть venv, mamba или что-то ещё, а не голый Python, поскольку в таком случае pip откажется работать.

```
$ pip install mkdocs
```

Собрать проект после этого:

```
$ cd doc && mkdocs build
```

Выходная директоря ./doc/site.

## Как делать свою документацию

В mkdocs.yml описана структура сайта, тема и другие переменные. В данном примере было решено использовать директорию md как хранилище исходных markdown-файлов (переменная docs_dir).

Не рекомендуется менять переменную site_dir, если не хотите, чтобы мой пайплан публикации на nginx сломался...

## Документация mkdocs
Лежит тут: https://www.mkdocs.org

## CI/CD документации

В директории .github лежит сценарий, который выполняет push в репозиторий "публикации". Его необходимо настроить, а именно поменять данные на свои и добавить в репозиторий токен Github.

https://github.com/marketplace/actions/push-a-directory-to-another-repository

Токен создается в Settings (пользователь) -> Developer Settings -> Personal access tokens -> Tokens. Минимальные права это repo (на самом деле меняются в зависимости от типа репозитория).

Токен нужно добавить в Settings (в репозитории) -> Secrets and variables -> Actions. Использовать имя из сценария.

Теперь при push (в репозиторий документации) будет делаться push (в репозиторий публикации), который сделает push (на сервер с nginx)...
