# Adversarial Attack Simpson

## Project Summary

- Simpson 캐릭터 분류 모델 대상 adversarial patch 실험
- ResNet 기반 이미지 분류 흐름에서 patch 적용 전후 예측 변화 확인
- AI security / adversarial example 개념을 이해하기 위한 toy project
- Production defense system이 아니라 실험과 관찰 중심의 프로젝트

## Dataset

- The Simpsons Characters Dataset
- Source: https://www.kaggle.com/datasets/alexattia/the-simpsons-characters-dataset

## What I Built

- Simpson character dataset 기반 분류 모델 학습 노트북
- 저장된 adversarial patch를 이미지 특정 영역에 합성하는 실험 코드
- 원본 이미지와 patch 적용 이미지의 모델 예측 결과 비교 흐름
- 저장된 checkpoint와 label encoder를 다시 불러오는 로드 예제

## Main Files

- `resnet_simpson.ipynb`
  - Simpson character dataset 기반 ResNet 분류 모델 학습
  - train/validation split, augmentation, early stopping, 평가 시각화 포함
- `apply_advpatch_on_shirt.ipynb`
  - `adv_patch.pt` 로드
  - shirt 영역 mask/bbox 계산
  - patch 합성 후 원본/패치 이미지 예측 비교
- `load_model.ipynb`
  - 저장된 checkpoint를 ResNet18 모델에 로드
- `config.yaml`
  - model, batch size, learning rate, epoch, early stopping 설정
- `adv_patch.pt`
  - 실험에 사용한 adversarial patch tensor
- `label_encoder.pkl`
  - Simpson 캐릭터 label encoder
- `sample_bart/`
  - Bart Simpson patch 적용 테스트 이미지

## Tech Stack

- Python
- PyTorch / torchvision
- NumPy / Pandas
- scikit-learn
- Jupyter Notebook

## Notes

- 학습 노트북은 Kaggle Simpson character dataset 경로를 기준으로 작성
- `apply_advpatch_on_shirt.ipynb` 실행 시 `checkpoint.pt`, `adv_patch.pt`, `label_encoder.pkl` 필요
- 실험 목적: adversarial patch가 분류 모델 예측에 주는 영향 관찰
