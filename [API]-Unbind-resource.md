> 현재 리소스에 bound 된 사용자를 unbind 한다.

## Request

**Method**: `POST`

**URL**: `/user/unbind`

**Auth**: `Required`

* Header
  * `USER-ID`: `Integer`, 요청하는 사용자의 아이디

**Parameters**: `None`

**Samples**:
```
curl -X POST http://143.248.41.173:8000/user/unbind \
--header "USER-ID: {UserId}"
```

## Response

#### 200 Success Resposne
`userID`: `String`, Unbound 된 사용자 ID
```json
    {
      "userId": "13"
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