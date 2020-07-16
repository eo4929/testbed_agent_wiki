# Please CHECK YOUR DESCRIPTION before committing!
[http://json.parser.online.fr/](http://json.parser.online.fr/)

~~~javascript
{
    "@context":"https://www.w3.org/2019/wot/td/v1",
    "id": "urn:dev:ops:32473-WoTLamp-1234",
    "title": "ChromeCast",
    "securityDefinitions": {
        "basic_sc": {"scheme": "basic", "in":"header"}
    },
    "security": ["basic_sc"],
    "properties": {
        "status": {
            "type": "string",
            "forms": [{
                "href": "https://mylamp.example.com/status"
            }]
        }
    },
    "actions": {
        "start": {
            "title": "start video file",
            "description": "start new youtube video.",
            "uriVariables": {
                "video_id" : { "type": "string"}
            }, 
            "forms": [{
                "href": "https://mylamp.example.com/start{?video_id}",
                "htv:methodName": "GET"
            }]
        },
       "pause": {
            "title": "pause video",
            "description": "pause current video.",
            "forms": [{
                "href": "https://mylamp.example.com/pause",
                "htv:methodName": "GET"
            }]
       },
       "play": {
            "title": "play video",
            "description": "play current video.",
            "forms": [{
                "href": "https://mylamp.example.com/play",
                "htv:methodName": "GET"
            }]
       },
       "stop": {
            "title": "stop video",
            "description": "stop current video.",
            "forms": [{
                "href": "https://mylamp.example.com/stop",
                "htv:methodName": "GET"
            }]
       },
       "youtube": {
            "title": "youtube video",
            "description": "start new youtube video.",
            "uriVariables": {
                "video_id" : { "type": "string"}
            }, 
            "forms": [{
                "href": "https://mylamp.example.com/youtube{?video_id}",
                "htv:methodName": "GET"
            }]
       }
    }
}
~~~