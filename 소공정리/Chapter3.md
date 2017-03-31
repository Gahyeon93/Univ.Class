# Chapter 3. Critical Systems
**3.1**  A simple safety-critical system
**3.2**  System dependability
**3.3**  Availability and reliability
**3.4**  Safety
**3.5**  Security
--------------
&nbsp;Critical system은 다음과 같이 세 가지로 분류한다. 경제적, 물리적으로 대미지를 받는 시스템이다. ~~(나누긴 하지만 이외에도 있음)~~
* ***Safety*-critical systems**
  * Failure results in *loss of life*, injury or damage to the environment;
  * *Chemical plant* protection system;
* ***Mission*-critical systems**
  * Failure results in failure of some goal-directed activity;
  * Spacecraft navigation system;
* ***Business*-critical systems**
  * Failure results in high economic losses;
  * Customer accounting system in a bank;


## 3.1 A simple safety-critical system
&nbsp; 책에서는 *인슐린 전달 시스템(Insulin delivery systems)*으로 설명한다.~~(나중에 읽어봐)~~
* ~~Used by diabetics to simulate the function of the pancreas which manufactures insulin, an essential hormone that metabolises blood glucose.~~
* ~~Measures blood glucose (sugar) using a micro-sensor and computes the insulin dose required to metabolise the glucose.~~
## 3.2 System dependability
#### System dependability
&nbsp;가장 중요한 **의존성(dependability).** '*자율운전'* 과 같은 시스템은 얼마나 믿을 수 있는지가 중요하다.
* For critical systems, it is usually the case that the most important system property is the dependability of the system.
&nbsp;크리티컬 시스템에서 가장 중요한 속성이다.
* The dependability of a system reflects the user’s degree of trust in that system. It reflects the extent of degree of trust in that system. It reflects the extent of the user’s confidence that it will operate as users expect and that it will not ‘fail’ in normal use.
&nbsp;시스템에 대한 신뢰도(degree of trust)와 만족도(extent of the confidence)반영.
* Usefulness and trustworthiness are not the same thing. A system does not have to be trusted to be useful.
#### Importance of dependability
* Systems that are not dependable and are unreliable, unsafe or insecure may be **rejected** by their users. 사용자들에게 거부당할 거다.
* The **costs** of system failure may be very **high**. 실패 비용 크다.
* Undependable systems may cause **information loss** with a high consequent **recovery cost**. 회복 비용과 정보 손실이 있을 거다.
#### Development methods for critical systems //개발 방법
* The costs of critical system failure are so high that development methods may be used that are **not cost-effective** for other types of system.

* Examples of development methods
  * Formal methods of software development
  * Static analysis
  * External quality assurance

&nbsp;critical하면 전체적인 개발 소스가 cost-effective하지 않을 수 있다.~~(기업은 cost-effective하긴 하지만).~~
* 스마트폰 : **99% 10만** vs 99.999% 100만
* 자율주행차 : 99% 100만 vs **99.999% 1000만**

와 같은 맥락.
#### Socio-technical critical systems //문제
* **Hardware failure**
  * Hardware fails because of *design* and *manufacturing errors* or because components have reached the end of their natural life. (HDD문제 등.)
* **Software failure**
  * Software fails due to errors in its specification, design or implementation.
* **Operational failure**
  * Human operators make mistakes. Now perhaps the largest single cause of system failures. (인간의 실수 등)


//24:50 p.10 (continue)
#### 인슐린 p.10 그림
p.11 그림 ; 장치는 정말 간단하지만,
32:50 p.12
< Dependability requirements>
* The system shall be available to deliver insulin when required to do so. 시스템은 필요할 때 인슐린을 제공해야한다.
* The system shall perform reliability and deliver the correct amount of insulin to counteract the current level of blood sugar. 시스템은 deliver하고 정확한 값.
* The essential safety requirement is that excessive doses of insulin should never be delivered as this is potentially life threatening. 초과 X. 이 외에도 더 있겠지.


< Dependability>34:22 p.13
* The dependability of a system equates to its trustworthiness.
* A dependable system is a system that is trusted by its users.
* Principal dimensions of dependability are:
  * Availability;시스템은 요청할 때 바로 작동해야함
  * Reliability;(못들음)다시듣기
  * Safety;시스템이 잘못 동작해도 안전해야.
  * Security; 외부 공격에 대한 방어.

