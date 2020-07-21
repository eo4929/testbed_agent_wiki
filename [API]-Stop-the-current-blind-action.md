> 진행중이던 블라인드 액션을 즉시 중단한다. 이 과정에서 `state` 속성 값은 중단된 위치로 갱신되지 않기 때문에, 실제 물리적인 높낮이와 `state` 속성 값이 일치하지 않게 된다.

## Request

**Method**: `POST`

**URL**: `/resource/stop`

**Auth**: `Required`

* Header
  * `USER-ID`: `Integer`, 요청하는 사용자의 아이디

**Parameters**: `None`

**Samples**:
```
curl -X POST http://143.248.49.87:8000/resource/stop \
--header "USER-ID: {UserId}"
```

## Response

#### 200 Success Response
* `action`: `String`, 실행된 커맨드의 이름
* `status`: `String`, 실행 여부 ("success" - 성공)
```json
    {
      "action": "stop",
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
