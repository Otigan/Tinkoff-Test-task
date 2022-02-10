# Тестовое задание Тинькофф
## Требования
1. На главном экране приложения отображается gif-изображение вместе с его
описанием, полученным с сайта developerslife.ru (детали работы с API — ниже) *
2. Под изображением располагаются две кнопки:
2.1. Одна (кнопка «следующий») загружает следующий рандомный пост
(вызывая метод API).
2.2. Вторая — позволяет вернуться к предыдущему посту, который мы
сохранили в кэш после загрузки.
2.3. Получается такая структура: (изначально кнопка назад не активна, но уже
есть какой-то пост, загруженный при старте) нажимаем на «следующий» →
появляется пост и кнопка назад становится активна → нажимаем на
«следующий» ещё раз → появляется новый пост и обе кнопки активны →
нажимаем назад и попадаем на один пост назад (обе кнопки активны) →
нажимаем ещё раз и попадаем на первую картинку (кнопка назад стала не
активна снова). Теперь если кликнуть на «следующий» мы сначала должны
пройти те посты, которые у нас были загружены, а потом как они кончатся
— загружать новые.
3. Ответы от API должны быть закешированы хотя бы на время сессии для
реализации переходов «назад».
4. Должны быть предусмотрены различные состояния загрузки данных: ошибка
загрузки, загрузка и успешная загрузка.
Будет здорово (но не обязательно), если вы позаботитесь о следующем:
- Приложение будет написано на языке Kotlin
- Общая плавность и стабильность приложения
- Возможность отображать gif-изображения из трех разных категорий сайта: горячее,
последнее, популярное
- GET http://developerslife.ru/ <раздел>/<номер страницы>?json=true
 Виды разделов:
- latest — последние
- hot — горячие
- top — лучшие
Пример: https://developerslife.ru/latest/0?json=true
- UNIT-тесты
- Анимации
* Примечания к реализации:
 - Для работы с gif-изображениями рекомендуется использовать Glide
 - Для получения постов необходимо использовать следующий метод: GET https://developerslife.ru/random?json=true


## Что было реализовано
- Приложение написано на языке Kotlin
- Загрузка гиф-изображений из трех категорий DevelopersLife
- Обработка ошибок со стороны сервера
- Наличие анимации для ViewPager2
- Unit-тесты для PagingSource
