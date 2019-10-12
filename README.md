## 用户

### 账号密码登录{#loginByPwd}

```
POST /user/loginByPwd
```
### 字段说明

| 参数名         | 类型            | 描述                          | 是否必须            |
| ----------- | ------------- | --------------------------- | --------------- |
| account          | string   | 账号                     | 是               |
| password          | string   | 密码                     | 是               |

### 返回数据示例{#loginData}

```js
{
  "code": 0,
  "data": {
    "token":"ud129vsdf12efgfs102",
    "member":{
      "id":1,//自增ID
      "avatar":"https://static.xxxxxx.com/avatar/avatar0.png", //头像
      "balance":20.00, //余额
      "hasInitPassword":false, //是否设置密码
      "invitationCode":"R8Gkd", //邀请码
      "nickname":"System", //昵称
      "phone":"13800000000", //手机号
      "qq":"13023120", //QQ
       "wechat":"",//微信
      "coin_id":9821454312, //虚拟币钱包ID
      "coin_count":1, //虚拟币金额
      "isIsVerified":false,//是否实名认证
      "isCreateWorld":false,//是否是创世居民，估计是否是第一批用户
      "forceLevelName":"青铜矿工Ⅱ",//用户等级名称
      "petLevelName":"蛋生",//宠物等级
      "tlbc_count":1.2,//我的TLBC
      "arithmetic_force":3,//我的算力
      "partnerEntrySetting":{ ,//广告数据
          "bannerUrl":"url",//bannerUrl
          "entryUrl":"url",//banner 跳转的url
          "showEntry":false,//广告显示与否
         }
     "associationEntrySettingDto":{//社区排行榜
          "bannerUrl":"url",//bannerUrl
          "entryUrl":"url",//banner 跳转的url
          "showEntry":false,//显示与否
     }
     "unCompleteDailyTaskNum":4,//打工红包还差多少任务
     "remainCollectTlbcTimesNum":12,//随机红包还差多少次TLBC
      "upgradeHbSetting":{
            "isCanCollectUpgradeHb":false,
            "level":10,//最高级别
            "maxAmount":2,//最高可以获得几元
            "promptLevel":5,//提示级别
            "promptText":"我在10级等你哟~",
            "shortLevel":8,//升级红包还差几级
        },
         "marketDay":0,//赶集日期
  
     
    }
  },
  "msg": "请求成功",
  "success": true
}
```
#### 以下是tuoluoshijian,返回的数据
```js

{
    "code":0,
    "data":{
        "arithmetic_force":141,
        "associationEntrySettingDto":{
            "bannerUrl":"https://res.tuoluoshijie.com/icons/banner/association-rank-banner.jpg",
            "entryUrl":"https://h5.tuoluoshijie.com/h5/prod/tlsj2/index.html#/association/index",
            "showEntry":true
        },
        "avatar":"http://thirdwx.qlogo.cn/mmopen/vi_32/Q0j4TwGTfTKBciaCQzIaLas5gHabl5rumttic0eQH3H9L3BO8lqOoZXlbiacD5eUc1gAOWOSR7ULvMPkg1hlYXsKg/132",
        "balance":0,
        "forceLevelName":"青铜矿工Ⅱ",
        "hasInitPassword":true,
        "id":5224460,
        "invitationCode":"qamzt",
        "isBindMp":false,
        "isBindWechat":true,
        "isCollectDailyTaskCompleteHb":false,
        "isCollectTlbcTaskCompleteHb":false,
        "isCompleteAllDailyTask":false,
        "isCompleteCollectTlbcTask":false,
        "isCreateWorld":false,
        "isNeedPerfectInfo":false,
        "isNewUser":false,
        "isPrivacyVisibleToChild":false,
        "isPrivacyVisibleToFather":false,
        "isPrivacyVisibleToGrandfather":false,
        "isShowUpgradeHb":true,
        "isVerified":true,
        "marketDay":0,
        "nickname":"DFE",
        "partnerEntrySetting":{
            "bannerUrl":"",
            "entryUrl":"",
            "showEntry":false
        },
        "petLevelName":"蛋生",
        "phone":"186****6096",
        "qq":"",
        "remainCollectTlbcTimesNum":12,
        "tlId":"72630045",
        "tlbc_count":0,
        "unCompleteDailyTaskNum":3,
        "upgradeHbSetting":{
            "isCanCollectUpgradeHb":false,
            "level":10,
            "maxAmount":2,
            "promptLevel":5,
            "promptText":"我在10级等你哟~",
            "shortLevel":8
        },
        "wechat":"",
        "wechatNickname":"DFE"
    },
    "msg":"请求成功",
    "success":true
}

```

