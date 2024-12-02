# Продвинутый bash

## Ввод-вывод и конвейеры
```
<
```
перенаправление stdin.

```
>
```
перенаправление stdout.

```
|
```
перенаправление с помощью конвейера вывода одной команды на вход другой команды.

## BusyBox

Подробнее: https://ru.wikipedia.org/wiki/BusyBox


Больше примеров:
https://habr.com/ru/companies/ruvds/articles/445270/

### head

### tail

### grep

### tar
```
$ tar -zxvf tar.gz
```

“-zxvf” - первое, что приходит в голову, когда линуксоид слышит tar. Это набор ключей, который позволяет распаковать сжатый tar, например, tar.gz.

```
z means (un)z̲ip.
x means ex̲tract files from the archive.
v means print the filenames v̲erbosely.
f means the following argument is a f̱ilename
```

Вместо gz может быть другой вариант архивации. Сам по себе tar это просто сбособ записать файлы в один файл, но сжатие не происходит, поэтому требуется еще добавить, например, gz.

## Больше утилит
### shred
### tac
### wget
### less
### which
### wc
### sort
### time

## Мониторинг и управление процессами
### htop, top

## Облегчение жизни
### Запуск нескольких процессов
* Через отправку в фон


* Через xargs


* Через несколько терминалов

tmux, screen
