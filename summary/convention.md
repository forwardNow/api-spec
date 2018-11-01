# 设计原则（约定）

* 数据编码为 UTF-8。
* 数据交换格式为：JSON。即 `Content-Type: application/json`
* 所有的 HTTP 请求的方法强制为 POST。
* 所有的 HTTP 响应状态码强制为 200。
* HTTP 响应体必须满足指定格式。