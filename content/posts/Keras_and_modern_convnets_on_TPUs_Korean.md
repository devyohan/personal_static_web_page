---
author:
  name: "Yohan Park (DevYohan)"
date: 2019-03-26
linktitle: Keras_and_modern_convnets_on_TPUs_Korean
title: TPU 에서 작동하는 Keras 와 현대 convolutional neural network
type:
- post
- posts
weight: 10
series:
- GCP
aliases:
- /blog/keras-and-modern-convnets-on-tpus-korean/
---

## 들어가기 전에
서울 강남구 역삼동 GS 타워에서 열린 Google Developers ML Summit 2019 의 Codelab 시간에 찾아본 문서를 한국어로 다시 정리했습니다.
연습 코드등은 정리하지 않았고, 이론적인 부분을 정리하였습니다.

## 개요
Q. 이것으로 무엇을 배울 수 있나요?
- 빠르게 '직접 만들 모델'을 TPU(Tensor Processing Units) 기반에서 작업할 수 있게 됩니다.
- 

Q. 이 실습을 진행하기 위해 미리 학습해야 할 부분은 무엇이 있나요?
- Python 3 

Q. 실습에 사용하는 TensorFlow 버전은 몇 인가요?
- 1.x 기반으로 진행됩니다. 2.x 이상은 따로 변환이 필요할 것으로 보입니다.

## 모델의 크기를 줄이는 노력들
이 코드랩에서는 Squeezenet 을 소개합니다.

Q. '모델 크기' 는 무엇을 뜻하나요?
- 모델의 파일크기를 뜻합니다.

## 참고문헌
- 정재윤, SQEEZENET(모델 압축), *Jaeyun's Blog(2018년 5월 62일)*, https://jayhey.github.io/deep%20learning/2018/05/26/SqueezeNet/
- https://arxiv.org/abs/1602.07360