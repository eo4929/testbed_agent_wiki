> 현재 리소스의 bound 여부와 bound된 사용자의 ID를 반환한다. 

## Request

**Method**: `GET`

**URL**: `/`

**Auth**: `None`

**Parameters**: `None`

**Samples**:
```
curl -X GET http://143.248.41.159:5000/
```

## Response

#### 200 Success Resposne
* `bound`: `Integer`, bound:1, unbound:2
* `userID`: `String`, 사용자 ID
```json
    {
      "bound": 1,
      "userID": "213",
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