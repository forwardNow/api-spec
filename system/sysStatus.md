# 系统状态

## 1. 查询（条件、分页）

请求：

```javascript
// POST /systemManage/systemInfo/querySystemInfo
// Content-Type: application/json
{
  condition: {
    computerName: String, // 电脑名称
  }
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
    items: [ // Array<com.xwh.it.systemManage.vo.SystemInfoVO>
       { cpuUsage: '', .... },
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
