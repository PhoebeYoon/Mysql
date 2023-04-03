###### :cactus:  Mysql

## 이 수업에서는 이런것을 배웁니다
1. sql의 기초문법이해   
    - 데이터베이스의 개념
    - Sql vs no Sql 뭔지
    - 관계형데이터베이스 mysql의 설치 및 실행
    - mysql를 터미널를 통해 배워보기
    - sql 문의 각종 연산자
    - sql로 데이터베이스 만들기
    - sql로 테이블생성,삭제
    - sql로 필드생성, 삭제, 변경    
2. sql의 데이터다루기   
    - workbench를 통한 디비관리
    - 데이터의 검색에 관련된 자주 사용하는 명령어
    - 데이터의 수정에 관련된 자주 사용하는 명령어
    - JSON데이터 타입 사용하기   
3. mysql를 활용한 응용
    - node.js를 활용한 웹사이트 만들기     
(위 과정은 전체코스입니다 1,2는 함께 진행되고 3는 별도로 진행됩니다.)

### 실습 순서
 - lesson01
 - 연습문제1,2
 - lesson02
 - 


## 데이타베이스 개념
### 데이터 ( Data ) 란 
데이터에 대한 다양한 설명들이 있겠지만 모두 동일한 것을 가리키고 있습니다. 우리 주변에 있는 모든 것이 데이터입니다. 컴퓨터에 저장된 내용 뿐 아니라 우리를 포함한 모든 것들이 '데이터' 입니다. 다만 이런 데이터들이 특정한 상황과 만나서 '정보'로 거듭나는 것입니다. 
### 정보 (infomation)란  
홍길동의 핸드폰은 010-1111-2222 라고 가정한다면 '010-1111-2222' 자체로는 별의미가 없는 데이터입니다. 그러나 이 데이터가 결제시스템과 만난다면 이 숫자들은 '인증'에 사용되는 정보가 될 것이고 '핸드폰결제'에 이용될 수 있는 유용한 정보가 될 것이다. 
그럼 이 많은 정보를 어떻게 저장하고 관리해야 할까요?  사람들의 머리속에 모두 외울수는 없는 일입니다. 
그래서 이것들을 저장하고 관리하는 개념과 시스템이 필요한 것입니다    
또한 정보는 매우 다양한 형태로 이루어져 있습니다. 예를 들어 '1588-1000' 과 '일오팔팔-천'을 우리는 동일하다고 생각할 수 있지만 이 둘을 같은 그룹에 넣은 것은 좋은 생각이 아닙니다. 그래서 정보의 형태를 구분하고 어떤식으로 저장할지 또 어떻게 관리할지를 지정하고 이런 데이터가 필요한 모든 사람이 같은 방식으로 이용하도록 해야 합니다.    
그렇지 않으면 데이터가 변형되거나 변경될때 어떤 사람은 알고있지만 어떤 사람은 모르는 경우가 발생할 수도 있고 사람마다 사용하는 언어와 동일한 데이터도 표현하는 방식이 다르니 혼선이 있을 것입니다 여기에 관리해주는 시스템으로써 <b>DBMS(Database Management System) </b>가 등장한 것입니다.   
우리가 일상적으로 접하는 마이크로소프트의 '액세스'가 작은 규모의 데이데베이스 관리프로그램중의 하나입니다. 

### RDBMS에서의 관계란?
우리는 RDBMS를 알아볼 것이며 그중 MySQL이라는 프로그램을 이용할 것입니다. 관계형이라는 말을 어렵게 생각할 필요가 없습니다. 그리고 아래의 이미지처럼 '출석부'와 '학생기록부'는 서로 다른 물리적인 서류가 있는데 이둘은 서로 관계를 맺고 있습니다. 
두 서류에서 말하는 '홍길동'이라는 학생은 모두 같은 사람을 지칭함합니다. 이것이 바로 관계형의 의미입니다.   또한 관계형 데이터베이스는 엑셀로 비유할 수 있습니다.  
    
 <img width="380" alt="스크린샷 2023-03-30 오후 6 26 33" src="https://user-images.githubusercontent.com/48478079/228792387-188f8c0e-f71a-4f17-bbd3-c2189dafb193.png">   
 <img width="380" alt="스크린샷 2023-03-30 오후 6 26 41" src="https://user-images.githubusercontent.com/48478079/228793347-80cabc42-c67a-4781-9675-4307f30b5496.png">