35:20  p,14 그림. (위 설명)
40:00 p.15
앞에 네개가 핵심적인 것이고 이외에 네가지 더.
< Other dependability propertie>
* Repairability
  * Reflects the extent to which the system can be repaired in the event of a failure
* Maintainability 유지보수.
  * Reflects the extent to which the system can be adapted to new requirements;
* Survivability
  * Reflects the extent to which the system can deliver services whilst under hostile attack; 공격에 대해 망가져도 최소한의 서비스는 가능해야.
* Error tolerance
  * Reflects the extent to which user input errors can be avoided and tolerated. 이건 .... 외부인의 오픈소스를 보면 return value 중요. 논리적 오류 등 중간중간 다 확인되어야. 그래야 산업적으로 준비된 것.

< Maintainability>p.16 pass
~~47:10 잠깐 시험얘기 : 괄호넣기...p.17에서 예를 들면 "survivavility" 단어쓰기라면 영어설명->답: survivavility~~

< Survivability> 48:25 p.17
* The ability of a system to continue to deliver its services to users in the face of deliberate or accidental attack
* This is an increasingly important attribute for distributed systems whose security can be compromised
* Survivability subsumes the notion of resilience -the ability of a system to continue in operation in spite of component failures

문제가 발생했을 때 사용자에게 어느정도 서비스가 가능한지. 뭐 금융서비스 등.
< Dependability vs performance> 49:50 p.18
의존성을 높여야 한다는 것은 앞에 있는 요소들을 높이는 것. but 그럼 performance는 떨어짐. 에러체크 등은 다 느리지는 것. 동일한 성능을 내기 위해서는 돈을 더 투자해야.
* Untrustworthy systems may be rejected by their users
* System failure costs may be very high
* It is very difficult to tune systems to make them more dependable
* It may be possible to compensate for poor performance
* Untrustworthy systems may cause loss of valuable information

< Dependability costs>p.19
exponentially 증가..
* Dependability costs tend to increase exponentially as increasing levels of dependability are required
* There are two reasons for this
  * The use of more expensive development techniques and hardware that are required to achieve the higher levels of dependability
  * The increased testing and system validation that is required to convince the system client that the required levels of dependability have been achieved

p.20 그림 : y축은 비용.
 critical말고 일반적인 얘기 해보자면...나중에 프로젝트를 맡았을 때, 에러체크하는 시간도 기간에 반드시 고려해야함. 개발 퍼센테이지..
의존성을 높이기 위해서는 어떻게 구현할까? 대표적인 것은 중복설계. 인슐린 경우 센서를 여러개 달아서 평균내기.
중복설계 -> 퍼포먼스 증가. 복잡도는 exponential로 증가할 수도.

< Dependability economics>1:00:10 p.21
ex...멀티쓰레드 버그 잡기 힘든데....->개발자체가 어려워져...
* Because of very high costs of dependability achievement, it may be more cost effective to accept untrustworthy systems and pay for failure costs
* However, this depends on social and political factors. A reputation for products  that can’t be trusted may lose future business
* Depends on system type -for business systems in particular, modest levels of dependability may be adequate


####
## 3.3 Availability and reliability
1:04:30 p.22
주어진 시간 안에. failure-free
ex)smoke free
availability : 시간안에 원하는 결과..?
두개 미세하게 다름. (?다시듣기)
소공과 멀지만 하나 말해주면 -> '정량적'으로 보고를 해야함. 오류가 날 확률이 ~%입니다. 등.
* Reliability
  * The probability of failure-free system operation over a specified time in a given environment for a given purpose
* Availability
  * The probability that a system, at a point in time, will be operational and able to deliver the requested services
* Both of these attributes can be expressed quantitatively
************여기까지 2번째시간.
## 3.4 Safety

## 3.5 Security

-------------
수업관련
1. 시험은 영어로. 답도 영어로. 상식적인 스펠링 오류는 ok. 명사 형용사는 주의.
2. (팀별발표에서 이런 그림 & 영양가있는 정보들 같이 소개..)
©Ian Sommerville 2006Software Engineering, 8th edition. Chapter 3
