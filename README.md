# l2h
1. Просмотрите историю коммитов в своём проекте и выберите три случайных коммита. Просмотрите изменения, которые были в них сделаны.
```
albert@albert-All-Series:~/Documents/l2h/spring-6-rest-mvc-example$ git log --oneline
9cd423c (HEAD -> main, origin/main, origin/HEAD) Merge pull request #1 from Fostix/gitlesson
3113345 resolved conflictfg
a9a5189 Initial commit
60f8216 Add Sort Parameter
9cef865 Refactor Spring Data JPA Repositories
2bf3dad Create Page Request Object
2c6bf14 Add Paging Parameters
821a823 Complete Search Functionality
1f87cb1 Complete Implementation
c774a97 update by id add validated annotation
c3e8013 Corrected method patch beer by id forget return values
98e11fa commented import mysql properties
a58c6f9 Corrected datetime variables
8697b1c Find By Name with Spring Data JPA
22388ae Refactor Service with Conditional Logic
d0576db Update Service to Accept Query Parameter
6ebe9a9 Capture Query Parameters with Spring MVC
8187dea List Beers Spring MVC Test
7aa9364 added docker-compose file
8fb7edc Fix Integration Tests
b1db4b9 Hibernate Create and Update Timestamp
c185776 Save CSV Data to Database
eb737af Added name column row and implemented CSV Parse Service with test
3024f0f Mapping with OpenCSV
f0c1ef7 Beer CSV POJO
1c5dc68 add csv file with more data
7e7e997 BeerRepositoryTest -> testSaveBeer and BootstrapDataTest -> run both fail results
2f17ed7 Add Database Column
2e6a645 add comment information flyway migration script configuration
cbae502 Flyway Dependencies
d856c76 Schema Script Generation
9e07213 Hikari Datasource Pool production statements example
61b044c Hikari Datasource Pool
ef14d0d JPA Updates for MySQL
fca8c8e #validate in product spring.jpa.hibernate.ddl-auto=update were problem here
d0b366f Console Logging of SQL Statements
825f4cf Spring Boot MySQL Profile
3c7d8f5 Adding MySQL Dependencies
20ba9cb scripts mysql-init
4c1f639 bootstrap test added
c51b1f8 java.lang.AssertionError: JSON path "$.length()" Expected: is <2>      but: was <6> Expected :is <2> Actual   :<6>
c1f6cd5 JPA Validation Error Message
39a212b JPA Validation Error Handler
d013727 Controller Testing with JPA
e7bd7b9 Database Constraint Validation
abf2ee1 Merge remote-tracking branch 'origin/main'
ba4908b JPA Validation
7dfb26d Customer and Beer services JPA implement patch by id
d0cf996 Customer and Beer services JPA implement patch by id and start data constraint validation
48cb96b Custom Error Body
c2d2b30 Custom Validation Handler
5472c9b Controller Binding Validation
d58c442 added dependency java bean validation maven dependency
025bb08 added customer implement the same function how in beer and tests both!
dab0081 added JPA Delete by Id Not Found
d4b9930 added JPA Delete Beer by Id
5cefe20 added Update Beer Not Found
0e95b70 added JPA Update Beer by Id Operation
0680ff2 added testing for expected exception was error cause in handlePost add path with id but not need it!
11e6e3b added controller integration test
f17576f added mappers for compile need pres maven Lifecycle -> clean and compile!
4af0a5c pom added dependencies and set configuration
4d2ab3a added Boot JPA Test Splice
37337c7 added Data JPA Repositories
34cdd2e hibernate UUID id generator
b6264b7 added entities
26866ee added dependencies spring-boot-starter-data-jpa and h2
0eff2fd rename dto
fbcd7f3 using java optional
972c160 using response status annotation for default errors
e949d5c controller advice for handle dry. customer and beer were the same method with handleNotFoundException
7d5e6ee added readme file
5417ceb add test exception for customer
aee69b7 using exception handler
5d9ef50 write exception and test for it
f99bce4 customer create tests and itself components too!!!
06e2877 dry problem solved
a42abe2 dry refactoring but have problems
5110b12 test patch beer
7ac0e69 test delete beer by id
e25060f test update beer
0e11b1a test create beer
bd1ab06 create json using jackson
322b7af test list beers
b08be36 implement patch. update only set parameters
98395d2 problem were in query not in code!!
a71c9c5 don't want pull and don't want set lastUpdatedDate
7d05d91 set header on http response. show location
eddc626 path parameters get by id
6cfc0ba http get work
78063dd delombock
ea41fca Lombok logging
41a30d3 Auto generate constructor lombok
83bd9bb lombok itself generate methods use build annotation for make code cleaner
4093ac9 created project
```
```
git diff dab0081
git diff d58c442
git diff 48cb96b
```
- Там много изменений

