# 用户模块

## 1. 基础 API

### 1.1. `/users/get`

#### 1.1.1. 作用

根据用户 ID 获取用户信息。

#### 1.1.2. 请求

请求参数：

| 参数 | 类型 | 必须 | 说明 |
| - | - | - | - |
| `UserId` | String | √ | 用户 ID （主键） |

示例：

```text
POST /users/get

{
  "UserId": "123"
}
```

#### 1.1.3. 响应

属性说明：

| 属性 | 类型 | 说明 |
| - | - | - |
| `UserId` | `String` | 用户ID |
| `UserTrueName` | `String` | 姓名 |
| `UserNickname` | `String` | 昵称 |
| `UserHeadImage` | `String` | 头像 |
| `Sex` | `String` | 性别。`'1'` 为男；`'2'` 为女 |
| `Phone` | `String` | 联系电话 |
| `PeopleCategory` | `String` | 人员类别 |
| `Address` | `String` | 住址 |
| `Landline` | `String` | 座机 |
| `QqNumber` | `String` | QQ号码 |
| `Email` | `String` | 电子邮箱 |
| `MedicalName` | `String` | 所属机构名称 |
| `UnitName` | `String` | 单位名称 |

示例：

```json
{
  "errorCode": 0,
  "reason": "OK",
  "result": {
    "UserId": "123",
    "UserTrueName": "张三",
    "UserNickname": "哇哈哈",
    "UserHeadImage": "",
    "Sex": "1",
    "Phone": "18707127777",
    "PeopleCategory": "1",
    "Address": "关山大道某小区",
    "Landline": "51666666",
    "QqNumber": "123456",
    "Email": "123456@qq.com",
    "MedicalName": "某机构",
    "UnitName": "某单位"
  }
}
```

## 2. 特殊 API
