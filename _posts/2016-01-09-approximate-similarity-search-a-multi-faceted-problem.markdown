---
title: Approximate similarity search - A multi-faceted problem
layout: post
date: 2016-01-09
tag:
- knn
- ann
blog: true
author: kwangswei
---

## 1. Introduction
- Similarity searching 은 전체 오브젝트 집합 내에서 쿼리로 주어지는 오브젝트와 유사한 오브젝트를 찾는 것이다.
- 쿼리는 크게 두가지 타입이 있다.
  - range queries: query(q)와의 거리(distance)가 사용자가 지정한 임계값(threshold) r 보다 작은 모든 오브젝트를 찾는 방식
  - k-nearest neighbors(k-NN) queries: q 와의 거리 순으로 k개의 오브젝트를 찾는 방식
- 정확한 Similarity search 의 경우 feature space 가 커질수록 (high-dimensional feature space), data 사이즈가 커질수록 성능 저하가 심하다.
- 따라서, quality <-> time 간 trade-off 가 필요하고, 이를 approximate similarity search 라고 한다.

#### 1.1. Why to approximate?
- KNN을 구하기 위해서 정확한 값이 아닌 근사값을 구하는 것에 문제가 없을까? 이론적 근거는 다음과 같다
  - User-perceived similarity 와 distance function 에 따른 feature 간 유사도 간에는 갭(gap) 이 이미 존재한다. 멀티미디어데이터의 경우 특히 그렇다.
  - 사용자 입장에서도 100% 정확한 데이터를 얻기 위해 오래 기다리는 것보다는 조금 덜 정확하더라도, 충분히 좋은 성능의 결과를 빠르게 받아보고 싶어할 수 있다.

---

## 2. A classification schema
- 기존 접근방법들은 아래 기준(좌표축)에 따라 분류할 수 있다.
  - 적용 가능한 데이터 타입에 따라
  - 근사값을 얻는 방법에 따라
  - 결과의 품질 보장 정도에 따라
  - 사용자와의 상호 작용의 정도에 따라

- (kwangswei) 접근 방법을 분석할 때 위의 기준을 염두하며 분석해야 할 듯.

#### 2.1. Data type (WIP)
- VSlp
- VS
- MS

#### 2.2. Approximation type
- CS(changing space)
- RC(reducing comparisons)
  - RCap(aggressive pruning)
  - RCes(early stopping)

#### 2.3. Quality guarantees
- NG(no guarantees)
- DG(deterministic guarantees)
- PG(probabilistic guarantees)
  - PGpar(parametric)
  - PGnpar(non-parametric)

#### 2.4. User interaction
- SA(static approach): Query 단계에서 파라메터 설정을 할 수 없고, approximate structure 가 생성되는 시점에 정해진 파라메터로 한정되는 것. 다양한 파라메터셋을 활용하여 여러 벌을 구성해놓고 사용자가 선택하게 할 수도 있다.
- IA(interactive approach): Query 시에 사용자가 파라메터를 지정할 수 있는 접근 방법.



---

## 3. Some Relevant cases
- (kwangswei) 몇몇 접근방법들을 위의 분류 기준에 따라 분류하고 어떻게 분류하였는지 설명해두었는데 필요한 분은 논문을 직접 찾아보시라~
- 위의 분류 스키마를 활용하면, 특정 접근 방법의 활용 방법을 짐작할 수 있다.
  - generality/efficiency trade-off
    - 예를 들면 Parametric 접근이 non-parametric 보다는 당연히 좋은 품질을 보여줄 수 있겠으나, 덜 범용적일 수 있다.
    - MS의 경우 VS보다 더 범용적이겠지만 성능이 느릴 수 있을테고.
![]({{site.url}}/assets/images/2016-01-09-approximate-similarity-search-a-multi-faceted-problem/table1.png)
---

## 4. Optimal approximate similarity search

TBW