2. Верните эти изменения командой git revert последовательно, чтобы в итоге получилось тоже три коммита.
```
albert@albert-All-Series:~/Documents/l2h/spring-6-rest-mvc-example$ git revert dab0081
Auto-merging src/main/java/learn/springframework/spring6restmvc/controller/BeerController.java
Auto-merging src/main/java/learn/springframework/spring6restmvc/services/BeerService.java
Auto-merging src/main/java/learn/springframework/spring6restmvc/services/BeerServiceImpl.java
Auto-merging src/main/java/learn/springframework/spring6restmvc/services/BeerServiceJPA.java
Auto-merging src/test/java/learn/springframework/spring6restmvc/controller/BeerControllerIT.java
Auto-merging src/test/java/learn/springframework/spring6restmvc/controller/BeerControllerTest.java
[main d0d683e] Revert "added JPA Delete by Id Not Found"
 6 files changed, 6 insertions(+), 22 deletions(-)
```
```
albert@albert-All-Series:~/Documents/l2h/spring-6-rest-mvc-example$ git revert d58c442
Auto-merging pom.xml
[main b3f06b0] Revert "added dependency java bean validation maven dependency"
 1 file changed, 4 deletions(-)
```
```
albert@albert-All-Series:~/Documents/l2h/spring-6-rest-mvc-example$ git revert 48cb96b
Auto-merging src/main/java/learn/springframework/spring6restmvc/controller/CustomerErrorController.java
Auto-merging src/test/java/learn/springframework/spring6restmvc/controller/BeerControllerTest.java
CONFLICT (content): Merge conflict in src/test/java/learn/springframework/spring6restmvc/controller/BeerControllerTest.java
error: could not revert 48cb96b... Custom Error Body
hint: After resolving the conflicts, mark them with
hint: "git add/rm <pathspec>", then run
hint: "git revert --continue".
hint: You can instead skip this commit with "git revert --skip".
hint: To abort and get back to the state before "git revert",
hint: run "git revert --abort".
```
- Resolved the conflict
```
albert@albert-All-Series:~/Documents/l2h/spring-6-rest-mvc-example$ git add .
albert@albert-All-Series:~/Documents/l2h/spring-6-rest-mvc-example$ git revert --continue 
[main 09f22f5] Revert "Custom Error Body"
 2 files changed, 3 insertions(+), 17 deletions(-)
```
- new three commits
```
albert@albert-All-Series:~/Documents/l2h/spring-6-rest-mvc-example$ git log
commit 30f2bb94e2684d25f20290483b866cba9081392e (HEAD -> main)
Author: albert <accretindiskthat@gmail.com>
Date:   Sat Mar 25 11:42:22 2023 +0500

    Revert "Custom Error Body"
    
    This reverts commit 48cb96b48040003d826f256069454d8863799d77.

commit 4c042dae17a5c629a6c95e3c7aa58f1f9a205a8a
Author: albert <accretindiskthat@gmail.com>
Date:   Sat Mar 25 11:35:17 2023 +0500

    Revert "added dependency java bean validation maven dependency"
    
    This reverts commit d58c4427aa0e864a32beed9a37dd0c4bde5e8267.

commit 53ba1e0119177439213479709c6a8d0d66e9d4c4
Author: albert <accretindiskthat@gmail.com>
Date:   Sat Mar 25 11:34:41 2023 +0500

    Revert "added JPA Delete by Id Not Found"
    
    This reverts commit dab00812cdc4f5cbb1f8bae4e4b5bb86ecd48b60.
```

