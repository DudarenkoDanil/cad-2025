# Отчет о лаботаротоной работе

Оформленн отчёт по выполнению

## Цель работы

Освоение базовой конфигурации Spring-приложений на основе Java-классов и создание простого консольного приложения.  
Реализация загрузчика CSV-файлов и вывод данных товаров в виде таблицы в консоль.  
Получение навыков работы с зависимостями, конфигурацией и структурой проекта с помощью Gradle и Spring.

## Выполнение работы

1. Установлены JDK 17.0.14 (Axiom Standard/Temurin) и Gradle 8.12.  
2. С помощью команды `gradle init --package ru.bsuedu.cad.lab` создан проект `product-table` с параметрами:  
   - Язык: Java  
   - DSL: Kotlin  
   - Тестовый фреймворк: JUnit Jupiter  
3. Добавлена зависимость `org.springframework:spring-context:6.2.2` в `build.gradle.kts`.  
4. Реализован Java-конфиг класс с аннотацией `@Configuration` и `@ComponentScan` для автоматического поиска компонентов.  
5. Созданы классы для чтения CSV (`ResourceFileReader`), парсинга (`CSVParser`), предоставления данных (`ConcreteProductProvider`), и рендеринга (`ConsoleTableRenderer`).  
6. CSV-файл помещён в `src/main/resources`.  
7. При запуске через `gradle run` приложение корректно загружает данные из CSV и выводит таблицу с товарами в консоль.  
8. Проведено тестирование и успешное завершение приложения без ошибок.


# Вопросы для защиты

### 1. Spring. Определение, назначение, особенности
Spring — популярный Java-фреймворк для создания масштабируемых, модульных и тестируемых приложений. Основные возможности: инверсия управления (IoC), внедрение зависимостей (DI), аспектно-ориентированное программирование (AOP), поддержка различных модулей (Spring MVC, Data, Security).

### 2. Проблемы ручной сборки приложений
Ручная сборка сложна, подвержена ошибкам, трудна в управлении зависимостями и повторяемости, снижает скорость разработки и поддержки.

### 3. Известные системы автоматической сборки
- **Maven** — декларативная сборка с POM, управление зависимостями, жизненный цикл проекта.
- **Gradle** — современная, гибкая система с Groovy/Kotlin DSL, быстрая и расширяемая.
- **Ant** — низкоуровневая, XML-ориентированная, требует больше ручной работы.
- **Make** — классика для C/C++ проектов, правило-ориентированная.

### 4. Типовая структура Java проекта
project-root/
├── src/
│ ├── main/java/ (исходный код)
│ ├── main/resources/ (ресурсы)
│ ├── test/java/ (тесты)
│ └── test/resources/ (ресурсы тестов)
├── build/
├── build.gradle/pom.xml

markdown

### 5. Типы зависимостей в Gradle
- **implementation** — для компиляции и runtime, скрыты от потребителей.
- **api** — доступны потребителям.
- **compileOnly** — только для компиляции.
- **runtimeOnly** — только для выполнения.
- **testImplementation** — для тестов.

### 6. Принцип инверсии управления (IoC)
Контейнер управляет созданием и связью объектов, а не код приложения. Позволяет снизить сцепление и повысить модульность.

### 7. Отличие IoC от внедрения зависимостей (DI)
IoC — общий принцип передачи контроля создания объектов контейнеру. DI — способ реализации IoC, при котором зависимости передаются объекту извне.

### 8. Принципы инверсии управления
- Контейнер создаёт и связывает объекты.
- Использование интерфейсов вместо конкретных классов.
- Внедрение зависимостей извне.
- Ослабленное сцепление.

### 9. Сцепление (Coupling) и связность (Cohesion)
- **Сцепление** — степень зависимости между модулями (лучше низкое).
- **Связность** — степень логической взаимосвязанности внутри модуля (лучше высокая).

### 10. Какой принцип внедрения зависимости использовать и почему
Внедрение через конструктор, т.к. обеспечивает иммутабельность, явность зависимостей и упрощает тестирование.

## Выводы

В ходе работы получен практический опыт настройки Spring-приложений с использованием Java-конфигурации и Gradle.  
Реализация загрузчика CSV-файлов и вывод данных в консоль демонстрирует принципы модульности и разделения ответственности.  
Полученные знания послужат основой для дальнейшей разработки более сложных веб-приложений с использованием Spring.