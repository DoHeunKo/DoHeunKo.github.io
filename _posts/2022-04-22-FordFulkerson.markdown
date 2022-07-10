---
layout: single 
title:  "Ford Fulkerson Algorithm" 
date:   2022-04-22 09:41:00 +0900  
categories: Data Structur & Algorithm
use_math: true  
comments : true  
categories: 
- Computer Science
- Algorithm Concepts
---  


# Ford Fulkerson Algorithm


1. 네트워크 유량  
2. 포드풀커슨 알고리즘  
3. 코드 모듈별 설명 & 실행결과 (여러가지 네트워크 모양에서 분석)  
4. 성능분석 (DFS,BFS)  
5. 한계 

## 1.Network Flow
> 특정한 지점에서 다른 지점까지 데이터가 얼마나 많이 흐르는지 측정하기위해 네트워크 플로우를 이용하고 유량 네트워크에서 주어진 두 정점 사이의 최대 유량을 찾기 위해 Ford Folkerson Algorithm(FFA)을 이용할 것이다. 하지만 DFS를 이용한 포드풀커슨알고리즘은 특수한 경우 한계점이 있기 때문에 그것을 개선한 에드먼트-카프 알고리즘에 대해 서도 알아보려고 한다.  

코드의 성능측정은 java의 DFS와 BFS를 이용하고, 그래프의 노드 수에 따라 최대유량이 어떻게 달라지는지 확인해 볼 것이다.



### Flow Network  (용여 , 조건, 그래프 설명)
 : 각 모서리 $ e \in E $ 에 음이 아닌 정수 값, 의 용량을 할당하는 함수(c)와 결합된 정점(V)과 모서리(E)가 있는 방향 그래프(G)의 흐름  


<img src="https://cp-algorithms.com/graph/Flow1.png" width="300" height="200">  

<img src="https://cp-algorithms.com/graph/Flow9.png" width="210" height="140">  

* 정점 u에서 v로가는 간선의 용량(capacity)  : $ c(u,v)$

* 정점u에서 v로 실제 흐르는 유량(flow) : $ f(u,v)$  

#### 속성
1. 용량제한  

$ \forall\ (u,v) \in E : f(u,v) \leq c(u,v) $  
2. 유량 대칭  

$ \forall\ (u,v) \in E : f(u,v) = -f(v,u) $  
3. 유량 보존  

$ \forall\ u \in V: u\neq t\Rightarrow \sum _{w\in V}f(u,w)=0  $  

* source : 유량이 시작하는 노드  
* sink : 유량이 도착하는 노드  
> 이 두 정점에서는 유량 보존이 성립하지 않는다. 하지만 다른 정점사이에 유량 보존이 성립하기 때문에 소스에서 나온 유량은 결국 싱크로 들어감  

$ \sum _{(s,u)\in E}f(s,u)=\sum _{(v,t)\in E}f(v,t) $

## 2.Ford Fulkerson Algorithm

 
Ford-Fulkerson( G, s, t)  
1 for each edge(u,v) G.E에 포함  
2 	(u, v) .f =0  
3	while there exists a path p from s to t in the residual network Gf  
4		cf(p)= main{ cf(u,v) : (u,v) is in p}  
5		for each edge (u,v) in p  
6			if( u,v) 는 E에 포함  
7				(u,v).f = (u,v).f + cf(p)  
8			else (v,u).f = (v,u).f – cf(p)  



>입력:   
-테스트 게이스의 첫줄에 정점과 간선의 개수 : N,M  
-이 후 M줄에 각각의 간선과 용량 : u,v,c  
-테스트 케이스의 마지막 줄에 소스와 싱크 : src, snk  
