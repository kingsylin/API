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
        }
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
