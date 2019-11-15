# VKChatBot

Installation:
```
$ pip install VKChatBot
```

Usage:
```
import os
from vkchatbot import VKChatBot


group_access_token = os.getenv('VK_GROUP_TOKEN')
group_id = os.getenv('VK_GROUP_ID')
bot = VKChatBot(access_token=group_access_token, group_id=group_id)
bot.register_command('фио', cmd_get_name)
bot.register_command('неделя', cmd_get_week)
bot.register_command('помощь', cmd_help)
bot.register_command('время', cmd_get_time)
bot.register_command('звонки', cmd_get_timetable)
bot.unknown_command_msg = unknown_command
bot.work()
```

## Setting up

Acquire access token in community settings. Turn on long polling mode and set it's API version to "5.80" (you can specify other version in 
VKChatBot constructor arguments, but chatbot requires at least 5.80 which is default)
`register_command` expects command name as it's first argument and callable as second. Callable must receive one argument `event` which is an update object (dict) 
returned by VK Long Polling server (read more about it in VK Docs).
Commands is fired when someone types "!" and command, like "!help". You can change prefix using constructor argument `command_prefix`.

I'm not planning to maintain this library very active and to write verbose documentation at this moment.
