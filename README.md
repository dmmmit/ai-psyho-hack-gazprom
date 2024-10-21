# Классификатор типа личности

Алгоритм, который автоматически анализирует данные пользователя из социальной сети и определяет его тип личности на основе выбранной типологии.

## Типология

| Тип   | Социальное направление | Способ принятия решений | Когнитивный стиль |
|-------|------------------------|-------------------------|-------------------|
| 1 Тип | Экстраверт              | Аналитический           | Ригидность         |
| 2 Тип | Интроверт               | Чувственный             | Гибкость           |

**Итоговый результат**: 1/2 + Э/И + А/Ч + Р/Г

> Возрастная категория + социальное направление + способ принятия решений + когнитивный стиль

## Подготовка данных

Для анализа используются **уже имеющиеся данные**, на основе которых **создаются новые признаки**.

> Например, среднее количество лайков на постах, использование характерных слов в тексте, стиль речи и т.д.

**Финальный вид данных**:

1. **Первая целевая**: Среднее количество лайков, количество постов, фото, друзей и групп.
2. **Вторая целевая**: Возраст, пол, разница в интересах.
3. **Третья целевая**: Эмбеддинги групп и постов, расстояния между ними.

## Работа с данными

1. **Первая целевая**: Обучение на указанных колонках с использованием алгоритма K-means. Объекты с неясной целевой переменной отбрасываются.
2. **Вторая целевая**: Рассчитывается разница в интересах через упоминание категорий, затем используется кластеризация.
3. **Третья целевая**: Текстовые данные переводятся в эмбеддинги, и рассчитываются расстояния между категориями.

## Telegram бот

Для удобного использования и тестирования алгоритма реализован Telegram-бот, который выполняет роль GUI. Бот написан с использованием фреймворка **Aiogram**.

