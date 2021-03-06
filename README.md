# 礼品码生成器

用法:

```bash
# 10000次生成性能测试
time php demo.php gen 10000

# 生成10000个代码(注意, 生产环境使用, 需要自己控制里面的base, 需要记录这个增长的序列值, 才能保证完全不重复)
php demo.php dump 10000

# 测试10000次随机暴力破解成功率
php demo.php check 10000
```

# code.php指标

```
特征: 可扩充礼品码类型, 同一基数只有固定礼品码, 不容易暴力破解

性能: 10000次生成耗时375ms (CPU: 3 GHz Intel Core i7)
爆破成功率: 百万分之十五以内.
```

# code.v1.php指标

```
特征: 可扩充礼品码类型, 同一基数产生不同礼品码, 较容易暴力破解

性能: 10000次生成耗时455ms (CPU: 3 GHz Intel Core i7)
爆破成功率: 万分之五以内.
```


# Tips

```
生产环境使用, 请修改下面两项, 防止被别人直接利用.
1: Code::SIGN: 修改为0-4095之间的整型
2: Code::BASE_26_CHARS: 乱序的不重复26个大写字母即可.
```
