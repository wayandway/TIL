# 네트워크 보안
## 목차
1. [네트워크 기초](#1-네트워크-기초-⬆️목차)
2. [네트워크 해킹 및 기법](#2-네트워크-해킹-및-기법-⬆️목차)
---
## 1. 네트워크 기초 [⬆️](#목차)
---
## 2. 네트워크 해킹 및 기법 [⬆️](#목차)
### 대표적인 공격 기법 2가지
>**1. 중간자 공격(Man In The Middle attack, MITM)**
<br>네트워크 통신 내용을 도청(*Sniffing*)하거나 조작(*Spoofing*)하는 공격 기법

>> 실습 1. [Cookie Sniffing](waeandway.tistory.com) 
<br> 실습 2. [ARP Spoofing](waeandway.tistory.com)


>**2. DoS/DDoS**
<br>**서비스 거부 공격(*Denial of Service, DoS*)**
<br>시스템을 악의적으로 공격해 원래의 용도로 사용 못하게 한다. 보통 사이트 또는 서비스의 기능을 일시적/영구적으로 방해 및 중단을 초래한다.
>* 시스템 자원 고갈 공격 → CPU, 메모리, 디스크 자원 고갈
>* 네트워크 자원 고갈 공격 → 무의미한 값으로 네트워크 대역폭 고갈
>* 공격자를 찾기 어려운 편
>* Layer에 관계 없이 다양한 공격 기법 존재

>**분산형 서비스 거부 공격(*Distributed Denial of Service*)**
<br>분산 서비스 거부 공격은 여러 대의 공격자를 분산적으로 배치해 동시에 서비스 거부 공격을 한다.

|☑️ex 네트워크 취약 허점|
|:----:|
|ICMP ping Flooding|
|Malformed IP Flooding|
|IP fragmented Flooding|
|SYN Flooding|
|UDP Flooding|
|ACK Flooding|
|Empty connection Flooding|

>>실습 1. [ICMP ping Flooding](waeandway.tistory.com)
<br>실습 2. [SYN Flooding](waeandway.tistory.com)
<br>실습 3. [Slowloris Attack](waeandway.tistory.com)