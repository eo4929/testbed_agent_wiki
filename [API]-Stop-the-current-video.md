> 현재 비디오를 실행 중단시킨다.  

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