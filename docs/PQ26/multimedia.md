# МУЛЬТИМЕДИА

### Изменение звучания Swing/Bolero (Arkamys)
!!! note ""
    Arkamys будет звучать правильно только если в магнитоле есть соответствующая параметрия. Заливается VCP или ODIS, файл этой параметрии недоступен.

```
Блок 5F → Длинное кодирование  
> Байт 11 — бит 2 → включить (добавляются пункты Skoda Surround и Virtual Subwoofer)
> Байт 08 – бит 6 - VDA Low Frequency Input → включить
→ Применить
```

### Изменение стартовой заставки Swing/Bolero
```
Блок 5F → Длинное кодирование  
> Байт 18 → меняем значение 00 на предпочтительное
01-vRS
02-SCOUT
03-Laurin & Klement
04-GreenLine
07-MonteCarlo (на свинг 2 и 3)
08-SportLine (только на свинг 3))
→ Применить
```
После сохранения кодировки необходимо применить новое значение перезагрузкой магнитолы (на свинге - продолжительным удержанием кнопки включения).  
При очередном первичном включении магнитолы (после снятия с сигналки) наблюдаем новую заставку.

### Деактивация AM диапазона в ГУ Swing/Bolero
```
Блок 5F → Длинное кодирование  
> Байт 14 – бит 1 → включить
```

### Изменение вида отображения автомобиля в меню «Состояние автомобиля»
```
Блок 5F → Длинное кодирование  
> Байт 01 – биты 0~23:
– 035201, модель: Skoda Rapid
– 035203, модель: Skoda Rapid Spaceback
- 035331, модель: Skoda Rapid FL (NH3)
– 036200, модель: Skoda Fabia
– 036202, модель: Skoda Fabia Combi
– 037301, модель: Skoda Octavia лифтбек
– 038401, модель: Skoda Superb лифтбек
→ Применить
```

### Изменение времени отображения заставки при включении магнитолы
```
Блок 5F → Адаптация 
> Time display for start screen → 2.0 s - выставляем нужное
→ Применить
```
> 20103

### Активация динамиков задних дверей после самостоятельной доустановки (Swing/Bolero/Amundsen)
```
Блок 5F → Длинное кодирование
> Байт 04 – биты 0~31 → выбираем
- ВЕ000000 (4 канала / 6 пассивных динамиков)
Если в задние двери установлена 2-х компонентная акустика с твитерами, соответственно выбираем:
— FF000000 (4 канала / 8 пассивных динамиков).
→ Применить
```

### Активация низкочастотного аналогового входа AUX-IN
```
Блок 5F → Длинное кодирование
> Байт 8 – бит 4 → включить
→ Применить
```

### Активация USB-входа
```
Блок 5F → Длинное кодирование
Байт 19 – биты 6~7 → выбираем значение
- 80 (USB функциональность) или
- С0 (USB и iPhone функциональность)
→ Применить
```

### Изменение чувствительности микрофона
```
Блок 5F → Адаптация 
> Microphone sensitivity → 0 dB – выставить необходимое значение.
→ Применить
```
* Отрицательное значение установленное в этом параметре будет увеличивать громкость сигнала с микрофона. Чем меньше отрицательное значение, тем больше усиление.
> 20103

### Показания БК при выключенном зажигании
```
Блок 5F → Адаптация 
> Car_Function_Adaptations_Gen2-menu_display_board_computer_clamp_15_off → переключить с not activated, на activated
→ Применить
```
> 20103

### Режим автошколы на Swing/Bolero
```
Блок 5F → Адаптация 
> Car_Function_Adaptations_Gen2-menu_display_driving_school → переключить с not activated на activated
> Car_Function_Adaptations_Gen2-menu_display_driving_school_over_threshold_high → переключить с not activated на activated
> Car_Function_List_CAN_Gen2-Driving_school → переключить с Not available на available
> Car_Function_List_CAN_Gen2-Driving_school_msg_bus → переключить с Not available на Comfort data bus
→ Применить
```
> 20103

### Активация режима «Бездорожье» Swing 3
```
Блок 5F → Адаптация 
> Car_Function_Adaptations_Gen2 - menu_display_compass_clamp_15_off → активир.
> Car_Function_Adaptations_Gen2 - menu_display_compass_over_threshold_high → активир.
> Car_Function_Adaptations_Gen2 - menu_display_compass → активир.
→ Применить
```
> 20103

### Активация Инженерного меню (Engineering Testmode) Swing 2
Только с использованием VAS5054 и ODIS-E
```
Запускаем программу ODIS-E
Выбираем проект (SK25X или SK26X) → пуск
Выбираем блок 5F → Diagnostic session (Сессия диагностики)
в открывшемся окошке выбираем:
Development mode (режим разработчика) → Execute (выполнить)
Далее: Adaptation/parameter (Адаптация) →
Developer mode (режим разработчика) → вводим значение Activated
```
Настройка параметров звука в Инженерном меню:  
Запуск инженерного меню производится продолжительным удержанием кнопки Setup до появления на экране меню: Engineering Testmode.   
Выбираем: Software System - Audio Management →   
в пункте Loudness ставим галочку   
далее выбираем: Input Gain Offset и в пунктах ниже увеличиваем уровень на 13 дБ   
* FM source — +12   
* Media File Player — +9   
* BT audio — +13   
Выходим из Инженерного меню и в настройках звука при необходимости подстраиваем баланс и эквалайзер.   
После завершения всех звуковых настроек Инженерное меню целесообразно деактивировать. Есть мнение, что в активированном состоянии оно разряжает аккумуляторную батарею.