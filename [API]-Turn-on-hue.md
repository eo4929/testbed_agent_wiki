> Switchbot을 Turn on한다. 이미 Turn on된 상태에서도 동작한다.

## Request

**Method**: `POST`

**URL**: `/resource/on`

**Auth**: `Required`

* Header
  * `USER-ID`: `Integer`, 요청하는 사용자의 아이디

**Parameters**: `None`

**Samples**:
```
curl -X POST http://143.248.41.159:5000/resource/on \
--header "USER-ID: {UserId}"
```

## Response

#### 200 Success Response
`String`, 스위치 on 성공여부에 대한 메시지
```json
    "[{\"success\":{\"/lights/2/state/on\":true}},{\"success\":{\"/lights/2/state/hue\":10000}},{\"success\":{\"/lights/2/state/sat\":254}},{\"success\":{\"/lights/2/state/bri\":254}}]"
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
#### 400 Actuation failed
`errorMessage`: `String`, 에러에 대한 메세지
```json
    {
      "errorMessage": "Actuation failed."
    }
```