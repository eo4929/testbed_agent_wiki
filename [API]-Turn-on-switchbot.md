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
`status`: `String`, 스위치 on/off 여부
```json
    {
      "status": "on"
    }
```
```json
    {
      "status": "off"
    }
```
***
#### 401 User ID not authenticated
`Message`: `String`, 에러에 대한 메세지
```json
    {
      "Message": "User ID not authenticated."
    }
```
***
#### 409 Resource bound to another user
`Message`: `String`, 에러에 대한 메세지
```json
    {
      "Message": "Resource bound to another user."
    }
```
***
#### 400 Other Errors
`Message`: `String`, 에러에 대한 메세지
```json
    {
      "Message": "Actuation failed. | No one bound. | Invalid action."
    }
```