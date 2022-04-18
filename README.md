# How to Flashed Arduino
Инструкция как подготовить модуль Arduino к работе
(к загрузке своих программ и в дальнейшем исполнению их)

# Flashing ESP8266 through NANO
1. Установить драйвер для микросхемы CH340
![image](https://user-images.githubusercontent.com/28355711/163768488-776b7dcb-eac1-480f-90cc-b8f5659ef436.png)

2. Установить Arduino IDE
3. Указываем ссылку для менеджера плат:      
      
        (RU) Файл -> Настройки    -> Дополнительные ссылки для менеджера плат
        (EN) File -> Preferences  -> Additional Boards Manager URLs

        https://arduino.esp8266.com/stable/package_esp8266com_index.json
![image](https://user-images.githubusercontent.com/28355711/163768841-1a055bce-f3d5-4d38-9910-17d521bdfb0b.png)

4. Установить пакет (библиотеки) для платы ESP8266 через "менеджер плат"

        Tools -> Manager librariesESP
        в поиске вводим ESP8266 и устанавливаем понравившийся пакет
        необходимый для решения поставленной/предстоящей задачи
![image](https://user-images.githubusercontent.com/28355711/163769071-d5a4f76f-129f-4272-8e4c-b517a857f9a7.png)

5. Собираем схему подключения для ПРОШИВКИ: Arduino NANO -> Преобразователь напряжения -> ESP8266
![image](https://user-images.githubusercontent.com/28355711/163769255-8184dfba-e3a2-4f53-bee6-66bbd7482226.png)

      Через преобразователь (с 5V на 3V) Потому что,
      выход 3V из Nano не достаточно для работы ESP8266

6. Подключаем NANO к ПК, и смотрим в менеджере устройств номер COM порта
![image](https://user-images.githubusercontent.com/28355711/163770098-2c4a6726-9690-4c1f-9aa5-adb90daca301.png)

7. Качаем ПО для первичной прошивки модуля ESP8266 ("FLASH_DOWNLOAD_TOOLS_V3.4.4")
8. Запускаем ESPFlashDownloadTool.exe и нажимаем на команду "ESP8266 DownloadTool"
![image](https://user-images.githubusercontent.com/28355711/163770473-b4e345de-449c-44ef-bd03-337db545ae74.png)

9. Заполняем "Download Path Config", выбираем COM к которому подключили схему и т.д. как на скрине
![image](https://user-images.githubusercontent.com/28355711/163779135-536a40f2-bfa3-46ca-a482-1c806a7a4c7f.png)
+ я указал исключительно blank.bin и прошил только данным шаблоном
+ Скорость порта в менеджере устройств windows (9600) не меняем и в flashTool тоже оставляем по умолчанию (115200)

10. Нажимаем "START" после чего должно произойти подключение по указанному COM порту и выполнение прошивки
![image](https://user-images.githubusercontent.com/28355711/163774774-ff783e8f-a575-4eeb-8fa5-eeab975dfaba.png)

если процесс не начинается (не идет загрузка, а вместо этого пищет в бесконечном цикле "connecting .." тогда
скорей всего это плата не ESP8266 или это не рабочая плата, потому что всю должно получится по данной инструкции

___У меня был случаи когда не шло и это был похожий модуль на ESP8266 но это был не он___

# Готов к загрузке своих скетчей (программ)
Выполнив предыдущий шаг плата готова к загрузке своих скетчей (программ)
1. Оставляем туже схему (схема для прошивки)
2. Заходим в Arduino IDE и пишем нужный программный код
3. Нажимаем Upload/Загрузить

# Готов к работе своего скется (программы)
Если надо проверить работу через туже схему (подключением через NANO) тогда
1. Необходимо отключить NANO от USB и отключить IO0 от земли на ESP8266
![image](https://user-images.githubusercontent.com/28355711/163778163-620bde22-95cf-4e06-8866-360929de3af7.png)

2. Подключить NANO к ПК

Теперь модуль ESP8266 работает в режиме исполнения кода (скетча загруженного в него)

# AT команды модуля ESP8266

      AT          - Ответ "ОК" если работает
      AT+GMR      - Ответ версия
