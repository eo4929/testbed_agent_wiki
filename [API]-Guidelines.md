> API에 대한 간략한 설명
 
## Request

**Method**: `GET` `POST` `PUT` `DELETE`

**URL**: `/api/v0/examples/{path-param}?{query-param}`

**Auth**: `Required` `None`

* Header
  * `<Key>: <Value Type>, <Description>`
  ***
  * `auth-token`: `String`, 인증 토큰
  ***

**Parameters**: `Required` `None`

* Path
  * `<Key>: <Value Type>, <Description>`
  ***
  * `path-param`: `String`, 경로에 넣은 파라매터
  ***

* Query
  * `<Key>: <Value Type>, <Description>`
  ***
  * `query-param`: `Integer`, 경로 뒤에 쿼리로 넣은 파라매터 
  ***

* Body (form)
  * `<Key>: <Value Type>, <Description>`
  ***
  * `form-param`: `String`, 바디에 쿼리로 넣은 파라매터
  ***

* Body (json)
  * Header
    * `Content-Type: application/json`
  * Body
    * `<Key>: <Value Type>, <Description>` & `json schema`
    ***
    * `jsonParamA`: `String`, 바디에 json으로 넣은 파라매터 A
    * `jsonParamB`: `Array`, 바디에 json으로 넣은 파라매터 B
    ```json
    {
      "jsonParamA": "jsonParamA in HTTP Request Body",
      "jsonParamB": ["jsonParamB", "in", "HTTP", "Request", "Body"]
    }
    ```
    ***

## Response
* `<Key>: <Value Type>, <Description>` & `json schema`

***
#### 200 Success Response
* `responseDataA`: `String`, 응답 결과에 포함된 데이터 A에 대한 설명
* `responseDataB`: `Array`, 응답 결과에 포함된 데이터 B에 대한 설명
```json
    {
      "responseDataA": "response Data A in response body",
      "responseDataB": ["response", "Data", "B"]
    }
```
***
#### 404 Resource Not Found
* `errorMessage`: `String`, 에러에 대한 메세지
```json
    {
      "errorMessage": "Resource Not Found."
    }
```
***
#### 401 Authentication Error
* `errorMessage`: `String`, 에러에 대한 메세지
```json
    {
      "errorMessage": "Authentication Error."
    }
```
***
#### 500 Internal Server Error
* `errorMessage`: `String`, 에러에 대한 메세지
```json
    {
      "errorMessage": "Internal Server Error."
    }
```
