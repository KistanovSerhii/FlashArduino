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

6. Подключаем NANO к ПК, и смотрим в менеджере устройств номер COM порта
![image](https://user-images.githubusercontent.com/28355711/163770098-2c4a6726-9690-4c1f-9aa5-adb90daca301.png)

7. Качаем ПО для первичной прошивки модуля ESP8266 ("FLASH_DOWNLOAD_TOOLS_V3.4.4")
8. Запускаем ESPFlashDownloadTool.exe и нажимаем на команду "ESP8266 DownloadTool"
![image](https://user-images.githubusercontent.com/28355711/163770473-b4e345de-449c-44ef-bd03-337db545ae74.png)

9. Заполняем "Download Path Config", выбираем COM к которому подключили схему и т.д. как на скрине
![image](https://user-images.githubusercontent.com/28355711/163770874-8728563a-9d2e-4837-82cb-9727dc9abcd8.png)

10. 
