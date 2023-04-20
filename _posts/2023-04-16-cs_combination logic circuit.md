---
title: "[컴퓨터구조] 전자회로 조합 논리 정리(간단히)"
last_modified_at: 2023-04-16T16:20:02-05:00
toc: true
toc_sticky: true
toc_label: "목차"
categories:
  - cs

tags:
  - cs
---


## 조합 논리회로(Combination logic circuit)

임의의 시점에서 출력이 그 시점의 입력 값에 의해서만 결정되는 논리회로. 메모리가 존재하지 않음.
종류)  
NOT, OR, AND, XOR, NOR, NAD, 반가산기, 전가산기, 디코더, 인코더, 멀티플렉서, 디멀티플렉서


## 반가산기(Half Adder)

두 개의 2진수 한 자리를 덧셈해 합(sum)과 캐리(carry)를 산출하기 위한 조합 논리회로.
1비트만 계산하고 캐리에 대한 입력을 받지 않아 최하위 비트에서만 사용 가능하다.

## 전가산기(Full Adder)

반 가산기 + carry. 

## 디코더

8진 표현은 각기 다른 여덟가지 값을 가져다가 3비트로 인코딩한다. 반면, 3:8 디코더는 8진 숫자를 단일 비트의 집합으로 되돌려준다.

디코더는 Minterm Generator라고도 불리는데, 즉, 최소항 생성기이다. n개의 입력이 디코더로 들어가면 2^n 개의 입력이 출력으로 나온다. 

- 3 to 8 디코더의 진리표

![__1](https://user-images.githubusercontent.com/63995044/232320204-f8dc38a6-2db9-4916-bbde-be08c3341767.png)

- 3 to 8 디코더의 회로도

![Untitled](https://user-images.githubusercontent.com/63995044/232321618-9b5d733d-5a18-4797-9e7f-3f31c19be3ac.png)

## 인코더

디코더의 반대 개념으로, 2^n개의 입력이 주어지면 출력은 n개로 나온다.

## 디멀티플렉서

디코더를 사용해 디멀티플렉서(demultiplexer)를 만들 수 있다. 혹은, 디먹스(demux)라고 한다. 디먹스는 입력을 몇 가지 출력 중 한 곳으로 전달한다. 즉, 한 개의 입력선을 받아들여 n개의 선택선의 조합에 의해 2^n개의 출력선 중에서 하나를 선택하여 출력하는 회로이며, 데이터 분배기라고 불린다. 

예를 들어 1 to 4 디멀티플렉서의 경우, 1개의 입력을 가지고 4개의 출력물이 있는데 S1과 S2에 의해 그 중 하나만 선택해 출력하는 회로이다. 

## 멀티플렉서(or 실렉터)

멀티플렉서(multiplexer)는 먹스(mux)라고도 부른다. 

디멀티플렉서와 반대인데, 디먹스는 “1개의 입력선이” S1, S0 선택자에 의해 4개의 출력선 중 하나를 선택해 출력하지만, 4 to 1 먹스는 “4개의 입력선” 중 S1, S0 선택자에 의해 1개를 선택하여 그 중 한 개를 출력한다.