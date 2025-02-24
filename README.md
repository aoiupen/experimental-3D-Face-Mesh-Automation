## 업데이트 중
# experimental-3D-Face-Mesh-Automation
- 3D 얼굴 메시 생성 자동화 및 PyQt 기반 UX로 작업 효율성 향상

# Facescape 2020 논문 참조

**목적** : 1장의 얼굴 이미지만으로 3D 얼굴 모델 생성  
**과정**
- **3D 스캐닝** : 360도 사진 촬영
- **3D 메쉬 구축** : 멀티뷰 이미지 → 3D 모델 → 정규화된 토폴로지
- **학습 및 리깅** : PCA 모델 학습 → 블렌드 쉐이프 기반 리깅

# 3D Mesh 데이터 구축

- **툴** : Reality Capture, Wrap 3D, Blender (+API)  
- **언어** : Python (PyQt 프레임워크)

## 1. 멀티뷰 이미지 → 3D 모델 (Reality Capture)

- **입력** : 여러 각도의 얼굴 사진

![3D Scanning](./src/Reality_Capture_01.png)

- **과정**
    - **Align Images** : 3D Point Cloud 생성
    ![3D Scanning](./src/Reality_Capture_02.png)
    - **Set Reconstruction Region** : Reconstruction 영역 지정 (AI 활용 자동화 예정)
    - **Dense Reconstruction** : 3D 메쉬 생성
    - **Texturing** : 텍스처 생성
- **출력** : 3D 메쉬와 텍스처

## 2. 3D 모델 → 정규화된 토폴로지 (Wrap 3D, Blender)

- **입력** : Reality Capture에서 생성한 3D 모델
- **과정**
    - **Optical Flow Wrapping**
        - **1차** : 기본 얼굴 템플릿 → 중립 표정
        - **2차 (표정마다 시행)** : 중립 표정 → 10여 가지 표정
    - **결과 크로스 체크** : Wrap 3D, Blender에서 확인

# 자동화 (Python, API 활용)

- **목표** : Reality Capture, Wrap 3D, Blender의 반복 작업 자동화, 배치화
- **효과** : 작업 속도 및 정확도 향상, 팀 생산성 향상, 프로젝트 기간 70% 단축

## 1. 멀티뷰 이미지 → 3D 모델 (Reality Capture)

### 1) Work flow 관점

![Before Automation](./src/Summary_01.png)
![After Automation](./src/Summary_02.png)

### 2) Work load 관점

![Before Automation](./src/Summary_03.png)
![After Automation](./src/Summary_04.png)

### 3) Idle time 관점

![Before Automation](./src/Summary_05.png)
![After Automation](./src/Summary_06.png)
