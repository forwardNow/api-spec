# 设计原则（约定）

* 数据交换格式为：JSON。即 `Content-Type: application/json;charset=UTF-8`
* HTTP 请求方法强制为 `POST`。
* HTTP 响应状态码强制为 200。
* HTTP 响应体必须满足规定的格式。
* API 接口必须详细说明
  * 请求体 JSON 数据每个属性的类型、意义（说明）、是否可省略
  * 响应体 JSON 数据每个属性的类型、意义（说明）