3. Попробуйте отменить эти три коммита:
* последний — командами git reset --soft и git restore;
```
git reset --soft 30f2bb94e2684d25f20290483b866cba9081392e
albert@albert-All-Series:~/Documents/l2h/spring-6-rest-mvc-example$ git status
On branch main
Your branch and 'origin/main' have diverged,
and have 3 and 49 different commits each, respectively.
  (use "git pull" to merge the remote branch into yours)

nothing to commit, working tree clean
```
- Ну так последний комит, ничего и не должно было произойти :)

* предпоследний — командой git reset --mixed и git restore;
```
albert@albert-All-Series:~/Documents/l2h/spring-6-rest-mvc-example$ git reset --mixed 4c042dae17a5c629a6c95e3c7aa58f1f9a205a8a
Unstaged changes after reset:
M	src/main/java/learn/springframework/spring6restmvc/controller/CustomerErrorController.java
M	src/test/java/learn/springframework/spring6restmvc/controller/BeerControllerTest.java
albert@albert-All-Series:~/Documents/l2h/spring-6-rest-mvc-example$ git restore src/main/java/learn/springframework/spring6restmvc/controller/CustomerErrorController.java
albert@albert-All-Series:~/Documents/l2h/spring-6-rest-mvc-example$ git status
On branch main
Your branch and 'origin/main' have diverged,
and have 2 and 49 different commits each, respectively.
  (use "git pull" to merge the remote branch into yours)

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
	modified:   src/test/java/learn/springframework/spring6restmvc/controller/BeerControllerTest.java

no changes added to commit (use "git add" and/or "git commit -a")
albert@albert-All-Series:~/Documents/l2h/spring-6-rest-mvc-example$ git restore src/test/java/learn/springframework/spring6restmvc/controller/BeerControllerTest.java
albert@albert-All-Series:~/Documents/l2h/spring-6-rest-mvc-example$ git status
On branch main
Your branch and 'origin/main' have diverged,
and have 2 and 49 different commits each, respectively.
  (use "git pull" to merge the remote branch into yours)

nothing to commit, working tree clean
```
* первый — командой git reset --hard.
```
albert@albert-All-Series:~/Documents/l2h/spring-6-rest-mvc-example$ git reset --hard 53ba1e0119177439213479709c6a8d0d66e9d4c4
HEAD is now at 53ba1e0 Revert "added JPA Delete by Id Not Found"
albert@albert-All-Series:~/Documents/l2h/spring-6-rest-mvc-example$ git status
On branch main
Your branch and 'origin/main' have diverged,
and have 1 and 49 different commits each, respectively.
  (use "git pull" to merge the remote branch into yours)

nothing to commit, working tree clean
albert@albert-All-Series:~/Documents/l2h/spring-6-rest-mvc-example$ git log
commit 53ba1e0119177439213479709c6a8d0d66e9d4c4 (HEAD -> main)
Author: albert <accretindiskthat@gmail.com>
Date:   Sat Mar 25 15:55:56 2023 +0500

    Revert "added JPA Delete by Id Not Found"
    
    This reverts commit dab00812cdc4f5cbb1f8bae4e4b5bb86ecd48b60.

commit 48cb96b48040003d826f256069454d8863799d77
Author: Albert <accretiondiskthat@gmail.com>
Date:   Sun Mar 12 20:10:35 2023 +0500

    Custom Error Body
```

