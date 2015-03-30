##이 설치 방법은 맥을 기준으로 한 것입니다.  
* ubuntu는 brew 대신 apt-get 명령어를 이용하시면 됩니다. 

#mysql
1) brew를 통한 설치  http://blog.saltfactory.net/121

2) path 찾아서 path 셋팅해주기 

    echo $PATH
    export PATH=$PATH:/usr/local/mysql/bin
    export PATH=$PATH:/usr/local/Cellar/mysql/5.6.22/bin
    (사람 마다 다를수 있음 찾아야 될듯함) 

3) mysql 시작하기

     mysql.server start
     mysql.server stop  - 안쓸대 중지 시키기

4) 패스워드 변경하기
     $mysqladmin -u root -p password new-password

위의 방법은 쉘에서 바로 실행하면 되지만, 암호가 히스토리에 남을수 있기 때문에 권하지 않습니다.

update문을 이용하여 root 암호 설정

     $ mysql -u root mysql
     mysql> update user set password = password('new-password') where user = 'root';
     mysql> flush privileges;

5) npm 셋팅   

     npm init 
     npm install mysql --save 


6) mysql workbench 찾아서 셋팅할 것 


#REDIS
* redis cheat sheet - http://lzone.de/cheat-sheet/Redis

1) brew를 통한 설치  http://cook.coredump.me/post/18886668039/brew-install-redis 

2) PATH 세팅하기

     echo P$ATH 
     export PATH=$PATH:/usr/local/opt/redis/bin
    

3) redis-stat 설치할 것 

https://github.com/junegunn/redis-stat/blob/master/README.md 

     gem install redis-stat

#mongo 
1)  mongodb 설치와 간단한 사용방법 

* http://docs.mongodb.org/manual/tutorial/install-mongodb-on-os-x/ 
* http://www.mkyong.com/mongodb/how-to-install-mongodb-on-mac-os-x/ 
* 명령어 참고만 http://daddycat.blogspot.kr/2013/02/mongodb-1.html
* mongod에 대한 이런 저런 글 모음 - http://linuxism.tistory.com/category/DB/MongoDB 

2) 도움이 되는 글 
* mongo db handling -  http://proserge.kh.ua/coding/index.php 에서 'mongodb for nodejs' 로 검색할것
* mongo sharding setting - http://mobicon.tistory.com/143
* mongo sharding 쉬운글 - http://queenyjina.tistory.com/48
* mongo operations bp - http://info.mongodb.com/rs/mongodb/images/10gen-MongoDB_Operations_Best_Practices.pdf

3)  mongo admin tool - http://docs.mongodb.org/ecosystem/tools/administration-interfaces/  (MMS 와 RoboMongo 추천) 

4)  sharding
* http://www.kchodorow.com/blog/2011/01/04/how-to-choose-a-shard-key-the-card-game/
* mongo sharding guide - http://docs.mongodb.org/v2.6/MongoDB-sharding-guide.pdf 
* http://docs.mongodb.org/manual/core/sharding/
* http://docs.mongodb.org/manual/core/sharded-cluster-mechanics/#sharding-internals-shard-keys
* 표준 편차 http://bcho.tistory.com/972
* Consistent Hashing  http://www.mimul.com/pebble/default/2012/05/04/1336102052449.html /  http://sarghis.com/blog/726/

5) 기타 사항
* mongo 인증 설정 - http://blog.sixpoly.com/?p=440 
* sql query vs mongo query  comparsion  http://docs.mongodb.org/manual/reference/sql-comparison/
