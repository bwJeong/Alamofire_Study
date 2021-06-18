# Alamofire_Study

## Alamofire
- Swift의 URLSession 기반 HTTP 네트워크 통신 라이브러리

### Request
- GET: HTTP 메세지의 헤더에 데이터를 추가해 전달하는 방식
```swift
// 1. 쿼리스트링 사용
AF.request("https://httpbin.org/get?foo=bar")

// 2. 파라미터 변수 사용
let parameters = ["foo": "bar"]
AF.request("https://httpbin.org/get", parameters: parameters)
```
- POST: HTTP 메세지의 Body에 데이터를 추가해 전달하는 방식
