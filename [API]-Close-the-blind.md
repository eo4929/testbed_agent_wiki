> 블라인드를 끝까지 닫는다. 

## Request

**Method**: `POST`

**URL**: `/resource/close`

**Auth**: `Required`

* Header
  * `USER-ID`: `Integer`, 요청하는 사용자의 아이디

**Parameters**: `None`

**Samples**:
```
curl -X POST http://143.248.49.87:8000/resource/close \
--header "USER-ID: {UserId}"
```

## Response

#### 200 Success Response
* `action`: `String`, 실행된 커맨드의 이름
* `status`: `String`, 실행 여부 ("success" - 성공)
```json
    {
      "action": "close",
      "status": "success"
    }
```
***
#### 401 Authentication Failed
`errorMessage`: `String`, 에러에 대한 메세지
```json
    {
      "errorMessage": "Authentication Failed."
    }
```
***
#### 401 Resource not bound
`errorMessage`: `String`, 에러에 대한 메세지
```json
    {
      "errorMessage": "Resource not bound."
    }
```
***
#### 409 Resource bound to another user
`errorMessage`: `String`, 에러에 대한 메세지
```json
    {
      "errorMessage": "Resource bound to another user."
    }
```
***
#### 400 Invalid action
`errorMessage`: `String`, 에러에 대한 메세지
```json
    {
      "errorMessage": "Invalid action."
    }
```
