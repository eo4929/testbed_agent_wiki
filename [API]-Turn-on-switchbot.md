> Switchbot을 Turn on한다. 이미 Turn on된 상태에서도 동작한다.

## Request

**Method**: `POST`

**URL**: `/resource/turnon`

**Auth**: `Required`

* Header
  * `USER-ID`: `Integer`, 요청하는 사용자의 아이디

**Parameters**: `None`

## Response

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