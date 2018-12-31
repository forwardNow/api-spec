# 机构管理

## 1. 查询机构（条件、分页）

请求：

```javascript
// POST /systemManage/OrganController/organSelectAlls
// Content-Type: application/json

{
  // 条件
  organName: String,       // 【可选】机构名称，模糊查询
  provinceName: String,    // 【可选】省级名称
  cityName: String,        // 【可选】城市名称
  townName: String,        // 【可选】区域名称

  // 分页器
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
    items: [
      // OrganVO 1
      // OrganVO 2
      // ......
    ]
  }
}
```

失败：

| code | message | result |
| - | - | - |
| 1 | `"fail"` | null |