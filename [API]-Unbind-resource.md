> 사용자가 리소스 사용을 완료하고 unbind 한다.

## Request

**Method**: `POST`

**URL**: `/user/unbind`

**Auth**: `Required`

* Header
  * `USER-ID`: `Integer`, 요청하는 사용자의 아이디

**Parameters**: `None`

**Samples**:
```
curl http://143.248.41.159:5000/user/unbind \
--header "USER-ID: {UserId}"
```

## Response

#### 200 Success Resposne
`userID`: `String`, Unbound 된 사용자 ID
```json
    {
      "userID": "13"
    }
```
***
#### 401 User ID not authenticated
`errorMessage`: `String`, 에러에 대한 메세지
```json
    {
      "errorMessage": "User ID not authenticated."
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
#### 400 Other Errors
`errorMessage`: `String`, 에러에 대한 메세지
```json
    {
      "errorMessage": "No one bound. | Invalid action."
    }
```