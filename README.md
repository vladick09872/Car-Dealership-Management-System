# 🚗 Car Dealership Management System

Car Dealership Management System — это полноценное Spring Boot приложение для управления автосалоном.  
Оно позволяет управлять автомобилями, покупателями, покупками и тест-драйвами.  
Проект интегрирован с Keycloak для авторизации и аутентификации, а также поддерживает Swagger UI для удобного тестирования API.

---

## 📸 Скриншот Swagger UI

![![Знімок екрана 2025-06-29 225045.png]![Image](https://github.com/user-attachments/assets/c6595ce5-7438-479c-9c39-b3ac90ed3b5e))
> Пример: список всех доступных эндпоинтов с авторизацией Keycloak

---

## 🔧 Технологии

- Java 17
- Spring Boot 3
- Spring Security + Keycloak
- Spring Data JPA + Hibernate
- Lombok
- Swagger (Springdoc OpenAPI)
- JUnit + Mockito

---

## 📦 Функционал

### 🔐 Аутентификация и роли через Keycloak:
- ROLE_ADMIN – полный доступ
- ROLE_MANAGER – частичный доступ
- ROLE_CUSTOMER – доступ к клиентским операциям

---

### 📁 Сущности:
- Car – автомобиль (title, price, inStock и т.д.)
- Customer – покупатель
- Purchase – покупка автомобиля
- TestDriveRequest – заявка на тест-драйв

---

### 📲 Основные эндпоинты

#### 🚘 Автомобили
- GET /cars — получить список авто
- POST /cars — добавить авто (только ADMIN)
- PUT /cars/{id} — обновить авто (ADMIN, MANAGER)
- DELETE /cars/{id} — удалить авто (ADMIN)

#### 👤 Покупатели
- GET /customers
- POST /customers
- GET /customers/{id}

#### 💸 Покупки
- POST /purchases/{carId}/customer/{customerId} — купить авто
- GET /purchases
- GET /purchases/customer/{id}

#### 🧪 Тест-драйвы
- POST /test-drives/{carId}/customer/{customerId} — создать заявку
- GET /test-drives
- GET /test-drives/car/{carId}
- DELETE /test-drives/{id} — отмена

---

## 🧪 Тестирование

Проект покрыт юнит-тестами:

- Service слои протестированы с @ExtendWith(MockitoExtension.class)
- Используются Mockito, JUnit 5

---

## 🚀 Запуск проекта

1. Установите PostgresSQL и создайте БД:
   `sql
   CREATE DATABASE car_dealership;
