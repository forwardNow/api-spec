# 错误码

## 1. 说明

在 HTTP 响应的状态码强制为 200 的请求下，通过错误码（`errorCode`）和原因（`reason`）表示 API 的调用状态。

错误码分为两种类别

* 系统类
* 业务类

## 2. 系统类

系统类也可以认为是通用类，与业务无关的状态码都可以认为是系统类，参考 HTTP 状态码，有如下

| errorCode | reason | 说明 |
| - | - | - |
| 0 | `OK` | 服务器成功返回用户请求的数据 |
| 401 | `Unauthorized` | 表示用户没有权限（令牌、用户名、密码错误） |
| 403 | `Forbidden` | 表示用户得到授权（与401错误相对），但是访问是被禁止的 |
| 404 | `Not Found` | 用户发出的请求针对的是不存在的记录，服务器没有进行操作 |
| 500 | `Internal Server Error` | 服务器发生错误，用户将无法判断发出的请求是否成功。 |

## 3. 业务类

### 3.1. 模式

`{模块编号}{操作编号}{错误编号}`

### 3.2. 示例