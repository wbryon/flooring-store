
# Flooring Store API

API для управления информацией о товарах и заказах в магазине напольных покрытий. Этот API предоставляет методы для работы с каталогом напольных покрытий, включая получение списка доступных покрытий и информации о каждом конкретном покрытии.

## Стек технологий

- **Kotlin** - основной язык программирования
- **SpringBoot 3**
- **OpenAPI 3.0** - стандарт для описания RESTful API
- **Swagger UI** - для визуализации и тестирования API

## Описание

`Flooring Store API` позволяет взаимодействовать с данными магазина напольных покрытий. Основные возможности:
- Получение списка напольных покрытий.
- Получение информации о конкретном напольном покрытии по идентификатору.

## Структура API

### Основные эндпоинты

- `GET /floors` - Возвращает список всех напольных покрытий.
- `GET /floors/{floor_id}` - Возвращает информацию о конкретном напольном покрытии по его идентификатору.

### Примеры запросов и ответов

#### Получение списка напольных покрытий

**Запрос**:
```http
GET /floors
```

**Ответ**:
```json
{
  "floors": [
    {
      "floor_id": "617cfebf-c483-43b3-9f70-87f8afad5ea6",
      "name": "паркетная доска Coswick",
      "floor_type": "engineered wood flooring"
    },
    ...
  ]
}
```

#### Получение информации о конкретном напольном покрытии

**Запрос**:
```http
GET /floors/{floor_id}
```

**Ответ**:
```json
{
  "floor_id": "617cfebf-c483-43b3-9f70-87f8afad5ea6",
  "name": "паркетная доска Coswick",
  "floor_type": "engineered wood flooring"
}
```

## Установка и запуск

### Шаг 1: Настройка проекта на Kotlin

В системе должны быть установлены **JDK 17** и **Maven**. Если используется IntelliJ IDEA, необходимо настроить проект для работы с Kotlin и добавить зависимости для **Spring Boot**.

### Шаг 2: Подключение Swagger

Добавление зависимостей для Swagger и OpenAPI в `pom.xml`:

```xml
<dependencies>
    <dependency>
        <groupId>org.springframework.boot</groupId>
        <artifactId>spring-boot-starter-web</artifactId>
    </dependency>
    <dependency>
        <groupId>org.springdoc</groupId>
        <artifactId>springdoc-openapi-ui</artifactId>
        <version>1.6.4</version>
    </dependency>
</dependencies>
```

### Шаг 3: Запуск проекта

Запуск приложения с помощью Maven:

```bash
mvn spring-boot:run
```

### Шаг 4: Доступ к Swagger UI

После запуска приложение будет доступно по адресу [http://localhost:8080/swagger-ui.html](http://localhost:8080/swagger-ui.html) для тестирования API.

## Структура OpenAPI спецификации

### Основные компоненты

- **Floor** - схема для одного покрытия
- **Floors** - массив объектов `Floor`
- **Error** - схема для обработки ошибок

### Пример структуры OpenAPI

Смотрим полный файл спецификации в проекте.
