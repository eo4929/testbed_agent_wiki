> Switchbot을 Turn off한다. 이미 Turn off된 상태에서도 동작한다.

## Request

**Method**: `POST`

**URL**: `/resource/turnoff`

**Auth**: `Required`

* Header
  * `USER-ID`: `Integer`, 요청하는 사용자의 아이디

**Parameters**: `None`

**Samples**:
```
curl http://143.248.41.159:5000/resource/turnoff \
--header "USER-ID: {UserId}"
```

## Response

#### 200 Success Resposne
* `status`: `String`, 스위치 on/off 여부
```json
    {
      "status": "off"
    }
```
***
#### 401 User ID not authenticated
* `errorMessage`: `String`, 에러에 대한 메세지
```json
    {
      "errorMessage": "User ID not authenticated."
    }
```
***
#### 409 Resource bound to another user
* `errorMessage`: `String`, 에러에 대한 메세지
```json
    {
      "errorMessage": "Resource bound to another user."
    }
```
***
#### 400 Other Errors
* `errorMessage`: `String`, 에러에 대한 메세지
```json
    {
      "errorMessage": "Actuation failed. | No one bound. | Invalid action."
    }
```