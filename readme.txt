Создание бота в телеграмм для отправки сообщений через node.js в телеграмме:
    1. вызвать BotFather  и  в нем набрать:          /start
    2. создать нового бота :                                      /newbot
    3. завести имя бота (любое доступное) :          my_project
    4. завести nik_name bota с окончанием bot:    my_project_bot
    5. BotFather присылает token для HTTP API (выделяет красным)
 primerno56789067898789098890cwR9aso
6. создать группу, куда бот будет кидать сообщения, не забываем добавить бота в чатconfig/config.json:{
  "telegram": {
    "token": "bot_token",
    "chat": "chat_id"
  }
}
7. Идем в браузер и в адресной строке вводим:
https://api.telegram.org/botXXXXXXXXXXXXXXXXXXXXXXX/getUpdates
где XXXXXXXXXXXXXXXXXXXXXXX — токен бота,

пример:
Абай
/newbot

BotFather
Alright, a new bot. How are we going to call it? Please choose a name for your bot.

Абай
elbrus_p2w3d4

BotFather
Good. Now let's choose a username for your bot. It must end in `bot`. Like this, for example: TetrisBot or tetris_bot.

Абай
elbrus_p2w3d4_bot

BotFather
Done! Congratulations on your new bot. You will find it at t.me/elbrus_p2w3d4_bot. You can now add a description, about section and profile picture for your bot, see /help for a list of commands. By the way, when you've finished creating your cool bot, ping our Bot Support if you want a better username for it. Just make sure the bot is fully operational before you do this.

Use this token to access the HTTP API:
1633939094:AAHyToE657AZFxvbR8RPtwbl5rAo4vgZtDA
Keep your token secure and store it safely, it can be used by anyone to control your bot.

For a description of the Bot API, see this page: https://core.telegram.org/bots/api
//------------------------------
получили токен : 1633939094:AAHyToE657AZFxvbR8RPtwbl5rAo4vgZtDA
в api telegram вставляем токен после выражения https://api.telegram.org/bot "ТОКЕН" /getUpdates
получаем 
https://api.telegram.org/1633939094:AAHyToE657AZFxvbR8RPtwbl5rAo4vgZtDA/getUpdates
получили {"ok":true,"result":[]}

в телеграмме создаем группу :
пример:Groupp_elbrus_p2w3d4


в бот подключаем всех участников и самого бота 'elbrus_p2w3d4_bot'
можно из телеграмма получить ссылку на приглашение в бот 
Invite to group via link:
у нас это: https://t.me/joinchat/GRnb-g_YBju8YHci

на приглашение надо согласиться 
поэтому в открываем 
Groupp_elbrus_p2w3d4 и в ней пишем 
/join elbrus_p2w3d4_bot

после этого заходим 
https://api.telegram.org/bot1633939094:AAHyToE657AZFxvbR8RPtwbl5rAo4vgZtDA/getUpdates

получаем 
{"ok":true,"result":[{"update_id":261666949,
"message":{"message_id":2,"from":{"id":51084134,"is_bot":false,"first_name":"\u0410\u0431\u0430\u0439","last_name":"\u0420\u0435\u0443\u0448\u0435\u043d\u043e\u0432","username":"Reushenov_Abay"},"chat":{"id":-421125114,"title":"Groupp_elbrus_p2w3d4","type":"group","all_members_are_administrators":true},"date":1613644694,"text":"/join elbrus_p2w3d4_bot","entities":[{"offset":0,"length":5,"type":"bot_command"}]}}]}
для группы id:"id":-421125114
для меня id: "id":51084134,
id и токен прописываем в config.json

{
  "telegram": {
    "token": "1633939094:AAHyToE657AZFxvbR8RPtwbl5rAo4vgZtDA",
    "chat": "-421125114"
  }
}

запускаем npm start
заполняем форму

получаем в телеграмм на адрес группы:
elbrus_p2w3d4
Name: Miron
Phone:  44 905 54159 20
Message: uiiiiiiiiiiiii

Вся логика идет через api/telegramMsg.js
при желании можно менять body которое формирует ответ.
