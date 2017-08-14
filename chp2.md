# Chapter 2 Preparing Data

## Contents
1. [Data types](#1-data-types)
2. [TOPIC2](#2-topic2)
3. [TOPIC3](#3-topic3)
4. [TOPIC4](#4-topic4)
5. [TOPIC5](#5-topic5)

## 1. Data Types
### Depending on its content
- 질적데이터(범주형데이터)
  - 명목형
  - 순서형

- 양적데이터

_i.e._
1) R에서는 2차원 형태의 배열로 되어 있는 양적데이터만 다룰 수 있으며, 숫자형, 문자형, 논리형으로 데이터의 유형이 있음. 한편 데이터의 구조로는 벡터, 요인, 행렬, 배열, 데이터 프레임, 리스트의 형태로 나누어짐.

### Depending on its shape
1) 벡터형
```r
x=c(1,3,5,-4,10) #Numeric
y=c("one", "two", "three") #String
z=c(TRUE, TRUE, FALSE, FALSE, TRUE) #Logic
```

_c.f._
1) Numeric, String, Logic type can be used together in a single variable, but the type must be unified as follows:
```r
> c(1, "1", TRUE) #Unified as string
[1] "1" "1" "TRUE"

> c(3, TRUE, FALSE)#Unified as numeric
[1] 3 1 0
```

2) Indexing
```r
> x[2]
[1] 3

> x[c(1,3,5)]
[1] 1 5 10

> x[c(TRUE, TRUE, FALSE, FALSE, TRUE)]
[1] 1 3 10
```

2) Level
```r

```
성별, 정도와 같이 문자형이나, 종류가 정해진 데이터를 의미함. factor() 함수를 사용하면, 숫자형, 문자형 데이터를 요인으로 인식하도록 만듦. 특히 정도에 관한 데이터의 경우, 순서를 지정할 수 있음; factor(income, order=TRUE, level=c("Low", "Medium", "High"))의 형태로 하면, Low<Medium<High 즉, 1<2<3이라는 순서로 데이터가 인식됨.

3) 행렬, 배열
행렬은 2차원 배열로서, 구성요소는 모두 동일한 유형으로 맞춰져야함. matrix() 함수를 활용하여 행렬을 생성할 수 있는데, rnames=c("R1", "R2", "R3"), cnames=c("C1", "C2", "C3"), x=matrix(1:9, nrow=3, ncol=3, byrow=TRUE, dimnames=list(rnames, cnames)) 로  x를 행렬로 선언이 가능하며, x[2,3]을 부를경우 6이 나타남. 한편 x[,3]과 같이 3번째 열을 전부 불러올 수도 있음.

4) 데이터프레임

5) 리스트

**Lorem ipsum** Lorem ipsum

* Lorem ipsum
* Lorem ipsum
* Lorem ipsum

_c.f._
1) 
2) 
3)

_i.e._
1) 
2) 
3) 

_e.g._

```c
```

## 2. Topic2
### Lorem ipsum
**Lorem ipsum** Lorem ipsum

* Lorem ipsum
* Lorem ipsum
* Lorem ipsum

_c.f._
1) 
2) 
3)

_i.e._
1) 
2) 
3) 

_e.g._

```c
```

## 3. Topic3
### Lorem ipsum
**Lorem ipsum** Lorem ipsum

* Lorem ipsum
* Lorem ipsum
* Lorem ipsum

_c.f._
1) 
2) 
3)

_i.e._
1) 
2) 
3) 

_e.g._

```c
```

## 4. Topic4
### Lorem ipsum
**Lorem ipsum** Lorem ipsum

* Lorem ipsum
* Lorem ipsum
* Lorem ipsum

_c.f._
1) 
2) 
3)

_i.e._
1) 
2) 
3) 

_e.g._

```c
```

## 5. Topic5
### Lorem ipsum
**Lorem ipsum** Lorem ipsum

* Lorem ipsum
* Lorem ipsum
* Lorem ipsum

_c.f._
1) 
2) 
3)

_i.e._
1) 
2) 
3) 

_e.g._

```c
```
