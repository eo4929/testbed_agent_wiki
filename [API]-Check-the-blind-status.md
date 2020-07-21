> 블라인드의 높낮이 상태(state)와 배터리 잔량(battery)을 확인할 수 있다.

## Request

**Method**: `GET`

**URL**: `/resource`

**Auth**: `Required`

* Header
  * `USER-ID`: `Integer`, 요청하는 사용자의 아이디

**Parameters**: `None`

**Samples**:
```
curl -X GET http://143.248.49.87:8000/resource \
--header "USER-ID: {UserId}"
```

## Response

#### 200 Success Response
* `state`: `Integer`, 블라인드의 현재 높낮이 상태 (0 - 전부 열려있음, 100 - 전부 닫혀있음)
* `battery`: `Integer`, 배터리 잔량 (잔량 값은 0 이하 혹은 100 이상의 값을 가질 수 있으며, 0 이하인 경우 블라인드가 작동하지 않음)
```json
    {
      "state": 25,
      "battery": 97
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