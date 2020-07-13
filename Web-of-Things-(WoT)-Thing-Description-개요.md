0. 개요
W3C web of things의 주요 구성 요소이면서, Thing의 entry point이다. 웹사이트에서 index.html와 유사한 역할을 한다.

1. 주요 문법  
  > 1-0  Thing metadata  
  thing을 나타내는 metadata.  
  >>@context : document에 쓰일 규약을 판단함 **(필수)** 예) https://www.w3.org/2019/wot/td/v1   
  title : human-readble title을 제공, string
  description: human-readble 추가 정보를 제공, string
  created: description이 생성된 날, datetime, 예) "2018-11-14T19:10:23.824Z"
  modified: description이 갱신된 날짜. datetime,
  
  > 1-1. PropertyAffordance  
  thing의 state를 나타낸다. 이 state는 조회(read) 가능하고, 갱신(write, optional)이 가능할 수 있다. 
  
   
  > 1-2. ActionAffordance  
  > 1-3. EventAffordance  

2. HyperMedia Control 문법
3.  
