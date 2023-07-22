**Бот для авторассылки по чатам**

Для того, чтобы установить бота, нужно выполнить пару простых команд:

`git clone https://github.com/KewsenGeek/Telegram-autotexter-bot`

``
pip3 install requirements.txt -r
``

Затем, нужно создать приложение на официальном сайте телеграмма: http://my.telegram.org

Для этого войдите в аккаунт > API developing tools и создайте приложение.

Для этого достаточно заполнить первые две графы: "App title" и "Short name"

После создания приложения, понадобятся всего два значения: api_id и api_hash

Для запуска бота, необходимо настроить его. Для этого в файле config.json нужно заполнить поля:

````
{ 
  "api_id": 0000,
  "api_hash": "hvuefnm3254y9878huuj7", # api_id и api_hash, который вы получили
  "username": "loremipsum" # username аккаунта, с которого будет работать бот
}
````

Теперь нужно настроить управляющего бота, через которого будет проходить настройка. 
Для этого в Telegram пишем боту @BotFather и регистрируем нового бота при помощи команды /newbot. 
Следуйте инструкциям и получите API-ключ для своего бота. 

Далее в файле settings.json нужно провести настройку:

````
{
  "ids": [], # ID чатов, где будет вестись рассылка (как получить, написано ниже)
  "text": "Это автоматически рассылаемый текст", # Текст, который будет рассылаться в чаты
  
  "timer": ["29-07-23 18:52:00", "29-07-23 18:52:05"], # Таймеры отправки сообщений
  
  "text_for_reply": "Это автоматический ответ", # Текст, который будет отправляться пользователям
  "admin_id": 703008433, # ID админа
  "admin_bot_api": "hvuefnm3254y9878huuj7:loremipsum4512" # API-ключ, полученный от @BotFather
}
````

Для того, чтобы получить ID чатов, необходимо запустить файл get_ids.py:

`python3 get_ids.py`

**!!!ВАЖНО!!!**

ID чатов **всегда** начинается со знака "-"

Бот настроен, и чтобы его запустить, необходимо написать `python3 main.py`

Бот-администратор напишет вам и предоставит доступ к настройкам