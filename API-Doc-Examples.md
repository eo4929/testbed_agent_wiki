> API에 대한 간략한 설명
 
## Request

**Method**: `POST`

**URL**: `/api/v0/examples/{path-param}?{query-param}`

**Auth**: `Required`

* Header
  * `<Key>: <Value Type>, <Description>`
  * e.g., `auth-token`: `Integer`, 인증 토큰

**Parameters**

* Path
  * `<Key>: <Value Type>, <Description>`
  * e.g., `path-param`: `String`, 경로에 넣은 파라매터

* Query
  * `<Key>: <Value Type>, <Description>`
  * e.g., `query-param`: `Integer`, 경로 뒤에 쿼리로 넣은 파라매터 

* Body (form)
  * `<Key>: <Value Type>, <Description>`
  * e.g., `form-param`: `String`, 바디에 쿼리로 넣은 파라매터 

* Body (json)
  * e.g.,

    `JsonParamA`: `String`, 바디에 json으로 넣은 파라매터 A

    `JsonParamB`: `Array`, 바디에 json으로 넣은 파라매터 B
    ```json
    {
      "JsonParamA": "JsonParamA in HTTP Request Body",
      "JsonParamB": ["JsonParamB", "in", "HTTP", "Request", "Body"]
    }
    ```

## Response

**e.g.,**
***
#### 200 Success Resposne
`ResponseDataA`: `String`, 응답 결과에 포함된 데이터 A에 대한 설명

`ResponseDataB`: `Array`, 응답 결과에 포함된 데이터 B에 대한 설명
```json
    {
      "ResponseDataA": "Response Data A in response body",
      "ResponseDataB": ["Response", "Data", "B"]
    }
```
***
#### 404 Resource Not Found
`Message`: `String`, 에러에 대한 메세지
```json
    {
      "Message": "Resource Not Found."
    }
```
***
#### 401 Authentication Error
`Message`: `String`, 에러에 대한 메세지
```json
    {
      "Message": "Authentication Error."
    }
```
***
#### 500 Internal Server Error
`Message`: `String`, 에러에 대한 메세지
```json
    {
      "Message": "Internal Server Error."
    }
```
***
