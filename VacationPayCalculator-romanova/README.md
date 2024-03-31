# Приложение "Калькулятор отпускных"

---

## Задание

Микросервис на SpringBoot + Java 11 c одним API:
GET "/calculate"

Минимальные требования: Приложение принимает твою среднюю зарплату за 12 месяцев и количество дней отпуска - отвечает суммой отпускных, которые придут сотруднику.

Доп. задание: При запросе также можно указать точные дни ухода в отпуск, тогда должен проводиться рассчет отпускных с учётом праздников и выходных.

---
# Реализованные классы

----
## 1. Точка входа для приложения Spring Boot: CalculatorApplication

Класс для работы с приложением Spring Boot.

----
## 2. Контроллер Spring Boot: VacationCalculatorController

Класс создан для обработки HTTP-запросов, связанных с расчетами отпуска.

---
### Реализованные методы

- `input(humans, csvFilePath, separator)`: считывания данные о людях из CVS файла в список

---
## 3. Сервис Spring Boot: VacationCalculatorService

Класс рассчитывает общую сумму отпускных на основе средней заработной платы и количества рабочих дней между двумя датами.

---
### Реализованные методы

- `calculateVacationSum`: Вычисление общей суммы отпускных для данного запроса.
- `getWorkingDaysBetweenTwoDates`: Вычисляет количество рабочих дней между двумя датами.
---
## 4. Конфигурациями отпусков: HolidayConfiguration

Класс предназначен для управления конфигурациями отпусков для приложения калькулятора отпусков.

---
### Реализованные методы

- Статический блок, который считывает данные праздничных дней из файла JSON.
- `isHoliday`: проверяет, является ли данная дата праздничной, проверяя, существует ли она в HOLIDAYS наборе.

---
## 5. DTO: VacationCalculationRequest

Класс для инкапсуляции данных.

---
### Реализованный методы

- Геттеры и сеттеры
