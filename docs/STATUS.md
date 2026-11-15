# Статус проекта Nivora

## Текущее состояние

- Репозиторий: exeteee/nivora-android.
- Рабочая ветка: work/nivora-foundation.
- Пакет Android: com.nivora.chat.
- Draft PR: https://github.com/exeteee/nivora-android/pull/1.
- Есть Nivora-брендинг, иконка, начальная палитра и частичное удаление Premium-промо из настроек.
- Добавлен тестовый build workflow с временной официальной Telegram sample API парой; только для закрытой разработки.
- Firebase-конфиг необязателен для первоначальной сборки.

## Первая APK-сборка

- GitHub Actions run: https://github.com/exeteee/nivora-android/actions/runs/43662667275
- Итог: success.
- Artifact: nivora-debug-apk.
- В архиве APK: afat/debug/app.apk.
- Размер APK: 127,842,715 bytes.
- Сборка использует Telegram sample API pair (только тестирование), debug signing и не содержит настроенного собственного Firebase push.
- Артефакт ещё не установлен и не проверен на физическом TECNO SPARK Go 2024.

## Не завершено

- Не проверены логин, получение и отправка сообщений на тестовой API-паре.
- Push-уведомления требуют собственного Firebase-проекта.
- Не было проверки на физическом TECNO SPARK Go 2024.
- До распространения требуется собственный Telegram API ID/hash и постоянный release-keystore.
- UI и Premium-промо ещё требуют дополнительного аудита.
