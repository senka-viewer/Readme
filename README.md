## Senka Viewer API说明
[Senka Viewer](https://senka.com.ru/) 为游戏[Kantai Collection](http://www.dmm.com/netgame/social/-/gadgets/=/app_id=854854/)玩家战果查询网站。
- 查询域名为：https://api.senka.com.ru
- 目前开放的api如下：
#### 往月数据查询
> /history/{serverno}/{year}/{month}

**serverno 起始数值为1 代表横须贺镇守府**

1. 正常返回数据结构如下
```
{
    "cutoff": [
        {
            "cutoff": {
                "1": 2089,
                "5": 1807,
                "20": 1389,
                "100": 827,
                "500": 392
            },  //战果线
            "timestamp": 1543644000000
        }
    ],
    "senka": [
        {
            "name": "xxx",  //玩家名称
            "comment": "xxxx",  //玩家签名
            "ranking": 18063, //玩家战果
            "medal": 2, //玩家勋章
            "history": [
                {
                    "rankno": 9,
                    "ranking": 1467,
                    "timestamp": 1541008800000
                } //玩家历史战果数据
            ]
        }
    ]
}
```

2. 异常返回数据结构
```
{
    "code": 1,  
    "status": "FAILURE|ERROR",  //FAILURE请求有误（缺少参数或参数有误） ERROR响应有误（服务器炸了）
    "info": "xxx"  //错误信息
}
```




  
