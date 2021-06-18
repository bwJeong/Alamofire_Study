# Alamofire_Study

## Alamofire
- Swift의 URLSession 기반 HTTP 네트워크 통신 라이브러리

### Request
- GET: URL에 쿼리스트링을 추가해 데이터를 전달하는 방식
```swift
AF.request("https://httpbin.org/get")

// method의 default는 .get
// AF.request("https://httpbin.org/get", method: .get) 와 동일한 기능을 수행한다.


```
- POST: HTTP 메세지의 헤더에 데이터를 추가해 전달하는 GET 방식과는 다르게, HTTP 메세지의 Body에 데이터를 추가해 전달하는 방식
