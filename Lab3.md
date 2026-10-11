# Вариант 1: «Анализ телеметрии датчиков умного дома» (IoT)
**Описание задания:**
Вам предоставлен список строк, содержащих показания датчиков температуры в комнатах за день (например, "22.5", "31.0", "18.4" и т.д.). Необходимо написать программу, которая обрабатывает этот массив данных с помощью функций и циклов.

Требования к программе:
* Функция convertToCelsius(rawList: List<String>): List<Double> — принимает список строковых значений, преобразует их в числа (Double), пропуская некорректные данные (например, пустые строки или ошибки парсинга).
* Функция calculateAverage(temperatures: List<Double>): Double — рассчитывает среднюю температуру по дому с помощью арифметических операций.
* Условия и циклы (for и if/else/when):
- Пройти циклом по полученному списку температур.
- Если температура выше 28.0, вывести предупреждение: "Внимание: перегрев!".
- Если ниже 18.0, вывести: "Холодно, включите отопление".
- В остальных случаях статус в норме.

Шаблон для Kotlin Playground:
```
fun main() {
    val sensorLogs = listOf("22.5", "31.0", "17.5", "abc", "24.0", "29.5", "16.8")

    // реализуйте функцию convertToCelsius
    val validTemps = convertToCelsius(sensorLogs)
    println("Валидные показания: $validTemps")

    // реализуйте функцию calculateAverage
    val avg = calculateAverage(validTemps)
    println("Средняя температура: $avg")
    
    println("\nАнализ состояния комнат:")
    for (temp in validTemps) {
        // Добавьте условную логику (if/else или when) для вывода статуса
    }
}
```


# Вариант 2: «Инвентарь и боевая система RPG-персонажа» (Геймдев)
**Описание задания:**
Разработать программу для анализа инвентаря игрока. Дан список названий предметов и список их базовой ценности (в золоте).

Требования к программе:
*Функция validateItemName(name: String): Boolean — проверяет название предмета: оно должно содержать не менее 4 символов и не начинаться с цифры (работа со строками).
*Функция calculateTotalLoot(values: List<Int>, multiplier: Double): Double — с помощью цикла и арифметических операций рассчитывает общую стоимость инвентаря с учетом множителя редкости.
* Условия (when):
- Распределить предметы по категориям в зависимости от их ценности (например: ценность > 100 — "Эпический", от 50 до 100 — "Редкий", ниже 50 — "Обычный").

Шаблон для Kotlin Playground:
```
fun main() {
    val items = listOf("Sword", "Shield", "123Potion", "Bow", "Axe")
    val itemValues = listOf(120, 80, 40, 95, 30)
    
    val rarityMultiplier = 1.25 // Множитель для расчета стоимости

    println("Проверка названий предметов:")
    for (item in items) {
        // Реализуйте validateItemName
        val isValid = validateItemName(item)
        println("Предмет '$item' корректен? $isValid")
    }

    // реализуйте calculateTotalLoot
    val totalCost = calculateTotalLoot(itemValues, rarityMultiplier)
    println("\nИтоговая стоимость инвентаря с учетом множителя: $totalCost")
}
```

# Вариант 3: «Расчет стоимости доставок интернет-магазина» (Логистика)
**Описание задания:**
Дан список расстояний доставок (в километрах) и типов транспорта. Необходимо рассчитать стоимость каждой доставки и общую сумму выручки логистической компании.

Требования к программе:
* Функция calculateDeliveryCost(distanceKm: Double, transportType: String): Double — рассчитывает стоимость по формуле: базовая ставка за километр умножается на расстояние.
* Ставка зависит от транспорта (when): "Bike" — 15 руб/км, "Car" — 40 руб/км, "Drone" — 60 руб/км.
* Функция filterLongDeliveries(distances: List<Double>, threshold: Double): Int — с помощью цикла считает, сколько доставок превышают заданное пороговое значение (например, больше 50 км).
* Арифметика и циклы: Вывести общую сумму всех доставок и среднее расстояние.
  
Шаблон для Kotlin Playground:
```
fun main() {
    val distances = listOf(12.5, 55.0, 5.0, 82.3, 30.0)
    val transports = listOf("Bike", "Car", "Bike", "Drone", "Car")

    println("Детали заказов:")
    for (i in distances.indices) {
        // реализовать calculateDeliveryCost
        val cost = calculateDeliveryCost(distances[i], transports[i])
        println("Заказ ${i + 1}: ${distances[i]} км на транспорте ${transports[i]} стоил $cost руб.")
    }

    // реализовать filterLongDeliveries
    val longTripsCount = filterLongDeliveries(distances, 50.0)
    println("\nКоличество доставок свыше 50 км: $longTripsCount")
}
```
