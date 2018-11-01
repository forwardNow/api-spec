# 过滤信息

## 1. 说明

如果记录数量很多，服务器不可能都将它们返回给用户。API应该提供参数，过滤返回结果。

## 2. 命名约定

以 `_`（下划线）打头的小写字母

## 3. 常用过滤参数

| 参数 | 类型 | 示例 | 说明 |
|-|-|-|-|
| `_limit` | `Number` | `{ "_limit": 20 }` | 返回的记录数 |
| `_offset` | `Number` | `{ "_offset": 0 }` | 偏移量 |
| `_orderby` | `String` | `{ "_orderby": "name asc" }` | 按指定字段排序 |
| `_count` | `Boolean` | `{ "_count": true }` | 是否返回总数 |
| `_keyword` | `*` | `{ "_keyword": "张" }` | 模糊查询 |

注：排序参数的模式为 `_orderby={field} [asc|desc]`

## 4. 精确查询

直接指定参数名和参数值即可，如 `{ "Sex": "1" }`

## 5. 示例

### 分页查询

HTTP 请求报文：

```text
POST /api/v1/users/list HTTP/1.1
Host: example.com
Accept: application/json
Content-Type: application/json

{
  "_limit": "20",  // 每页 20 条记录
  "_offset": "20", // 跳过 20 条记录，即获取第 2 页
  "_count": true,
  "Sex": "0"
}
```

HTTP 响应报文：

```text
HTTP/1.1 200 OK
Content-Type: application/json

{
  "errorCode": 0,
  "reason": "OK",
  "result": {
    "total": 2,
    "items": [
      { "UserId": '1', "UserTrueName": "张三", "Sex": "0" },
      { "UserId": '2', "UserTrueName": "李四", "Sex": "0" }
    ]
  }
}
```