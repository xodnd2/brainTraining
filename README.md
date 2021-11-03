# brainTraining

(폴더가 100개 이상이라)폴더 자체로 추가가 안돼서 압축하여 올립니다..

유저 데이터를 활용하기로 한 부분이 아직 좀 미흡하지만, 차차 완성해보도록 하겠습니다.

부족한 실력으로 직접 여러 기능을 구현해보려고 하니, 시간도 좀 부족했고 비효율적인 코드들도 많이 있는 것 같습니다..

특히나 데이터를 조작하는 부분에 있어서 제가 무지한게 많아 코드가 많이 더러워진 듯 합니다.

발표도 제대로 준비하지 못해서 횡설수설한거 같아 여러모로 아쉬움이 많습니다 ㅠㅠ
(코드를 너무 많이 짜다보니까 제가 짠 코드도 순간 기억이 잘 안났습니다..)

다음 프로젝트에서는 기능은 좀 더 줄이더라도, 더 탄탄하게 코드를 짤 수 있도록 하겠습니다. 

또한 발표도 좀 더 스무스하게 할 수 있도록 노력해보겠습니다.

***폴더 설명***\
Base 폴더 : 기본적인 뼈대 폼 모음\
Test 폴더 : 각각 테스트들의 폼 모음\
Data 폴더 : 데이터를 관리하는 클래스거나 , 프로퍼티를 지닌 클래스들 모음.\
            ㄴDataManager.cs 전체적인 데이터를 관리하는 메소드 모음. \
            ㄴRecordCalculate.cs 테스트 결과를 나이로 변환, 분/초/밀리초 단위로 변환 등. \

***의문점(?)***\n
분명 1000밀리초가 1초인데, 윈폼 타이머로 60밀리초가 1초에 가까움..\
https://smartfactory121.tistory.com/90 (이곳 참조)\
            
***MySQL 테이블 생성 명령어***\

create table user (\
  id varchar(20) not null,\
  pwd varchar(20) not null,\
  birth date not null,\
  bestbrain int default 0,\
  curbrain int default 0,\
  curbraindate date default '2000-01-01',\
  curlogindate date default '2000-01-01',\
  primary key(id)\
);\

create table record (\
  id varchar(20) not null,\
  date date not null,\
  brainage int default 0,\
  순서연결 int default 0,\
  가위바위보 int default 0,\
  계산25회 int default 0,\
  고속세기 int default 0,\
  기억5X5 int default 0,\
  연속뺄셈 int default 0,\
  primary key(id, date),\
  FOREIGN KEY(id) REFERENCES user(id) ON DELETE CASCADE\
);\
