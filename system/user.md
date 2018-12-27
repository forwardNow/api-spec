# 用户模块

## 1. 说明

用户模块相关 API 。

## 2. `/UserController/queryUserInfo`

>根据用户 ID 获取用户数据。

请求：

```javascript
{
  "userId": "123" // <String>。用户 ID
}
```

响应：

```javascript
{
  "code": 0,
  "message": "OK",
  "result": {
    "UserId": "123", // String。 用户 ID
    "UserTrueName": "张三", // String。 真实姓名
    "UserNickname": "哇哈哈", // String。 昵称。
    ......
  }
}
```

## 3. `/api/delteUserById`

>根据用户 ID 获取删除用户。

请求：

```javascript
{
  "userId": "123" // <String>。用户 ID
}
```

响应：

```javascript
{
  "code": 0,
  "message": "OK",
  "result": null
}
```

## 4. `/api/insertUser`

>添加用户。

请求：

```javascript
{
  "UserTrueName": "张三", // String。 真实姓名
  "UserNickname": "哇哈哈", // String。 昵称。
}
```

响应：

```javascript
{
  "code": 0,
  "message": "OK",
  "result": null
}
```