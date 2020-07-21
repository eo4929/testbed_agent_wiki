> 블라인드를 자신이 원하는 높낮이로 설정한다.

## Request

**Method**: `POST`

**URL**: `/resource/position`

**Auth**: `Required`

* Header
  * `USER-ID`: `Integer`, 요청하는 사용자의 아이디

**Parameters**: `Required`

* Body (form)
  * `position`: `Integer`, 사용자가 원하는 블라인드의 높낮이 값 (0 - 전부 열려있음, 100 - 전부 닫혀있음)

**Samples**:
```
curl -X POST http://143.248.49.87:8000/resource/position \
--header "USER-ID: {UserId}" \
--form "position={position}"
```

## Response

#### 200 Success Response
* `action`: `String`, 실행된 커맨드의 이름
* `status`: `String`, 실행 여부 ("success" - 성공)
```json
    {
      "action": "position",
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
***
#### 400 The position value should be provided.
`errorMessage`: `String`, 에러에 대한 메세지
```json
    {
      "errorMessage": "The position value should be provided."
    }
```
***
#### 400 The position value should be 0-100.
`errorMessage`: `String`, 에러에 대한 메세지
```json
    {
      "errorMessage": "The position value should be 0-100."
    }
```