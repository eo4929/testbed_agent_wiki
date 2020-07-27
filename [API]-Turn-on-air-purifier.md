> air purifier를 Turn on한다. 이미 Turn on된 상태에서도 동작한다.

## Request

**Method**: `POST`

**URL**: `/resource/on`

**Auth**: `Required`

* Header
  * `USER-ID`: `Integer`, 요청하는 사용자의 아이디

**Parameters**: `None`

## Response

#### 200 Success Response
* `status`: `String`, air purifier on/off 여부
```json
    {
      "status": "on"
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
#### 400 Actuation failed
`errorMessage`: `String`, 에러에 대한 메세지
```json
    {
      "errorMessage": "Actuation failed."
    }
```