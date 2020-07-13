~~~javascrip
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
            "forms": [{
                "href": "https://mylamp.example.com/toggle"
            }]
        },
       "pause": {
            "title": "pause video",
            "description": "pause current video."
            "forms": [{
                "href": "https://mylamp.example.com/pause"
            }]
       },
       "play": {
            "title": "play video",
            "description": "play current video."
            "forms": [{
                "href": "https://mylamp.example.com/play"
            }]
       },
       "stop": {
            "title": "stop video",
            "description": "stop current video."
            "forms": [{
                "href": "https://mylamp.example.com/stop"
            }]
       },
       "youtube": {
            "title": "youtube video",
            "description": "start new youtube video.",
            "uriVariables": {
                "video_id" : { "type": "string"},
            }, 
            "forms": [{
                "href": "https://mylamp.example.com/youtube{?video_id}"
            }]
       },
    }
}
~~~