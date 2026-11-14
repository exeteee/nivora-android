# Подготовка сборки Nivora

Сейчас в репозитории лежит исходный код. APK ещё не собран и не проверен на Tecno Spark Go 2024. Для первой тестовой сборки нужны три вещи: собственный Telegram API ID/API hash, отдельный Firebase-конфиг и секреты GitHub.

## 1. Получить API ID и API hash Telegram

1. Откройте [my.telegram.org](https://my.telegram.org/) и войдите в свой Telegram-аккаунт.
2. Перейдите в **API development tools**.
3. Создайте приложение с названием `Nivora`, платформой Android и описанием вроде `Unofficial Android client`.
4. Сохраните выданные `api_id` и `api_hash`.

Код входа Telegram и пароль двухэтапной проверки никому не отправляйте. Вводите их только на официальном сайте Telegram. Не присылайте мне API-данные в чат.

## 2. Создать отдельную Firebase-конфигурацию

Firebase нужен для push-уведомлений, когда приложение закрыто.

1. Откройте [Firebase Console](https://console.firebase.google.com/) и создайте собственный проект Nivora.
2. Добавьте Android-приложение с точным package name: `com.nivora.chat`.
3. Включите Firebase Cloud Messaging.
4. Скачайте созданный файл `google-services.json`.

Не используйте конфиги из исходников Telegram: они удалены из текущей ветки, чтобы Nivora не подключался к чужому Firebase-проекту.

## 3. Сохранить настройки в GitHub Secrets

Откройте репозиторий [exeteee/nivora-android](https://github.com/exeteee/nivora-android), затем:

**Settings → Secrets and variables → Actions → New repository secret**

Создайте секреты с точными именами:

| Имя секрета | Что вставить |
|---|---|
| `NIVORA_API_ID` | Числовой `api_id` с my.telegram.org |
| `NIVORA_API_HASH` | `api_hash` с my.telegram.org |
| `GOOGLE_SERVICES_JSON` | Полное содержимое скачанного `google-services.json` |

Дополнительно можно добавить `NIVORA_MAPS_API_KEY` — собственный ключ Google Maps SDK for Android. Без него экранные карты могут не загружаться; для сборки обычной переписки он необязателен.

Не добавляйте эти значения в README, исходный код или обычные сообщения. Файл Firebase вставляйте целиком, включая фигурные скобки.

## 4. Запустить тестовую сборку

После добавления секретов откройте вкладку **Actions** репозитория и выберите **Build Nivora Android APK**. Workflow проверит исходники, соберёт вариант `AfatDebug` и приложит APK как artifact с именем `nivora-debug-apk`.

Сборка Debug предназначена только для первой проверки и не является финальной версией для распространения. Перед раздачей друзьям нужен отдельный постоянный release-keystore, чтобы последующие APK могли обновлять предыдущие без удаления приложения.

## Что уже изменено

- Название приложения — Nivora (в английской и русской локали).
- Package name — `com.nivora.chat`, чтобы Nivora устанавливался отдельно от официального Telegram.
- В настройках убраны пункты Telegram Premium и Telegram Business, а также напоминание о Premium.
- Добавлена стартовая светлая палитра в стиле iOS.
- Telegram API ID/hash берутся из настроек сборки, а не из исходного кода.
- Чужие Firebase JSON, Google Maps key и тестовый release-keystore убраны из текущего состояния ветки.

## Что ещё не готово

Полный аудит всех упоминаний и рекламных экранов Premium во всём приложении ещё не завершён. Дополнительные функции, глубокая переработка интерфейса, тесты на реальном устройстве и release-подпись впереди. Не считайте текущую ветку готовым APK.
