### crontab的文件格式

```
cron(Minutes Hours Day-of-month Month Day-of-week Year)
```

分 时 日 月 星期 要运行的命令

- 第1列分钟0～59
- 第2列小时0～23（0表示子夜）
- 第3列日1～31
- 第4列月1～12
- 第5列星期0～7（0和7表示星期天）
- 第6列要运行的命令

在以上各个字段中，还可以使用以下特殊字符：

- 星号（*）：代表所有可能的值，例如month字段如果是星号，则表示在满足其它字段的制约条件后每月都执行该命令操作。
- 逗号（,）：可以用逗号隔开的值指定一个列表范围，例如，“1,2,5,7,8,9”
- 中杠（-）：可以用整数之间的中杠表示一个整数范围，例如“2-6”表示“2,3,4,5,6”
- 正斜线（/）：可以用正斜线指定时间的间隔频率，例如“0-23/2”表示每两小时执行一次。同时正斜线可以和星号一起使用，例如*/10，如果用在minute字段，表示每十分钟执行一次。

### 案列

- 每月1号4点执行

```
0 0 4 1 * ?
```
> 注意：因为Linux上的crontab不支持到秒，只能是分钟级，因此对于秒，我们补0即可。如上，在该表达式中的第一位我们补0

我们可以通过以下[工具](https://www.bejson.com/othertools/cron/)对表达式进行验证


[参考资料](https://linuxtools-rst.readthedocs.io/zh_CN/latest/tool/crontab.html)



