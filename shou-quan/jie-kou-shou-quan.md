# 接口授权

## 获取授权

系统所有请求都会需要授权验证，通过系统提授权接口获取token，该token有效期为24小时，过期之后需要重新获取token。

## 授权使用

系统所有接口请求发送http请求时，需要在请求头添加Authorization属性，值为通过授权接口获取的token值。

## 示例\(请求头\)

```text
General
    Request URL:http://192.168.2.100:5513/api-center/train/stations
    Request Method:GET
    Status Code:200 
    Remote Address:192.168.2.100:5513
    Referrer Policy:no-referrer-when-downgrade
Response Headers
    Access-Control-Allow-Origin:*
    Content-Type:application/json;charset=UTF-8
    Date:Fri, 03 Aug 2018 10:41:15 GMT
    Set-Cookie:JSESSIONID=18F5B41DA8ED654A5C64E987E999EEFB; Path=/api-center; HttpOnly
    Transfer-Encoding:chunked
    Vary:Origin
    X-Application-Context:application:dev:5513
Request Headers
    Accept:application/json
    Accept-Encoding:gzip, deflate
    Accept-Language:zh-CN,zh;q=0.9
    Authorization:eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJleHAiOjg3MzY2ODk4MTUwMzMsInBheWxvYWQiOiJ7XCJpZFwiOjEsXCJuYW1lXCI6XCLlvKDkuIlcIixcInJlbWFya1wiOlwi5rWL6K-V6LSm5Y-3XCIsXCJjdXN0b21lck5vXCI6XCIwMTUxMDEzNlwiLFwiYXBwa2V5XCI6XCJ6aGFuZ3NhblwiLFwiYXBwc2VjcmV0XCI6XCJlMTBhZGMzOTQ5YmE1OWFiYmU1NmUwNTdmMjBmODgzZVwiLFwiY3JlYXRlZEJ5XCI6XCJcIixcImNyZWF0ZWRUaW1lXCI6MTUyMjMwMTM1MTAwMCxcImxhc3RVcGRhdGVkQnlcIjpudWxsLFwibGFzdFVwZGF0ZWRUaW1lXCI6MTUyMjMwMTM1NTAwMCxcImlzUGF5TWVtYmVyXCI6XCIwXCJ9In0.OZMa4fe2K1khxXlENDblPTAswpmC89lb6thS9vHQ8bw
    Connection:keep-alive
    Host:192.168.2.100:5513
    Origin:http://xunlian.55555.io:8082
    Referer:http://xunlian.55555.io:8082/sosoapi-web/auth/apidoc/preview.htm?docId=4
    User-Agent:Mozilla/5.0 (Windows NT 6.1; WOW64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/63.0.3239.84 Safari/537.36
```

注意请求头中的 

```text
Authorization:eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJleHAiOjg3MzY2ODk4MTUwMzMsInBheWxvYWQiOiJ7XCJpZFwiOjEsXCJuYW1lXCI6XCLlvKDkuIlcIixcInJlbWFya1wiOlwi5rWL6K-V6LSm5Y-3XCIsXCJjdXN0b21lck5vXCI6XCIwMTUxMDEzNlwiLFwiYXBwa2V5XCI6XCJ6aGFuZ3NhblwiLFwiYXBwc2VjcmV0XCI6XCJlMTBhZGMzOTQ5YmE1OWFiYmU1NmUwNTdmMjBmODgzZVwiLFwiY3JlYXRlZEJ5XCI6XCJcIixcImNyZWF0ZWRUaW1lXCI6MTUyMjMwMTM1MTAwMCxcImxhc3RVcGRhdGVkQnlcIjpudWxsLFwibGFzdFVwZGF0ZWRUaW1lXCI6MTUyMjMwMTM1NTAwMCxcImlzUGF5TWVtYmVyXCI6XCIwXCJ9In0.OZMa4fe2K1khxXlENDblPTAswpmC89lb6thS9vHQ8bw
```



