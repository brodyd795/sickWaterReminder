# Drink Water Reminder
This script was intended to remind my wife to drink more water when she is sick. Rather than reminding her myself, this script does it automatically.

# Requirements
Need to install fbchat for this functionality.

# Usage
from fbchat import Client
from fbchat.models import *

```python
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
