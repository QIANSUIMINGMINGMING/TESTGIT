# 安卓api

#### 实例

<iframe height=498 width=510 src="https://www.bilibili.com/video/BV1aZ4y1W7UT?from=search&seid=11514272801202422895">

#### 分析问题

接收到的数据是：

startCoord = 4 13502649.259333 3657479.698623 0.000000  , endCoord = 4 13502654.417360 3657500.435975 0.000000  ,distance = 21.369207,  startDirection = 北, endDirection = 右转
startCoord = 4 13502654.417360 3657500.435975 0.000000  , endCoord = 4 13502687.601000 3657492.182000 0.000000  ,distance = 34.194767,  startDirection = 东, endDirection = 左转
startCoord = 4 13502687.601000 3657492.182000 0.000000  , endCoord = 4 13502693.175000 3657514.591000 0.000000  ,distance = 23.091833,  startDirection = 北, endDirection = 右转

根据这三段作出图像为：

![image-20200718185600605](C:\Users\alien\AppData\Roaming\Typora\typora-user-images\image-20200718185600605.png)

根据图像和点的位置，我们首先要确定