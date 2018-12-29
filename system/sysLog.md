# 系统日志

## 1. 查询日志（条件、分页）

请求：

```javascript
// POST /systemManage/operateLog/queryOperateLog
// Content-Type: application/json
{
  condition: {
    operateObj: String, // 操作对象
    operateMethod: String,  // 操作方法
    createUser: String, // 创建人
    startDate: String,  // 开始时间
    endDate: String,  // 结束时间
  },
  pager: {
    pageSize: 20, // 每页的记录数
    currentPage: 1, // 当前页（请求第几页）
  }
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
    pager: {
      total: 2, // 总记录数
      pageSize: 20, // 每页的记录数
      currentPage: 1, // 当前页（请求第几页）
    },
    items: [ // Array<com.xwh.it.systemManage.vo>
       { id: 1, operateObj: '', .... },
       { id: 2, operateObj: '', .... },
       ......
    ]
  }
}
```

异常：

| code | message | result |
| - | - | - |
| 1 | `"fail"` | null |
| 500 | `"未知错误"` | null |
