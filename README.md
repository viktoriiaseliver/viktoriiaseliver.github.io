# Страницы приложений

Публичный репозиторий ровно под одно: политику приватности и поддержку.
Их требует App Store Review (5.1.1) и Beta App Review, а адрес должен быть
живым и открываться без входа. Исходники приложений остаются закрытыми —
здесь только страницы.

## Почему именно такое имя репозитория

Репозиторий называется `viktoriiaseliver.github.io` — это **сайт
пользователя** GitHub Pages, он публикуется по адресу
`https://viktoriiaseliver.github.io/`. Папка `timer-app/` внутри отдаёт
`https://viktoriiaseliver.github.io/timer-app/privacy.html` — **ровно те
адреса, которые уже зашиты в приложении** (`Shared/AppInfo.swift`,
`AppLinks`). Менять в коде ничего не нужно.

Если когда-нибудь понадобится открыть сам репозиторий `timer-app` и
включить в нём Pages — он перехватит путь `/timer-app/` на себя. Тогда
папку отсюда можно удалить.

## Как опубликовать (один раз)

1. Создать на GitHub **публичный** пустой репозиторий с именем
   `viktoriiaseliver.github.io` (без README — он уже здесь).
2. В этой папке:

   ```bash
   git remote add origin git@github.com:viktoriiaseliver/viktoriiaseliver.github.io.git
   git push -u origin main
   ```

3. Pages для сайта пользователя включаются сами. Через минуту проверить:

   ```bash
   curl -s -o /dev/null -w "%{http_code}\n" https://viktoriiaseliver.github.io/timer-app/privacy.html
   ```

   Должно быть `200`.

## Что здесь лежит

| Папка | Приложение | Формат |
|---|---|---|
| `timer-app/` | Five More Minutes | HTML, ru + en |
| `gamut/` | Gamut | Markdown, Jekyll превращает в HTML |
| `_style.css` | общий стиль | светлая и тёмная тема |

Файла `.nojekyll` здесь нет намеренно: без Jekyll страницы Gamut остались
бы markdown-текстом.

## Того

Страниц Того здесь пока нет — у него свой домен. Когда понадобится,
завести папку `togo/` рядом и добавить ссылку в `index.html`.
