---
layout: post
category: note
title: Apache Spark 에서 Scala 언어가 성능이 좋다?
tags: 분산 Spark Hadoop
---

모든 경우에서 성능이 뛰어난지 특정 상황에서 한해서 성능이 뛰어난지에 대해 찾아보려 합니다. 직접 검증전에 기술 블로그의 글을 참고하여 성능 측정 방법과 결과를 확인 해보겠습니다.

## 측정 History

- 2018년 12월 28일
  - Apache Spark 학습중에 Python, R 언어로만 사용하는 것도 큰 성능 차이가 나는지에 대한 궁금증으로 출발하였습니다.
  - 기술 블로그 글을 참고하여 성능 뿐만이 아닌 언어별 특징도 파악하고 있습니다.

## 사용 가능한 언어

Apache Spark 2.4.0 버전에 따른 호환 언어 목록

|지원 언어|미지원 언어|
|---|---|
|Java 8+|Java 7|
|Python 2.7+ / 3.4+|Python 2.6|
|R 3.1+|N/A|
|Scala 2.11|Scala 2.10|

## 측정 환경

저는 4대의 Raspberry PI 3B+ 를 기준으로 측정해보고자 합니다.

이유는?
장시간 테스트에도 큰 비용없이 테스트가 가능하기에 선택했습니다. 그리고 제가 모르는 측정 결과에 대해 어떠한 부분에서 병목 현상이 있었는지 등을 확인하기에도 좋을 것 같다는 생각이 들었습니다.

## 참고한 내용

- https://spark.apache.org/docs/latest/
- https://www.kdnuggets.com/2018/05/apache-spark-python-scala.html
- http://bcho.tistory.com/1031?category=563141
