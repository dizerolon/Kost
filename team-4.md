# team-4: Создание БД маркетплейса

**Описание:** Спроектировать базу данных для маркетплейса, реализовать SQL-таблицы, наполнить их тестовыми данными (фикстурами) и контейнеризировать всё в Docker для удобства запуска и тестирования. 

#### Часть 1: Проектирование и создание базы данных
1. Создайте SQL-скрипт, который создаёт необходимые таблицы для маркетплейса.
   - Минимальный набор таблиц должен включать:
     - **Пользователи** (id, имя, email, дата регистрации)
     - **Продавцы** (id, название компании, описание, дата регистрации)
     - **Товары** (id, название, описание, цена, id_продавца)
     - **Заказы** (id, id_пользователя, дата заказа, общая сумма)
     - **Элементы заказа** (id, id_заказа, id_товара, количество, цена)
2. Добавьте первичные и внешние ключи для установления связей между таблицами (например, связь между пользователями и заказами).
3. Добавьте ограничения на уникальность, не-`null` поля, а также создайте индексы, где это необходимо.

#### Часть 2: Заполнение фикстурами
1. Создайте SQL-скрипт с фикстурами для наполнения таблиц тестовыми данными.
   - Добавьте минимум 20 пользователей, 10 продавцов, 20 товаров и 15 заказов.
   - Учтите связи между таблицами, например, чтобы у заказа был реальный пользователь и связанные товары.
2. Скрипт должен обеспечивать успешное выполнение при запуске без ошибок.

#### Часть 3: Контейнеризация с Docker
1. Создайте `Dockerfile` для настройки контейнера с базой данных (например, на основе образа PostgreSQL или MySQL).
   - Убедитесь, что ваш `Dockerfile` настраивает базу данных и автоматически применяет SQL-скрипты для создания таблиц и их заполнения.
2. Создайте `docker-compose.yml` файл, чтобы упростить запуск контейнера с базой данных.
   - Контейнер должен быть доступен для подключения, чтобы можно было протестировать базу данных через SQL-клиент.

#### Примерный результат
После выполнения должен быть репозиторий с:
- SQL-скриптом для создания таблиц (`schema.sql`).
- SQL-скриптом для наполнения фикстурами (`fixtures.sql`).
- `Dockerfile` для контейнеризации базы данных.
- `docker-compose.yml` для запуска проекта.
