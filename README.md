## Senka Viewer API说明
[Senka Viewer](https://senka.com.ru/) 为游戏[Kantai Collection](http://www.dmm.com/netgame/social/-/gadgets/=/app_id=854854/)玩家战果查询网站。
- 查询域名为：https://api.senka.com.ru
- 目前开放的api如下：
#### 往月数据查询
> /history/{serverno}/{year}/{month}
如果不需要详细玩家数据请使用
> /history/cutoffs/{serverno}/{year}/{month}
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




## Senka Viewer API Intro 
[Senka Viewer](https://senka.com.ru/) is a data query website for the players of [Kantai Collection](http://www.dmm.com/netgame/social/-/gadgets/=/app_id=854854/) to look up the ranking (i.e. Senka) data of the game.
- The address is：https://api.senka.com.ru
- The following api's are open for access：
#### List data form the past
> /history/{serverno}/{year}/{month}
If you don't need player details
> /history/cutoffs/{serverno}/{year}/{month}
**The least value of serverno is 1, representing Yokosuka.**

1. Data should be provided as follows:
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
            },  //the Senka cutoffs            "timestamp": 1543644000000
        }
    ],
    "senka": [
        {
            "name": "xxx",  //the player's ID
            "comment": "xxxx",  //the player's comment
            "ranking": 18063, //the player's Senka
            "medal": 2, //the number of the player's medals
            "history": [
                {
                    "rankno": 9,
                    "ranking": 1467,
                    "timestamp": 1541008800000
                } //the player's Senka data of the past
            ]
        }
    ]
}
```

2. Data like the follows will be provided when there are errors:
```
{
    "code": 1,  
    "status": "FAILURE|ERROR",  //FAILURE means that the query is wrong (parameters are missing or illegal). ERROR means that our server is not responding.    "info": "xxx"  //error massege
}
```




  