더 설명할 것이 있지만 요약해서 말하자면 데이터베이스는  
'자료의 중복을 배제한 ', ' 컴퓨터가 접근할 수 있는 저장매체에 저장된 ' , '고유한 업무를 수행하는데 반드시 필요한','여러 응용시스템이 공동으로 소유하고 유지하는 자료' 입니다. 
그럼 이제 다음으로 필요한 것은 이러한 데이터베이스를 만들기 위해 '어떤식으로' 만들지를 정할 필요가 있습니다.  
이쯤해서 등장하는 것이 <b>RDMBS 와 NoSQL ( Not Only SQL ) </b>입니다.  
RDMBS는 관계형 데이터베이스를 말하는데 여러개의 테이블이 특정한 <b>'관계'</b> 로 이루어져있는 구조를 가진 데이터베이스이며,   
NoSQL(Not Only SQL): 데이터-테이블간의 관계를 정의하지 않는 데이터베이스입니다. 
그런데 NoSQL를 말하면서 '스키마가 없다'라는 말이 붙어다니는 것을 보실 수 있습니다. 스키마가 뭔지 설명해 보겠습니다. 
### 스키마란 데이터베이스의 구조를 전반적으로 기술한 것을 말합니다.
스키마는 데이터베이스의 구조를 개체(Entity), 속성(Attribute), 관계(Relationship)로 정의하고 있습니다. 
- 외부스키마: 사용자 입장에서 정의한 데이터베이스의 논리적구조로 데이터들을 어떤 형식, 구조, 어떤 화면을 통해 사용자에게 보여줄지에 대한 정의입니다. 
- 개념스키마 : 데이터베이스의 전체적인 논리적 구조를 말합니다.
- 내부스키마 : 물리적 저장장치의 입장에서 본 데이터베이스의 구조입니다.
이렇게까지만 설명하겠습니다. 일단 실습을 위해서는 이런 정도로만 이해해도 될듯합니다. (더 자세히하면 아마 모두 수업을 떠나실듯합니다 )
그럼 sql이라는 것은 뭘까요 ?
### SQL(Structured Query Language)로 데이터베이스에서 데이터를 정의, 조작, 제어하기 위해 사용되는 언어입니다.   
즉 구조화된 질문을 하는 언어라는 뜻입니다 무슨 말이냐하면 데이터베이스에서 원하는 정보를 꺼내올때 그냥 아무렇게나 물어보면 안된다는 것입니다. 사람의 뇌는 글자가 조금 틀려도 문장의 앞뒤가 바뀌어도 이해하지만 얘는 그렇지 않다는 것입니다. 주어진 형식대로 질문을 해야 이해하고 답변을 한다는 것입니다. 

위에서 설명한 내용은 데이터베이스라는 것을 설명한 것입니다. 

## 그럼 우리가 다룰  mySql는 뭔가요?
데이터베이스를 종이에 적어서 관리할 수는 없잖아요. 그래서 관리해주는 프로그램을 만들었는데 이걸 DBMS라고 부릅니다. 
대표적으로 MySQL, 오라클(Oracle), SQL 서버, MariaDB 등이 있습니다.    

| DBMS|	제작사|	작동운영체제	| 기타 |
|----|---|---|---|
| MySQL	|Oracle	|Unix, Linux, Windows, Mac	|오픈 소스(무료), 상용|
| MariaDB|MariaDB	 |Unix, Linux, Windows	|오픈 소스(무료),MySQL 초기 개발자들이 독립해서 만듦|
|Oracle|	Oracle	|Unix, Linux, Windows|	상용 시장 점유율 1위|
| Access |	Microsoft|	Windows	|PC용|
| SQLite	|SQLite	|Android, iOS	|모바일 전용, 오픈 소스(무료)|

