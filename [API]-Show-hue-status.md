> 현재 hue 리소스의 status를 반환한다. 

## Request

**Method**: `GET`

**URL**: `/resource`

**Auth**: `Required`

* Header
  * `USER-ID`: `Integer`, 요청하는 사용자의 아이디

**Parameters**: `None`

**Samples**:
```
curl -X GET http://143.248.41.159:8000/resource \
--header "USER-ID: {UserId}"
```

## Response

#### 200 Success Response
`String`, hue의 status를 나타내는 메시지
```
 {\"state\":{\"on\":false,\"bri\":254,\"hue\":10000,\"sat\":254,\"effect\":\"none\",\"xy\":[0.5711,0.3986],\"ct\":500,\"alert\":\"none\",\"colormode\":\"hs\",\"mode\":\"homeautomation\",\"reachable\":true},\"swupdate\":{\"state\":\"noupdates\",\"lastinstall\":\"2020-05-23T05:26:49\"},\"type\":\"Extended color light\",\"name\":\"Hue color downlight 2\",\"modelid\":\"LCT002\",\"manufacturername\":\"Signify Netherlands B.V.\",\"productname\":\"Hue color downlight\",\"capabilities\":{\"certified\":true,\"control\":{\"mindimlevel\":5000,\"maxlumen\":630,\"colorgamuttype\":\"B\",\"colorgamut\":[[0.6750,0.3220],[0.4090,0.5180],[0.1670,0.0400]],\"ct\":{\"min\":153,\"max\":500}},\"streaming\":{\"renderer\":true,\"proxy\":false}},\"config\":{\"archetype\":\"floodbulb\",\"function\":\"mixed\",\"direction\":\"downwards\",\"startup\":{\"mode\":\"safety\",\"configured\":true}},\"uniqueid\":\"00:17:88:01:00:e2:11:07-0b\",\"swversion\":\"5.127.1.26581\"}
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