# drua-tg
Allows you to send tg-cli commands from Lua via TCP more intuitively.

### Usage
```lua
drua = require('drua-tg')
drua.IP = 'localhost'
drua.PORT = 4567
drua.message(chat_id, text)
```

To run multiple commands on the same TCP session:
```lua
s = drua.sopen()
drua.message(chat_id, text, s)
drua.send_photo(chat_id, filename, s)
s:close()
```

Previously used in otouto. Based on
[lua-tg](http://github.com/juanpotato/lua-tg) by JuanPotato.
