> API에 대한 간략한 설명이 들어간다.
 
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

    `json-param0`: `String`, 바디에 json으로 넣은 파라매터0

    `json-param1`: `Array`, 바디에 json으로 넣은 파라매터1
    ```json
    {
      "json-param0": "json-pram0 in HTTP Request Body",
      "json-param1": ["json-param1", "in", "HTTP", "Request", "Body"]
    }
    ```

## Response

