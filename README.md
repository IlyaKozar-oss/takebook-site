# Смотри тут / Smotri tut — лендинг и документы

Публичный сайт Smotri tut на английском и «Смотри тут» на русском. Сборка Jekyll и публикация GitHub Pages запускаются при каждом push в `main`.

## Адреса

| Страница | English | Русский |
| --- | --- | --- |
| Главная | https://jelliedfish-oss.github.io/takebook-site/ | https://jelliedfish-oss.github.io/takebook-site/ru/ |
| Privacy Policy | https://jelliedfish-oss.github.io/takebook-site/privacy/ | https://jelliedfish-oss.github.io/takebook-site/ru/privacy/ |
| Terms of Use | https://jelliedfish-oss.github.io/takebook-site/terms/ | https://jelliedfish-oss.github.io/takebook-site/ru/terms/ |
| Support | https://jelliedfish-oss.github.io/takebook-site/support/ | https://jelliedfish-oss.github.io/takebook-site/ru/support/ |

Переключатель EN/RU сохраняет текущую страницу: например, `/privacy/` переключается на `/ru/privacy/`.

## Добавление контента

1. Английские документы: `privacy.md`, `terms.md`, `support.md`. Русские: `ru/privacy.md`, `ru/terms.md`, `ru/support.md`.
2. Сохраните настройки между двумя строками `---`. Добавьте окончательный текст после второго `---`.
3. После согласования текста измените `draft_notice: true` на `draft_notice: false` для соответствующей языковой версии. При необходимости добавьте `updated: YYYY-MM-DD` с фактической датой документа.
4. Сохраните изменения в `main`. Workflow **Deploy GitHub Pages** автоматически опубликует их; дождитесь зелёного статуса в Actions.

Сейчас все документы содержат только уведомление «Здесь появится информация» / «Information will appear here» и закрыты от индексации. До отправки приложения в App Store нужно добавить окончательные тексты и реальные контакты.

## Переводы и структура

- `_data/translations.yml` — тексты лендинга, навигации и заглушек на обоих языках.
- `_includes/landing.html` — общий макет главной страницы.
- `_layouts/default.html` — навигация, переключение языка, метаданные и подвал.
- `assets/tokens.css` — токены Studio Navy из `TakebookStyle` приложения: обе цветовые темы, системная типографика, отступы 4/8/12/16/24/32 px, радиусы 10/12/14/16 px, минимальная область нажатия 44 px и основная кнопка 52 px.
- `assets/site.css` — адаптивная вёрстка и компоненты на этих токенах; крупный заголовок лендинга масштабируется для широкого экрана.
- `assets/brand-mark.png` — исходный `TakebookBrandMark` из приложения. Светлая/тёмная тема следует настройке системы.
- `_layouts/document.html` — макет документов.
- `index.html`, `ru/index.html` — точки входа двух версий.
- `404.html`, `ru/404.html` — страницы ошибки.
- `assets/site.css`, `assets/mark.svg` — оформление.
- `_config.yml` — GitHub Pages URL и базовый путь.
- `.github/workflows/pages.yml` — сборка и публикация.

## Подключение в приложении

Общая конфигурация `PhoneLegalLinks` используется на экранах телефона, пароля и профиля «Смотри тут». `TAKEBOOK_TERMS_URL`, `TAKEBOOK_PRIVACY_URL`, `TAKEBOOK_HELP_URL` в `TakebookDemoApp.xcconfig` ведут на разные русские страницы `/ru/terms/`, `/ru/privacy/`, `/ru/support/`, соответствующие текущему русскому интерфейсу приложения. На сайте можно переключить язык.

При смене GitHub-аккаунта или домена обновите `url` в `_config.yml`, remote репозитория и три адреса документов в конфигурации приложения. Ссылки приглашений и видеодублей требуют отдельного сервера и не относятся к юридическим страницам.

Сайт не требует базы данных, клиентского JavaScript, сторонних шрифтов или дополнительных секретов. Не добавляйте в публичный репозиторий пароли, API-ключи и приватные пользовательские материалы.
