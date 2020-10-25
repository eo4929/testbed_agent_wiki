> 새로운 유튜브 비디오를 실행시킨다. 

## Request

**Method**: `POST`

**URL**: `/resource/youtube`

**Auth**: `Required`

* Header
  * `USER-ID`: `Integer`, 요청하는 사용자의 아이디

**Parameters**: 
    `video_id`: `String`, 요청하고자 하는 유튜브 비디오의 아이디

**Samples**:
```
curl -X POST http://143.248.49.87:8000/resource/youtube \