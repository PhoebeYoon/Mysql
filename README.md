###### :cactus:  Mysql

이전 수업내용에서 터미널에서 데이터베이스, 테이블, 필드수정을 해봤습니다. 그리고 기본적인 문자처리, 숫자처리 및 기본함수에 대해 알아보았습니다.  
그런데 터미널에서 타이핑으로 조작하는것이 생각보다 번거롭고 불편합니다. 그래서 이제부터는 좀 수월하게 데이터베이스를 다룰 수 있도록 workbench라는 프로그램을 사용해 보도록 하겠습니다.   



## workbench 실행
workbench는 개발을 도와주는 툴입니다. 예를 들어 웹페이지를 만들려고 할때, 메모장에서도 만들수 있지만 대부분은 vscode를 사용합니다. 왜냐하면 개발을 할때 쉽게 할수있기 때문입니다. 여러가지를 기능을 사용할 수 있으니 시간도 단축되고 에러도 쉽게 수정할 있습니다. 마찬가지로 터미널에서 명령을 일일이 입력하는 것보다 휠씬 수월합니다.     
프로그램에서 돌고래 아이콘을 실행시킵니다.   
여기서 주목한 것을 'MySQL Connections' 부분으로 root 와 localhost:3306 부분입니다. 아마 서버실습에서 포트에 대해 배우셨을 것입니다. 

클릭해서 실행하면 아래와 같이 나옵니다 

<img width="883" alt="스크린샷 2023-03-30 오후 8 54 22" src="https://user-images.githubusercontent.com/48478079/228828130-fb9eef49-4ce1-40cf-921a-8fdeac56da27.png">    
mysql설치시에 입력했던 비번을 입력하시면 됩니다. 

mac에서는 아래와 같은 화면이 나옵니다( 버전마다 조금씩 화면이 다릅니다. 아래 이미지는 최신버전입니다 )   
<img width="500" alt="스크린샷 2023-03-31 오후 7 58 26" src="https://user-images.githubusercontent.com/48478079/229102625-b56bbaff-dd21-4269-b84f-124d1446bcdf.png">


<img width="180" alt="스크린샷 2023-04-01 오후 9 47 09" src="https://user-images.githubusercontent.com/48478079/229289767-78983eec-3067-4657-bb2c-2ebfcb215673.png">

## workbench 화면설명
<img width="400" alt="스크린샷 2023-04-02 오후 9 46 05" src="https://user-images.githubusercontent.com/48478079/229353790-347feed7-32a5-4ae0-9d49-ac3d146e7f2f.png">     
터미널창에서 타이핑하여 주던 명령어들을 workbench에서는 '쿼리'탭을 열고 그곳에 입력한다. 실행할때는 번개모양 :zap: 아이콘을 클릭하면 된다. 여러줄을 입력했다면 그 명령들을 블록으로 지정하고 번개모양 :zap:을 클릭하면 된다.    
한줄만 실행할때는 ctrl + enter

주석처리는 문장앞에 -- (2개) 를 붙이면 됩니다.
 
