## 游戏 js 调用Android 方法

js方法
```
var game={
    "action":1,
    "jumpUrl":"",
    "msg":"",
    "prizeType":1
}
game为String类型
window.android.callAndroid(game);
action==1时，全屏视频广告播放,action==2时， 触发底部banner广告,action==3时分享调起，action==4时网页调起 备注：（jumpUrl:1:游戏玩法介绍,2:分红信息,3:我的TLBC,4:活动内容,5:系统消息）
```
```js


目前的奖励类型
prizeType:{ 
 1=金币不足
 2=游戏加速
 3=打开飞行宝箱
 4=获得转盘卷
 5=获得恐龙
 …其它待定
}

```

## Android 调用 js  方法

js方法
```
  function callByAndroidInteraction(msg){
    
  }
```
```js
var game={
    "action":1,
    "msg":"",
    "prizeType":1
}
action:{
0=视频广告观看完毕，
1=为看完，
}
目前的奖励类型
prizeType:{ 
 1=金币不足
 2=游戏加速
 3=打开飞行宝箱
 4=获得转盘卷
 5=获得恐龙
 …其它待定
}

```




## H5 js 调用Android 方法

js方法
```
var game={
    "action":1,
    "jumpUrl":"",
    "msg":""
}

window.android.callAndroid(game);
```
```js
action==1时我的团队，action==2时我的收益，action==3时推广二维码，

```
