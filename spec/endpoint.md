# 请求路径

## 1. 说明

路径又称"终点"（endpoint），表示 API 的具体 URL（URI）。

每个 URL 代表一个资源（resource），尽量使用名词。

## 2. 模式

```text
https://example.com/api/{version}/{module}/{sub_module}/{operation}
```

## 3. 命名约定

使用 `_` 连接的小写字母。

## 4. 说明

|  | 示例 | 说明 |
| - | - | - |
| `{version}` | `v1` | 以 `v` 打头，后面跟版本号 |
| `{module}` | `users` | 模块名 |
| `{sub_module}` |  | 子模块名 |
| `{operation}` | `get` | 操作类型 |

## 5. `{operation}`

常用的增删改查的操作类型命名如下：

| operation | 说明 |
|-|-|
| `get` | 获取单条记录 |
| `list` | 获取多条记录 |
| `insert` | 插入一条记录 |
| `update` | 更新一条记录 |
| `delete` | 删除一条记录 |

## 6. 示例

### 6.1. 获取单条记录

HTTP 请求报文：

```text
POST /api/v1/users/get HTTP/1.1
Host: example.com
Accept: application/json
Content-Type: application/json

{
  "UserId": '123'
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
    "UserId": '123',
    "UserTrueName": "张三",
    "Sex": "0"
  }
}
```