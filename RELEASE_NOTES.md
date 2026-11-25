# Release v1.1.0 – Data Coupling & Updated Tariffs

## Added
- Додано спеціальний базовий тариф доставки `80.0` для міста `"Kyiv"`.
- Додано явний параметр ставки податку `tax_rate` зі значенням за замовчуванням `0.20` у функцію `process_standard_invoice`.

## Changed
- Збільшено коефіцієнт розрахунку вартості доставки за вагу з `12.0` до `15.0` за кілограм.
- Проведено архітектурний рефакторинг модуля: виконано перехід від Common, Stamp та Control Coupling до еталонного Data Coupling.

## Breaking Changes
- Видалено глобальну змінну стану `GLOBAL_TAX_RATE`.
- Змінено сигнатуру `calculate_delivery_cost`: замість об'єкта `CustomerProfile` тепер передається лише рядок `city`.
- Видалено єдину функцію `process_invoice` та керуючий прапорець `mode_flag`; логіку розділено на дві незалежні функції: `process_standard_invoice` та `process_tax_exempt_invoice`.