### 微信登录{#loginByWechat}
```
POST /user/loginByWechat
```
### 字段说明

| 参数名         | 类型            | 描述                          | 是否必须            |
| ----------- | ------------- | --------------------------- | --------------- |
| code          | string   | 微信登录前端返回的校验码                     | 是               |

返回数据同[登录数据](user.md#loginData)


### 短信验证码登录{#loginByPhone}
```
POST /user/loginByPhone
```
### 字段说明

| 参数名         | 类型            | 描述                          | 是否必须            |
| ----------- | ------------- | --------------------------- | --------------- |
| phone          | string   | 手机号                     | 是               |
| sms_code          | string   | 验证码                     | 是               |

返回数据同[登录数据](#loginData)

### 找回密码{#getBackPwd}
```
POST /user/getBackPwd
```
### 字段说明

| 参数名         | 类型            | 描述                          | 是否必须            |
| ----------- | ------------- | --------------------------- | --------------- |
| phone          | string   | 手机号                     | 是               |
| password          | string   | 新密码                     | 是               |
| sms_code          | string   | 验证码                     | 是               |

返回数据同[基础响应](README.md#baseresponse)


### 修改昵称{#getUserInfo}

后端需要根据请求头中的`token`鉴权
```
GET /user/getUserInfo
```
### 字段说明

返回数据同[登录数据](#loginData)

### 设置密码{#setPassword}

后端需要根据请求头中的`token`鉴权
```
POST /user/setPassword
```
### 字段说明

| 参数名         | 类型            | 描述                          | 是否必须            |
| ----------- | ------------- | --------------------------- | --------------- |
| password          | string   | 新密码                     | 是               |

返回数据同[基础响应](README.md#baseresponse)


### 绑定手机号{#setPhone}

后端需要根据请求头中的`token`鉴权
```
POST /user/setPhone
```
### 字段说明

| 参数名         | 类型            | 描述                          | 是否必须            |
| ----------- | ------------- | --------------------------- | --------------- |
| phone          | string   | 手机号                     | 是               |
| sms_code          | string   | 验证码                     | 是               |

返回数据同[基础响应](README.md#baseresponse)

### 修改昵称{#updateNickname}

后端需要根据请求头中的`token`鉴权
```
POST /user/updateNickname
```
### 字段说明

| 参数名         | 类型            | 描述                          | 是否必须            |
| ----------- | ------------- | --------------------------- | --------------- |
| nickName          | string   | 昵称                     | 是               |

返回数据同[基础响应](README.md#baseresponse)

### app配置接口，页面配置接口{#/funcSwitch/getAll.json}

后端需要根据请求头中的`token`鉴权
```
POST /funcSwitch/getAll.json
```
```js
{
    "code":0,
    "data":{
        "hiddenArithmeticForce":false,
        "hiddenBannerAds":false,
        "hiddenCustomerServiceTel":false,
        "hiddenDailyTaskHb":false,
        "hiddenEarningPage":false,
        "hiddenFlashScreen":false,
        "hiddenGame":false,
        "hiddenGiftPack":false,
        "hiddenGrowArithmeticForce":false,
        "hiddenHbExpressNews":false,
        "hiddenInvitationCodeTips":false,
        "hiddenInvitationVoucher":false,
        "hiddenJoinCommunity":false,
        "hiddenLaunchScreen":false,
        "hiddenMyAssets":false,
        "hiddenMyInvitationCode":false,
        "hiddenMyTlbcToUseBtn":false,
        "hiddenOldRecreation":true,
        "hiddenRank":false,
        "hiddenRealNameInfo":false,
        "hiddenSDWNativeUrl":false,
        "hiddenSettingAbountTlbc":false,
        "hiddenSettingCommonQA":false,
        "hiddenSettingTlbcEcoAccount":false,
        "hiddenShowEarningPage":true,
        "hiddenSpeedUpByInvitationVoucherBtn":false,
        "hiddenSubscribeWechatMp":false,
        "hiddenSuggestion":false,
        "hiddenTlbcAccountLogin":false,
        "hiddenTlbcAccountLoginBtn ":false,
        "hiddenTlbcCollectHb":false,
        "hiddenTreasureBox":false,
        "hiddenTurntable":false,
        "hiddenUpgradeHb":false,
        "hiddenWholeTaskPage":false,
        "hiddenWithdraw":false
    },
    "msg":"请求成功",
    "success":true
}

```

### 打工界面{#/task/getMyTaskStatus.json  n}

后端需要根据请求头中的`token`鉴权，如果不懂字段意思，可以登陆tuoluoshijie,打开 《打工》界面
```
POST /task/getMyTaskStatus.json  
```
```js
{
    "code":0,
    "data":{
        "arithmetic_force":141,
        "currentChapter":0,
        "dailyTaskList":[
            {
                "actived":true,
                "arithForceAward":1,
                "code":"DAILY_SIGN",
                "description":"签到获取算力",
                "id":1,
                "isComplete":false,
                "logo":"https://res.tuoluoshijie.com/icons/task/sign_task.png",
                "name":"每日签到",
                "setting":"",
                "type":1,
                "upperLimit":1
            },
            {
                "actived":true,
                "arithForceAward":50,
                "code":"INVITE_FRIEND",
                "description":"邀请1好友+10算力",
                "id":2,
                "isComplete":false,
                "logo":"https://res.tuoluoshijie.com/icons/task/invite_task.png",
                "name":"邀请5名好友",
                "setting":"",
                "type":1,
                "upperLimit":5
            },
            {
                "actived":true,
                "arithForceAward":5,
                "code":"ONLINE_TIME",
                "description":"登录陀螺世界，在线时长30分钟",
                "id":3,
                "isComplete":true,
                "logo":"https://res.tuoluoshijie.com/icons/task/online_task.png",
                "name":"在线30分钟",
                "setting":"",
                "type":1,
                "upperLimit":1
            }
        ],
        "forceLevelLogo":"https://res.tuoluoshijie.com/icons/force_level/common/2.png",
        "forceLevelName":"青铜矿工Ⅱ",
        "inviteNum":0,
        "isCompleteSign":false,
        "isVerified":true,
        "oneTimeTaskList":[
            {
                "actived":true,
                "arithForceAward":100,
                "code":"REAL_NAME_AUTH",
                "description":"注册并完成实名认证",
                "id":4,
                "isComplete":true,
                "logo":"https://res.tuoluoshijie.com/icons/task/verify_task.png",
                "name":"实名认证",
                "setting":"",
                "type":2,
                "upperLimit":1
            },
            {
                "actived":true,
                "arithForceAward":5,
                "code":"SUBSCRIBE_MP_WEIXIN",
                "description":"关注公众号获取算力",
                "id":5,
                "isComplete":false,
                "logo":"https://res.tuoluoshijie.com/icons/task/subscribe_task.png",
                "name":"关注微信公众号",
                "setting":"",
                "type":2,
                "upperLimit":1
            },
            {
                "actived":true,
                "arithForceAward":5,
                "code":"BIND_WEXIN",
                "description":"绑定微信登录获取算力",
                "id":6,
                "isComplete":true,
                "logo":"https://res.tuoluoshijie.com/icons/task/bind_task.png",
                "name":"绑定微信",
                "setting":"",
                "type":2,
                "upperLimit":1
            },
            {
                "actived":true,
                "arithForceAward":20,
                "code":"NEWBIE_RESPONDENT",
                "description":"回答问卷",
                "id":10,
                "isComplete":false,
                "logo":"https://res.tuoluoshijie.com/icons/task/test/1556421350588.png",
                "name":"新手学习(1/3)--游戏篇",
                "setting":"["游戏篇","收益篇","生态篇"]",
                "type":2,
                "upperLimit":3
            }
        ],
        "onlineMinutes":36,
        "tlbc_count":0
    },
    "msg":"请求成功",
    "success":true
}
```

###  手机版本更新接口{#/version/getLastestVersion.json}

后端需要根据请求头中的`token`鉴权
```
POST /version/getLastestVersion.json
```
```js
{
    "code":0,
    "data":{
        "compatible":false,
        "domainType":0,
        "downloadUrl":"test",
        "forceUpdate":false,
        "gitTag":"test",
        "f16id":0,
        "operateTime":54545454,
        "operator":"test",
        "platform":"test",
        "status":0,
        "type":0,
        "versionDetail":"test",
        "versionName":"test",
        "versionOwner":"test",
        "versionSeq":0,
        "versionSize":"test",
        "versionSummary":"test",
        "versionTime":46465656565
    },
    "msg":"请求成功",
    "success":true
}

```

### 提交认证信息{#/user/realNameAuth.json}

后端需要根据请求头中的`token`鉴权
```
POST /personnel/realNameAuth.json
```
### 字段说明

| 参数名         | 类型            | 描述                          | 是否必须            |
| ----------- | ------------- | --------------------------- | --------------- |
| realName          | string   | name                     | 是               |
| idCard          | string   | ID                     | 是               |

```js
{
    "code":0,
    "data":{

    },
    "msg":"提交成功",
    "success":true
}
```

### 获取实名认证信息{#/user/getRealNameInfo.json}

后端需要根据请求头中的`token`鉴权
```
POST /personnel/getRealNameInfo.json
```
```js
{
    "code":0,
    "data":{
        "idCard":"",
        "isVerified":true,
        "realName":""
    },
    "msg":"请求成功",
    "success":true
}

```
### 设置赶集{#/user/setMarketDay}

后端需要根据请求头中的`token`鉴权
```
POST /user/setMarketDay
```
### 字段说明

| 参数名         | 类型            | 描述                          | 是否必须            |
| ----------- | ------------- | --------------------------- | --------------- |
| marketDay          | int   | marketDay(1,2,3)                  | 是               |


```js
{
    "code":0,
    "data":{},
    "msg":"请求成功",
    "success":true
}
```
### 设置QQ,微信账号{#/user/updateMemberSocialInfo}

后端需要根据请求头中的`token`鉴权
```
POST /user/updateMemberSocialInfo
```
### 字段说明

| 参数名         | 类型            | 描述                          | 是否必须            |
| ----------- | ------------- | --------------------------- | --------------- |
| qq          | String   | qq                | 是               |
| wechat          | String   | wechat                  | 是               |
```js
{
    "code":0,
    "data":{},
    "msg":"请求成功",
    "success":true
}
```
### test{#/userupdateIsPrivacyVisible}

后端需要根据请求头中的`token`鉴权
```
POST /userupdateIsPrivacyVisible
```
### 字段说明

| 参数名         | 类型            | 描述                          | 是否必须            |
| ----------- | ------------- | --------------------------- | --------------- |
| toFather          | boolean   | 对师傅是否可见                | 是               |
| toGrandFather          | boolean   | 对师公是否可见                  | 是               |
| toFather          | boolean   | 对徒弟是否可见                  | 是               |

```js
{
    "code":0,
    "data":{},
    "msg":"请求成功",
    "success":true
}
```

### test{#test.json}

后端需要根据请求头中的`token`鉴权
```
POST /funcSwitch/getAll.json
```
```js
```


