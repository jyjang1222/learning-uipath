# Reframework

## 정보 사이트
- https://youtu.be/JPZ7a3lS2Io - config파일 assets시트 사용법
- https://youtu.be/FTiFUD2u5TE - reframework의 대략적인 개요

## 기억사항
- 오케스트레이터 폴더에 맞게 프로세스를 실행해야 정상작동한다.
- 하단의 파란 바 에서 프로세스 폴더 선택 가능
- 예) jy.jang@sictglobal.com's WorkSpace Shared, 운영, 테스트

## ReFramework란
- 개발자가 프로세스를 설계할 때 도움을 줄 수 있는 템플릿을 말한다.

## ReFramework의 기능
- 실패한 트랜잭션을 재시도할 수 있으며 프로그램을 다시 초기화하고 사람의 개입 없이 그에 따라 예외를 처리하는 기능이 있다.
- 각 State마다 Log Message 액티비티가 사용되어 어떤 상황이 일어나는지 세부 내용을 알려주어 디버깅에 용이하다.
- Dispatcher, Performer라 불리는 실행 모델을 적용할 수 있는데 일반적으로 Performer를 구현하는데 ReFramework를 사용한다.

## 트랜잭션 기반 프로세스의 특징
- 트랜잭션 기반 처리 : 반복 처리 방식과 유사하지만 반복처리 방식과 다르게 처리과정 중에 문제가 발생해도 처리과정들이 서로 독립적으로 처리되기 때문에 전체 처리과정에 영향을 주지 않는다.

## ReFramework 템플릿 단계
1. Initialization State
- 이 상태는 프로세스 설정에 필요한 데이터를 초기화하고 프로세스를 실행시키는데 필요한 사항들이 준비가 되었는지 확인하는 단계이다.
- 설정에 필요한 데이터는 보통 폴더내의 Config.xlsx 파일에서 읽어오고 그 데이터들을 State 간에 사용되는 Dictionary에 저장한다. (워크플로를 직접 수정할 필요가 없어지므로 유지보수에 용이해짐)

2. Get Transaction Data State
- 처리할 다음 트랜잭션 데이터를 가져오는 단계이다. 

3. Process Transaction State
- 앞의 단계 에서 받아온 트랜잭션 데이터를 처리하는 단계이다.

4. End Process State
- 프로세스 종료 단계

## 예외(Exception)의 종류
- 비즈니스 예외 : 프로세스 설계 상에서 발생할 수 있는 에러이다.
- 애플리케이션 예외 : 창이 팅긴다거나 하는 환경적인 요인으로 인해 발생하는 에러이다.

## Dispatcher
- 처리할 데이터를 가져와 이를 큐에 추가하는 부분이다.
- 하나 이상의 데이터 소스로 부터 데이터를 추출하여 큐Item을 만들고 오케스트레이터의 큐에 트랜잭션Item을 넣기 위하여 사용된다.

## Performer
- 큐에서 데이터를 가져와 이를 처리하는 프로세스를 실행하는 부분이다.
- 오케스트레이터 큐로부터 트랜잭션Item을 가져와 이를 처리하는 프로세스이다.