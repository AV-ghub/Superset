List самых полезных и наглядных ресурсов, сгруппированный по категориям:

### 1. Официальные ресурсы (Fundamentals)

*   **Официальная документация Apache Superset:**
    *   [Tutorials — Apache Superset](https://superset.apache.org/docs/tutorials) — базовые уроки от создателей.
    *   [Videos — Apache Superset](https://superset.apache.org/docs/videos) — подборка видео с официального канала.
    *   *Плюсы:* Самая актуальная информация. *Минусы:* Не всегда самые сложные кейсы.

*   **Официальный YouTube-канал Apache Superset:**
    *   [Apache Superset YouTube Channel](https://www.youtube.com/c/ApacheSuperset) — записи с митапов, демо новых фич.

### 2. Лучшие YouTube-каналы (Визуальное обучение)

*   **Preset (Коммерческая компания основателей Superset):**
    *   [Preset YouTube Channel](https://www.youtube.com/c/PresetIO) — **Это самый ценный ресурс.** Здесь регулярно публикуются подробные туториалы и лучшие практики (Best Practices) от самих создателей и core-контрибьюторов Superset. Ищите видео от Max Beauchemin, Elizabeth Thompson, Beto Dealmeida.

*   **Data with Adams:**
    *   [Data with Adams - Superset Playlist](https://www.youtube.com/playlist?list=PLTP_wg-pA-1eTxL7uXSW16i3Ba51F4hnH) — Очень понятные и практичные скринкасты по созданию дашбордов.

### 3. Продвинутые блоги и статьи (Глубокое погружение)

*   **Preset Blog:**
    *   [Preset Blog](https://preset.io/blog/) — **Золотая жила.** Десятки статей на тему: "Как сделать X в Superset", разбор архитектуры, примеры сложных дашбордов.

*   **Towards Data Science (на Medium):**
    *   Поищите по тегу "Apache Superset". Часто публикуются кейсы и туториалы от data-инженеров из крупных компаний.

### 4. Книги (Систематизированные знания)

Прямо сейчас нет книги, которая бы целиком и полностью была посвящена Superset на продвинутом уровне. Однако, основы работы с данными и визуализацией хорошо описаны в:
*   **"Fundamentals of Data Visualization" by Claus O. Wilke** — чтобы делать не просто рабочие, но и эффективные дашборды.
*   **Книги по SQL** — так как умение писать эффективные запросы это 80% успеха в Superset.

### 5. Практика и сообщество

*   **GitHub Discussions:**
    *   [Apache Superset GitHub Discussions](https://github.com/apache/superset/discussions) — Здесь можно задать конкретный вопрос и получить ответ от разработчиков. Просмотр чужих обсуждений невероятно полезен.
*   **Stack Overflow:** Используйте тег `[apache-superset]`.

---

### На что specifically обратить внимание в туториалах:

Чтобы выйти на продвинутый уровень, ищите материалы, которые раскрывают эти темы:

1.  **Advanced Dashboard Interactions:**
    *   Кросс-фильтрация (Cross-Filters), настройка Filter Scopes.
    *   Использование чартов в качестве фильтров (Chart-based Filtering).
    *   Создание каскадных (зависимых) фильтров.

2.  **Advanced SQL & Jinja Templating:**
    *   Параметризованные запросы с `Jinja2`.
    *   Использование `{{ url_param() }}`, `{{ filter_values() }}`, `{{ current_user_id() }}`.
    *   Динамическое управление запросами на основе действий пользователя.

3.  **Security and Deployment:**
    *   Настройка Row Level Security (RLS).
    *   Управление ролями и разрешениями.
    *   Best practices по производительности больших дашбордов.

4.  **Customization:**
    *   Добавление собственных CSS-стилей для дашбордов.
    *   Разработка собственных визуализаций (если у вас есть навыки фронтенд-разработки).

**Итог:** Начните с **канала Preset на YouTube** и **их блога** — это даст вам самый большой скачок в понимании возможностей Superset. Затем для решения конкретных проблем используйте **GitHub Discussions**.
