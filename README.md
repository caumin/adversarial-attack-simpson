# Adversarial Attack Simpson

Simpson 캐릭터 분류 모델을 대상으로 adversarial patch가 이미지 분류 결과를 어떻게 바꿀 수 있는지 실험한 AI security 토이 프로젝트입니다.

## Overview

ResNet 기반 Simpson 캐릭터 분류 모델을 만들고, 사전에 생성한 adversarial patch를 이미지의 특정 영역에 합성해 모델 예측 변화를 확인합니다. 프로젝트의 목적은 방어 시스템 구축보다는 adversarial example이 실제 이미지 분류 흐름에서 어떤 식으로 작동하는지 관찰하는 데 있습니다.

## Main Files

- `resnet_simpson.ipynb`: Simpson character dataset 기반 ResNet 분류 모델 학습 및 평가
- `apply_advpatch_on_shirt.ipynb`: 저장된 patch를 이미지의 shirt 영역에 합성하고 원본/패치 적용 후 예측 비교
- `load_model.ipynb`: 저장된 checkpoint를 ResNet 모델에 로드하는 실험 노트북
- `config.yaml`: 모델, 학습률, epoch, early stopping 등 학습 설정
- `adv_patch.pt`: 실험에 사용한 adversarial patch tensor
- `label_encoder.pkl`: Simpson 캐릭터 label encoder
- `sample_bart/`: patch 적용 예시용 Bart Simpson 이미지

## Tech Stack

- Python
- PyTorch / torchvision
- NumPy / Pandas
- scikit-learn
- Jupyter Notebook

## Notes

- 학습 노트북은 Kaggle Simpson character dataset 경로를 기준으로 작성되어 있습니다.
- `apply_advpatch_on_shirt.ipynb`는 `checkpoint.pt`, `adv_patch.pt`, `label_encoder.pkl`이 같은 디렉터리에 있다고 가정합니다.
- 이 프로젝트는 adversarial example 개념을 확인하기 위한 toy project입니다.
