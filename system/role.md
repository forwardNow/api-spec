# 角色管理

## 1. 模型（PO/VO/bean）

### 1.1. UserRoleVO

```javascript
{
  roleId: Integer, // 角色ID
  userRoleId: String, // 角色编码
  roleLevel: String, // 角色等级
  roleName: String, // 角色名称
  roleStatus: String, // 角色状态
  createUserId: String, // 创建角色的用户
  updateUserId: String, // 更新角色的用户
  createDate: String, // 创建时间
  updateDate: String, // 更新时间
  createUser: String, // 创建人
  createTime: String, // 创建时间
  lastUpdateUser: String, // 最后修改人
  lastUpdateTime: String, // 最后修改时间
  isDelete: char, // 删除状态
}
```

## 2. 查询角色列表

请求：

```javascript
// POST /systemManage/UserRoleController/selectUserRole
// Content-Type: application/json

{
  // 条件
  roleName: String,       // 【可选，模糊查询】角色名称

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
       {}, // UserRoleVO
       {}, // UserRoleVO
       ......
    ]
  }
}
```

失败：

| code | message | result |
| - | - | - |
| 1 | `"fail"` | null |

## 3. 删除角色

请求：

```javascript
// POST /systemManage/UserRoleController/deleteUserRole
// Content-Type: application/json

{
  roleId: String // 【必填】角色 ID
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

失败：

| code | message | result |
| - | - | - |
| 1 | `"fail"` | null |