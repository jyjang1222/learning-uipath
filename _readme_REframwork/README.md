# Reframework

## ReFramework 정보 사이트
- https://youtu.be/FTiFUD2u5TE - ReFramework 이해하기
- https://www.soais.com/reframework-in-uipath/ - 

## 업무 프로세스의 3가지 유형
- 선형처리 : 처리 과정이 한 번만 수행되는 형태.
    - 장단점 : 단순하고 구현하기 쉽지만, 다른 데이터들을 반복적으로 처리해야 하는 경우에는 적합하지 않다.
- 반복처리 : 처리 과정이 여러번 실행되는 형태.
    - 장단점 : 처리과정 중에 문제가 발생할 경우, 처리과정이 멈춰서 전체 처리과정에 영향을 준다.
- 트랜잭션 기반 처리 : 반복 처리 방식과 유사하지만 반복처리 방식과 다르게 처리과정 중에 문제가 발생해도 처리과정들이 서로 독립적으로 처리되기 때문에 전체 처리과정에 영향을 주지 않는다.

## ReFramework란
- 개발자가 프로세스를 설계할 때 도움을 줄 수 있는 템플릿을 말한다.

## ReFramework를 사용하는 이유
- 실패한 트랜잭션을 재시도할 수 있으며 프로그램을 다시 초기화하고 사람의 개입 없이 그에 따라 예외를 처리하는 기능이 있다.

## ReFramework 템플릿 단계
1. Initialization State
- 이 상태는 프로세스 설정에 필요한 데이터를 초기화하고 프로세스를 실행시키는데 필요한 사항들이 준비가 되었는지 확인하는 단계이다.
- 오류(시스템은 예외)가 발생했을 경우는 프로세스 종료(End Process) 상태로 이동하고 초기화(Initialization)에 성공한 경우 흐름은 트랜잭션 데이터 가져오기 상태로 이동한다.

2. Get Transaction Data State
- 처리할 다음 트랜잭션 데이터를 가져오는 단계이다. 
- 처리할 데이터가 없는 경우는 End Process 상태로 이동하고, 그렇지 않으면 Process Transaction으로 이동하여 추가 실행을 진행한다.

3. Process Transaction State
- 앞의 단계 에서 받아온 트랜잭션 데이터를 처리하는 단계이다.
- 처리 결과 

4. End Process State