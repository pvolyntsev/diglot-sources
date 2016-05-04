# diglot-sources
Works, articles and books for [Diglot service](https://github.com/pvolyntsev/diglot)

Сервис позволяет работать со статьями через github, автоматически обновляя содержимое статей при изменении репозитория.

Для добавления материалов в сервис необходимо

1. Зарегистрироваться на http://diglot.copist.ru/
2. Включить в настройках учётной записи http://diglot.copist.ru/profile/integration интеграцию со своей учётной записью на github.com
3. Сделать новый репозиторий, в корне которого разместить индексный файл `diglot.ini`
    Содержимое файла `diglot.ini`
    ```
    [branch]
    published
    
    [article]
    my-article-name
    ```
4. Создать директорию `my-article-name`, в которой разместить три файла: `meta.ini` `original.md` `translation.md`
    Содержимое файла `meta.ini`
    ```
    [original]
    language=english
    title=Original Article Name
    url=http://example.com/original-article-url
    author=Jonh Smith
    home=http://jonh.smith.me/
    
    [translation]
    language=russian
    title=Название статьи в переводе
    url=http://example.ru/адрес-статьи
    author=Иван Степанов
    home=http://ivan.stepanov.ru/
    ```
5. Создать ветку `published` и "подтягивать" туда изменения статей. Сервис [Diglot service](https://github.com/pvolyntsev/diglot) будет брать изменения только из этой ветки. Название ветки может быть изменено на другое; имя ветки надо указать в индексном файле `diglot.ini` в секции `[branch]`

