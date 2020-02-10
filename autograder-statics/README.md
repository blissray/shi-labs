## TEAMLAB Autograder 시계열 데이터 분석 프로젝트
### 개요

TEAMLAB Autograder에는 학생들이 제출한 다양한 코드 데이터들이 쌓이고 있습니다. 그러나 이 데이터에 대한 통계가 제대로 생성되지 않아 여러가지 분석에 어려움을 겪고 있다.  
예를 들면 아래와 같은 사항들에 대해서 파악하고 싶을 것 이다.

- 각 Lab assignment에 대한 평균적으로 몇 번의 제출이 이루어지고 있는가?
- 숙제가 완료되기 전까지 걸리는 시간은 얼마인가?

본 프로젝트에서는 현재 TEAMLAB Autograder에 제출된 숙제 데이터를 분석하여 시각화하는 프로젝트이다. 하나의 숙제를 제품의 공정 과정이라고 볼 때, submission이 시작되면 제품이 제작이 출시되는 것이고, 숙제가 모두 패스되면 숙제가 완료되는 것이라고 볼 수 있다. 이를 고려하여 아래와 같은 이슈들을 해결할 수 있는 데이터를 가공해 보자

### 이슈

- 각 숙제마다 분반들의 평균 제출 횟수는 다른가? 이를 box plot 그래프를 그려서 비교해보자!
- 비교적 어려운 숙제로 받아들여지고 있는 'gowithflow'의 working in progress를 파악하고 싶다. 1시간 단위를 기준으로 WIP를 산출한다고 했을때, 숙제를 처음시작했을 경우 'active'로 모든 함수를 맞췄을 경우 'finish'로 기록한다. 이때 시간당 WIP는 얼마인지를 bar plot 그래프로 표현하여라
단 gowithflow의 함수는 총 9개이다.
- 각 문제당 성공하는 데 까지 걸리는 시간은 평균적으로 얼마나 차이날까? 도수분포표를 사용하여 각 문제당 걸리는 시간을 시각화 하여라
- 학생들은 언제 숙제를 가장 많이낼까? 새벽에 가장 많이 낼까 저녁에 가장 많이 낼까. 이를 알아볼 수 있도록 line graph를 사용하여 시각화 하여라

### 데이터

- 데이터 설명
    1. 학생아이디 리스트
        - 2019년 2학기 수강중인 학생들의 아이디 리스트
        - 각 파일들은 학생들의 분반임
    2. 수강생 DB 정보
        - 데이터베이스에 저장된 학생 아이디 정보와 그 아이디를 관리하기 위한 DB index 정보
    3. 숙제 정보 데이터
        - Lab assignment 리스트 - Lab assignment의 이름이 기재되어 있음

    4. 숙제 데이터 제출 이력 

    - 하나의 숙제 데이터는 여러개의 함수로 구성되며 이는 submission detail 이라는 이름으로 관리됨
    - submssion_list는 한번 제출된 숙제에 대한 데이터로 아래와 같은 항목이 저장됨
        - user_index - 제출한 사용자 정보(DB 저장정보)
        - assignment_name - 숙제명
        - submission_id - submission index
        - submission_time - 제출 시간
    - submission_detail은 하나의 submission에 대한 각 함수의 합격 여부를 저장한 파일
        - index - submission detail의 아이디
        - passed - 함수의 합격여부
        - assignment_detail_id - 해당함수의 저장 번호
        - submission_id - 제출된 숙제의 submission index
- 다운로드 대상 데이터
    - 학생 아이디 리스트
        - [stu_list_2.csv](./data/stu_list_2.csv)
        - [stu_list_3.csv](./data/stu_list_3.csv)
        - [stu_list_1.csv](./data/stu_list_1.csv)

    - 수강생 DB 정보
        - [user_list.csv](./data/user_list.csv)

    - 숙제정보데이터
        - [lab_list.csv](./data/lab_list.csv)

    - 숙제데이터 제출이력
        - [submission_list.csv](./data/submission_list.csv)
        - [submission_detail_list.csv](./data/submission_detail_list.csv)