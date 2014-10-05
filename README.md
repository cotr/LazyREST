LazyREST 是一个直接使用Web接口进行配置的REST Server。目前它主要在SAE上使用。

# 本fork所作的修改

1. URL重写格式改为 `/api/{{table}}/{{api}}.json?{{key}}={{value}}...`

2. 密码默认加盐，请修改 `/app/mod/api.class.php` `get_token()` 中的 `'SALTHERE'` 。加盐方式为 `md5(md5($username).md5($password).$SALT` 。

# LazyREST的特性
```
对于常见的增删改查接口，不用写一行代码。只需要在Web界面上点点鼠标就好了。
对于基于token的接口认证，也不用写一行代码，只需要选中一个checkbox。
每个接口提供I/O过滤功能，你有机会直接过滤输入和修整输出。
对于不常用的特殊业务逻辑接口，你可以在浏览器上直接编写该接口的代码。
```

# LazyREST的核心理念是
```
数据库+元数据 = Rest接口
```

LazyRest的工作方式是
```
读取数据库信息，让开发者指定对应的元信息；
通过元信息直接实现Rest接口，当元信息发生变动时，无需重新编码，接口直接可用
```

# 使用教程
LR很难直接理解，为了能节省你的时间，请认真阅读这篇文章 http://ftqq.com/lazyrest/
