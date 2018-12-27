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
  "result": null
}
```

异常：

| code | message | result |
| - | - | - |
| 1 | `"用户名或密码错误"` | null |
| 2 | `"证书已失效"` | null |
| 3 | `"账户已冻结"` | null |

## 2. 登出（退出）