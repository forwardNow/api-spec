# 会话模块

## 1. 登陆

请求：

```javascript
// POST /systemManage/UserController/userLogin
// Content-Type: application/json

{
  "userName": "admin",      // String，必须。登录名
  "userPassword": "111111"  // String，必须。密码
}
```

响应：

```javascript
// HTTP/1.1 200 OK
// Content-Type: application/json

{
  "code": 0,
  "message": "OK",
  "result": {
    // com.xwh.it.systemManage.vo.UserVO
    "userId": Integer, // 用户的ID
    "userName": String, // 用户名
    "userRealName": String, // 用户真实姓名
    "userCart": String, // 用户的身份证
    "userPoliceCart": String, // 用户的警官证
    "userPassword": String, // 用户的密码
    "userOrgan": String, // 用户所属的机构
    "userDepartment": String, // 用户所属的部门
    "fatherId": String, // 创建该用户的用户ID
    "userLevel": Integer, // 用户的等級
    "userPhone": String, // 用户的电话
    "userEmail": String, // 用户的邮箱
    "userStatus": String, // 用户状态，1:正常;2:锁定;3:注销
    "userRole": String, // 用户的角色
    "applicationSystem": String, // 应用管理系统
    "manufacturer": String, // 厂商
    "personinCharge": String, // 负责人
    "updateId": Integer, // 修改该用户的用户ID
    "userNumber": Integer, // 用户登录次数
    "userCreateTime": String, // 用户的注册时间
    "userUpdateTime": String, // 用户的修改时间*
    "userLastTime": String, // 用户最后一次登入时间*
    "createUser": String, // 创建人
    "createTime": String, // 创建时间
    "lastUpdateUser": String, // 最后修改人
    "lastUpdateTime": String, // 最后修改时间
    "isDelete": char, // 删除状态
  }
}
```

异常：

| code | message | result |
| - | - | - |
| 1 | `"用户名或密码错误"` | null |
| 2 | `"证书已失效"` | null |
| 3 | `"账户已冻结"` | null |
| 500 | `"未知错误"` | null |

## 2. 登出（退出）

请求：

```javascript
// POST /systemManage/UserController/userLogout
// Content-Type: application/json

{
  "userId": Integer      // Number，必须。用户 ID
}
```

响应：

```javascript
// HTTP/1.1 200 OK
// Content-Type: application/json

{
  "code": 0,
  "message": "OK",
  "result": null
}
```

异常：

| code | message | result |
| - | - | - |
| 1 | `"退出失败"` | null |
| 500 | `"未知错误"` | null |