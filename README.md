# Alamofire_Study

## Alamofire
- Swift의 URLSession 기반 HTTP 네트워크 통신 라이브러리

### Request
```swift
func request(_ convertible: URLConvertible, 
             method: HTTPMethod = .get, 
             parameters: Parameters? = nil, 
             encoding: ParameterEncoding = URLEncoding.default, 
             headers: HTTPHeaders? = nil, 
             interceptor: RequestInterceptor? = nil, 
             requestModifier: RequestModifier? = nil) -> DataRequest
```
- GET
  - HTTP 메세지의 헤더에 데이터를 추가해 전달하는 방식
```swift
// 1. 쿼리스트링 사용
AF.request("https://httpbin.org/get?foo=bar")

// 2. 파라미터 변수 사용
// URL에 파라미터 변수로 만든 쿼리스트링이 추가되어 전달되기 때문에 1.과 동일
let parameters = ["foo" : "bar"]
AF.request("https://httpbin.org/get", parameters: parameters)
```
- POST
  - HTTP 메세지의 Body에 데이터를 추가해 전달하는 방식
```swift
let parameters = ["foo" : "bar"]
AF.request("https://httpbin.org/post", method: .post, parameters: parameters)
```

### Response
- Response는 async로 진행되므로, 이후의 작업 또한 async로 진행해야 함
- response, responseData, responseString, responseJSON, responseDecodable와 같은 다양한 기능을 제공
```swift
// 간단 예시
AF.request(url).responseJSON { response in
  switch response.result {
    case .success(let res):
      // ...
    case .failure(let err):
      // ...
  }
}
```
