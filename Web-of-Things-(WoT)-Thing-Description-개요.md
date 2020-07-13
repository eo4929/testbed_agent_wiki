# 0. 개요
W3C web of things의 주요 구성 요소이면서, Thing의 entry point이다. 웹사이트에서 index.html와 유사한 역할을 한다.



# 1. 주요 문법  
  1-0  Thing metadata  
  thing을 나타내는 metadata.  
  >@context : document에 쓰일 규약을 판단함 **(필수)** 예) https://www.w3.org/2019/wot/td/v1   
  title : human-readble title을 제공, string
  description: human-readble 추가 정보를 제공, string
  created: description이 생성된 날, datetime, 예) "2018-11-14T19:10:23.824Z"
  modified: description이 갱신된 날짜. datetime  
  
 ## 1-1. PropertyAffordance  
  thing의 state를 나타낸다. 이 state는 조회(read) 가능하고, 갱신(write, optional)이 가능할 수 있다.   
  >forms **(필수)** : 어떻게 기능이 작동할 지 설명하는 form, form의 array 형태 
   
 ##  1-2. ActionAffordance  
  thing의 function을 실행시킬 수 있다. thing의 state를 조작하거나 thing의 process를 시작할 수 있다. 
  >forms **(필수)** : 어떻게 기능이 작동할 지 설명하는 form, form의 array 형태 
  input: action의 input data schema를 정의한다. Data Schema
  output: action의 output data schema를 정의한다. Data Schema 
  
 ##  1-3. EventAffordance 
  비동기적으로 event data를 사용자에게 push한다.  
  >forms **(필수)** : 어떻게 기능이 작동할 지 설명하는 form, form의 array 형태 
  subscription: 구독(subscription)하기 위해 필요한 data schema를 정의한다. Data Schema 
  data: Thing에서 push되는 event의 data schema를 정의한다. Data Schema
  cancellation: 구독을 취소하기 위해 필요한 data schema를 정의한다. Data Schema
 

# 2. DataSchema 문법  
data format을 나타낸다.   
>@type: data schema의 type을 나타낸다. data schema의 type에 따라서 다르게 표현해 주어야하므로 매우 중요함. string    

가장 많이 쓰이는 것으로 보이는 ArraySchema와 ObjectSchema만 다루겠음.
 
 ## 2-1  ArraySchema
Array를 나타내는 data schema. @type에 array라고 표시된다
>items: array의 성질을 정의한다. DataSchema나 DataSchema의 Array
예)
~~~javascript
"rgb": {
        "title": "RGB color value",
        "type": "array",
        "items" : {
            "type" : "number",
            "minimum": 0,
            "maximum": 255
        },
        "minItems": 3,
        "maxItems": 3
    }
~~~

 ## 2-2 ObjectSchema  
Object를 나타내는 data schema. @type에 object라고 표시된다.
> properties : data schema nested definitions, Map of DataShema  
required: object의 어떤 변수들이 필수적(mandatory)인지를 정의함. Array of string

예)
~~~javascript
"properties": {
    "status": {
        "title": "Status",
        "type": "string",
        "enum": ["On", "Off", "Error"]
    },
    "brightness": {
        "title": "Brightness value",
        "type": "number",
        "minimum": 0.0,
        "maximum": 100.0
    },
    "rgb": {
        "title": "RGB color value",
        "type": "array",
        "items" : {
            "type" : "number",
            "minimum": 0,
            "maximum": 255
        },
        "minItems": 3,
        "maxItems": 3
    }
}
~~~


# 3. HyperMedia Control 문법
Thing에서 사용되는 web link와 web from들을 표현한다. 
## 3-1 Form 
form은 특정 operation을 실행시킬 수 있게 함, request method를 만들어서 submission target에게 보냄. 
>href **(필수)** : form의 submission target의 URI, anyURI
op: 
contenttype: media type에 따른 content 종류(text/plain 등)과, 잠재적인 인자(charset=utf-8 등)
htv:methodName: http의 수행 operation을 결정 "GET", "PUT", "POST"




