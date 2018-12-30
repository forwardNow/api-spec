# 菜单管理

## 1. 获取菜单树

>说明：用于构建左侧菜单树

请求：

```javascript
// POST /systemManage/MenuController/getMenuList
// Content-Type: application/json

{
}
```

响应：

```javascript
// HTTP/1.1 200 OK
// Content-Type: application/json

{
  "code": 0,
  "message": "OK",
  "result": [
    // com.xwh.it.systemManage.vo.UpcRightVO
    {
      upcId: Integer, // 权限表主键
      upcRight: String, // 权限对应的页面
      upcRightName: String, // 权限说明（菜单名称）
      fatherId: Integer, // 父ID
      icon: String, // 图标
      url: String, // URL
      sort: Integer, // 排序
      desc: String, // 描述
      createUser: String, // 创建人
      createTime: String, // 创建时间
      lastUpdateUser: String, // 最后修改人
      lastUpdateTime: String, // 最后修改时间
      isDelete: char, // 删除状态0代表已删除 1代表未删除
    },
    { upcId: 1, fatherId: null, ... },
    { upcId: 2, fatherId: 1, ... },
    { upcId: 3, fatherId: 1, ... },
    ......
  ]
}
```

失败：

| code | message | result |
| - | - | - |
| 1 | `"获取失败"` | null |
| 500 | `"未知错误"` | null |