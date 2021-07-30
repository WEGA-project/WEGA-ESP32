# esp32wega
Web Electronic Garden Automatic on ESP32 mk project.
https://t.me/esp32wega

Содержание 
=================
<!--ts-->
* [Минимальные требования и знания](#what_to_know)
* [Схема подключения компонентов](#schema)
* [Что потребуется купить(ESP32, датчики, резисторы)](#what_to_buy)
* [Установка софта](#install)
  * [Arduino IDE](#arduino)
  * [Additional Boards Manager URLs](#boards_manager)
  * [Установка платы ESP32](#esp_board_install)
  * [Visual Studio Code configuration](#vscode)
  * [Проверка правильности выбранных настроек](#config-check)
* [Где искать помощь](#help)

<!--te-->

<a name="what_to_know"></a>

### Минимальные требования и знания

Для того, чтобы собрать этот миксер необходимо:

- Минимальные знания в электронике (знать что такое `+` или `GND`)
- Умение читать схему, да-да, именно читать, а не разглядывать и смотреть
- Знание, что такое паяльник и как с ним работать
- Понимание как соединить три проводка в одной точке
- Умение собирать компоненты по схеме
- Знать и уметь, как прошивать ардуину и вообще знать, что это такое
- Минимальные знания в программировании. Мы попытались минимизировать необходимость ковыряние в коде, но все же придется изменять некоторые значения, о которых речь пойдет ниже

Если, всего выше перечисленного или одного из выше перечисленного не знаешь, не умеешь, не понимаешь, найди человека, который соберет этот миксер за тебя.


<a name="schema"></a>
## Схема подключения
<a href="images/esp32-wega-v1.jpg"><img src="images/esp32-wega-v1.jpg" width="250"></a>

<a name="what_to_buy"></a>
## Компоненты для заказа
 1. Плата контроллера ESP32 https://aliexpress.ru/item/4000115960206.html
 1. Датчик влажности ATH10 https://aliexpress.ru/item/4000961263862.html
 1. Фоторезистор 5528 для измерения света https://aliexpress.ru/item/1125719348.html
 1. Датчик расстояния для измерения уровня https://aliexpress.ru/item/4000899658467.html
 1. Стабилизатор для питания контроллера MP1584E https://aliexpress.ru/item/32706897605.html
 1. Терморезистор 100кОм для компенсации ЕС https://aliexpress.ru/item/32865194243.html
 1. Водонепроницаемый ds18b20 датчик температуры корней https://aliexpress.ru/item/32832225749.html
 1. Монтажная плата https://aliexpress.ru/item/32546265487.html
 1. Провода и резисторы ...


### Установка софта(Install software)

<a name="arduino"></a>
#### Arduino IDE
[Install Arduino IDE](https://www.arduino.cc/en/software)

Запускаем Arduino IDE, прописываем путь к `Additional Boards Manager URLs` для нашей ESP, устанавливаем нашу плату(board)

<a name="boards_manager"></a>
**Additional Boards Manager URLs**

File -> Preferences

<a href="images/prefs.png"><img src="images/prefs.png" width="250"></a>

Вставляем ссылку на конфиг и нажимаем OK.

`https://raw.githubusercontent.com/espressif/arduino-esp32/gh-pages/package_esp32_dev_index.json`

<a href="images/esp_json.png"><img src="images/esp_json.png" width="250"></a>

<a name="esp_board_install"></a>
**Установка платы ESP32**

Tools -> Board -> Board managers

<a href="images/select_esp_board.png"><img src="images/select_esp_board.png" width="250"></a>

Ищем `ESP32`, выбираем версию 1.0.6 и нажимаем `intstall`

<a href="images/esp_install.png"><img src="images/esp_install.png" width="250"></a>

Изначальное конфигурирование Arduino IDE закончено

Для поддержки платы в Windows необходимо установить драйвер USB http://www.wch.cn/downloads/CH341SER_ZIP.html

Вы можете пропустить следующий шаг если вы собираетесь использовать vscode как основной IDE

Выбираем правильную плату ESP

Tools -> boards manager -> ESP32 Arduino -> NodeMCU-32S

<a name="vscode"></a>
#### Visual Studio Code configuration
<details>
<p>

Если вы планируете использовать vscode как основную IDE для работы с файлами ардуины вам потребуется установить [arduino plugin](https://marketplace.visualstudio.com/items?itemName=vsciot-vscode.vscode-arduino) и сконфигурировать его для работы с вашей платой.

[Здесь видео пример как это сделать](https://www.youtube.com/watch?v=FnEvJXpxxNM)
</p>
</details>

## Компоненты для модуля измерения pH
 1. АЦП ADS1115 https://aliexpress.ru/item/32954034047.html
 1. Изолятор питания B1205S-2W https://aliexpress.ru/item/1005001291619304.html
 1. Изолятор шины i2c ADUM1251 https://aliexpress.ru/item/33052971531.html
 1. Плата для распайки изолятора i2c https://aliexpress.ru/item/1728075292.html
 1. Шилд pH https://aliexpress.ru/item/1005001672420703.html
 1. Набор для калибровки pH https://aliexpress.ru/item/33025867435.html

## Корпуса для 3D печати
 * Изготовление электрода ЕС: https://t.me/esp32wega/87
 * Корпус для контроллера: https://t.me/esp32wega/2850
 * Корпус датчика уровня: https://t.me/esp32wega/2363
 * Корпус датчика воздуха: https://t.me/esp32wega/2352

## Ещё
 * 2302 все сдохли после влажной осени


## Калибровка EC:
Для калибровки наиболее удобно использовать аптечный раствор кальция хлорида шестиводного. 
Жидкий в ампулах 100 г/л на 5 или 10 мл.
Можно приготовить три калибровочных раствора 1, 2 и 5 ампул растворить в полулитре (если ампула 10мл то в литре) дистиллята с ЕС 0.01

### Калибровочные растворы:
 * 1 ампула ЕС = 1.114 мсм/см
 * 2 апулы ЕС = 2.132 мсм/см
 * 3 апулы ЕС = 3.107 мсм/см
 * 4 апулы ЕС = 4.057 мсм/см
 * 5 ампул ЕС = 4.988 мсм/см
 * 6 ампул ЕС = 5.909 мсм/см



<a name="help"></a>
### Где искать помощь

Если у вас все еще есть вопросы по настройке, заливке и гонфигурированни этого дозера/миксера, 
то их всегда можно задать в официальном телеграмм канале [esp32-wega](https://t.me/esp32wega)

**!!! ВАЖНО !!!**

Ответы на вопросы, а что такое плюс или GND, а как быть с проводами и так далее в телеграмм канале дававться не будут.

Смотри [Минимальные требования и знания](#what_to_know)

