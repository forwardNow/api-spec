# 返回结果

## 1. 模式

```text
HTTP/1.1 200 OK
Content-Type: application/json

{
  "errorCode": <Number>,
  "reason": <String>,
  "result": <Object|null>
}
```

## 2. 说明

| 属性 | 类型 | 说明 |
| - | - | - |
| `errorCode` | `Number` | 错误码，请查看[详情](./errorcode.md) |
| `reason` | `String` | 错误原因 |
| `result` | `Object` `null` | 结果数据 |

## 3. 结果数据

结果数据分两种情况

* 一条记录
* 多条记录

### 3.1. 一条记录

直接用普通对象表示，其格式如下

```json
{
  "errorCode": 0,
  "reason": "OK",
  "result": { "UserId": "1", "UserTrueName": "张三" }
}
```

### 3.2. 多条记录

多条记录一般用于分页，其格式如下

```json
{
  "errorCode": 0,
  "reason": "OK",
  "result": {
    "total": 2,
    "items": [
      { "UserId": "1", "UserTrueName": "张三" },
      { "UserId": "2", "UserTrueName": "李四" }
    ]
  }
}
```