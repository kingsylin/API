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
    }
  },
  "msg": "请求成功",
  "success": true
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
