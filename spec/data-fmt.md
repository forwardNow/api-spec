# 数据交换格式

## 1. 介绍

约定前后端数据交换格式。也就是说，针对 HTTP 进行约定，涉及以下方面：

* 状态码
* 方法
* 消息体数据格式
  * MIME 类型
  * 普通数据
  * 分页数据

## 2. 状态码

HTTP 响应的状态码统一为 200，无论是找不到资源（“404”）还是服务器内部错误（“500”），都强制为 200。

服务器端业务处理的状态由消息体内的状态字段（`"code"`）决定，查看 “状态码” 章节。

好处：

* 方便客户端统一处理

## 3. 方法

HTTP 请求的方法统一为 `"POST"`。

好处：

* 避免编码问题

## 4. 消息体数据格式

请求：

```text
{
  "prop1": "value1",
  "prop2": "value2",
  "prop3": "value3"
}
```

响应：

```text
{
  "code": <Number>,           // 业务状态码（必须）
  "message": [String],        // 状态码描述（可选）
  "result": [Object | Array]  // 数据/结果（可选）
}
```

### 4.1. MIME 类型

统一使用 `application/json` MIME 类型，即消息头为：

```text
Content-Type: application/json;charset=UTF-8
```

### 4.2. 普通数据（单条数据）

请求：

>请求体数据可以使用 bean 对象接收

```text
POST /api/v1/users/get HTTP/1.1
Host: example.com
Accept: application/json
Content-Type: application/json

{
  "UserId": '123'
}
```

响应：

```text
HTTP/1.1 200 OK
Content-Type: application/json

{
  "code": 0,
  "message": "OK",
  "result": {
    "UserId": '123',
    "UserTrueName": "张三",
    "Sex": "0"
  }
}
```

### 4.3. 分页数据（多条数据）

请求：

>请求体 `condition` 字段可以使用 bean 对象接收，`pager` 字段用分页对象接收。

```text
POST /api/v1/users/list HTTP/1.1
Host: example.com
Accept: application/json
Content-Type: application/json

{
  "condition": {
    "sex": "0"
  },
  "pager": {
    "currentPage": 1, // 当前页
    "pageSize": 20,   // 每页的记录数
  }
}
```

响应：

> `result` 中需要返回 `pager` 用于前端分页。

```text
HTTP/1.1 200 OK
Content-Type: application/json

{
  "code": 0,
  "message": "OK",
  "result": {
    "pager": {
      "total": 2,
      "currentPage": 1, // 当前页
      "pageSize": 20,   // 每页的记录数
    },
    "items": [
      { "UserId": "1", "UserTrueName": "张三" },
      { "UserId": "2", "UserTrueName": "李四" }
    ]
  }
}
```