# 用户模块

## 1. 查询用户（条件、分页）

请求：

```javascript
// POST /systemManage/UserController/queryUserInfo
// Content-Type: application/json

{
  // 条件
  userName: String,       // 【可选】用户名，模糊查询
  userDepartment: String, // 【可选】部门名称，模糊查询
  userCart: String,       // 【可选】身份证号
  userPoliceCart: String, // 【可选】警官证号
  userRole: String        // 【可选】角色名

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
    items: [ // Array<com.xwh.it.systemManage.vo.UserVO>
       { userId: 1, userName: '', .... },
       { userId: 2, userName: '', .... },
       ......
    ]
  }
}
```

失败：

| code | message | result |
| - | - | - |
| 1 | `"fail"` | null |

## 2. 删除用户

请求：

```javascript
// POST /systemManage/UserController/deleteUser
// Content-Type: application/json

{
  userId: Integer // 【必填】用户的ID
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

## 3. 用户详情

请求：

```javascript
// POST /systemManage/UserController/userDetails
// Content-Type: application/json

{
  userId: Integer // 【必填】用户的ID
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
    // com.xwh.it.systemManage.vo.UserVO
  }
}
```

失败：

| code | message | result |
| - | - | - |
| 1 | `"fail"` | null |

## 4. 添加用户

请求：

```javascript
// POST /systemManage/UserController/addUser
// Content-Type: application/json

{
  userName: '',
  userRealName: '',
  userRole: '',
  userDepartment: '',
  userPhone: '',
  userCart: '',
  manufacturer: '',
  userEmail: '',
  applicationSystem: '',
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

## 5. 重置密码

请求：

```javascript
// POST /systemManage/UserController/userPassWordRemake
// Content-Type: application/json

{
  userId: Integer // 【必填】用户的ID
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

## 6. 导出用户

请求：

```javascript
// POST /systemManage/UserController/userExport
// Content-Type: application/json

[ 1, 2, 8 ] // 【必填】用户的 ID 列表
```

响应：

```javascript
// HTTP/1.1 200 OK
// Content-Type: application/vnd.ms-excel

// 流数据，下载
```

失败：

| code | message | result |
| - | - | - |
| 1 | `"fail"` | null |