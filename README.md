# Drink Water Reminder
I wrote this simple app to help remind a loved one to drink more water when they are sick. Rather than trying to remind them myself, the script does it automatically.

# Requirements
Need to install fbchat for this functionality. Also need to schedule this script to run automatically. I've done this using Crontab on my Raspberry Pi with the following line:
#0, 30, 10-22 * * * sudo -u username python3 /full-path/drink-water.py

# Usage
```python
from fbchat import Client
from fbchat.models import *

# get credentials
with open("credentials.txt", "r") as f:
	lines = f.readlines()
	username = lines[0].rstrip()
	password = lines[1].rstrip()
	my_uid = lines[2].rstrip()
f.close()

# open client
client = Client(username, password)

# send message
client.send(Message(text='Time to drink water!'), thread_id=my_uid, thread_type=ThreadType.USER)
client.logout()
```

# Contributing
Pull requests are welcome. Feel free to contact me at brodydingel795@gmail.com for suggestions or comments.

# License
This project is open source.
