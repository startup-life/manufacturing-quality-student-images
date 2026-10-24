# manufacturing-quality-student-images

텀블러 외관의 정상·불량을 구분하는 실습용 이미지 128장입니다. 수강생이 Teachable Machine과 사진 판독 실습에 쓸 사진을 모았습니다.

## 이 사진은 무엇인가

- 생성형 AI로 만든 합성 이미지입니다. 실제 공장이나 실제 제품의 사진이 아닙니다.
- 사진 속 외관 판정은 실습용입니다. 중량, 누수, 출하 승인까지 뜻하지 않습니다.
- 크기는 1024x1024 JPG이고 전체 약 7MB입니다.

## 폴더

| 경로 | 장수 | 용도 |
|---|---:|---|
| `assets/dataset/images/` | 128 | 사진 128장 (`TUM-REF-###.jpg`, `TUM-PRC-###.jpg`) |
| `metadata/generation_manifest.csv` | 1 | 사진별 트랙, 용도, 경로, SHA-256 |

**학습 준비용·결과 확인용 사진은 파일 목록의 `split` 열로 구분합니다.**

| `split` | 장수 | 용도 |
|---|---:|---|
| `train` | 64 | 학습 준비용: 기준 설명·학습 사진 선별 (`TUM-REF-001` ~ `TUM-REF-064`) |
| `val` | 64 | 결과 확인용: 학습에 쓰지 않은 사진으로 판독 연습 (`TUM-PRC-001` ~ `TUM-PRC-064`) |

사진은 모두 `assets/dataset/images/`에 있습니다. `train`·`val`이라는 별도 폴더는 없습니다.

`subtype` 열은 비어 있습니다. 사진별 유형과 판단 보류(HOLD) 여부는 학생용 저장소에 넣지 않습니다.

## 실습에서 쓰는 방법

**학습 준비용 사진에서 학습할 사진을 고릅니다. 결과 확인용 사진은 학습이 끝난 뒤 판독 결과를 살펴보는 데 씁니다.**

파일 목록의 `split` 값은 각각 `train`과 `val`입니다.

`train`은 정상·불량 기준을 설명하는 사진 모음입니다.

교재에서는 정상 16장과 불량 40장을 골라 총 56장으로 학습합니다. 판단 보류(HOLD) 8장은 학습에서 제외합니다.

`val` 64장은 학습에 넣지 않고 결과 확인에 씁니다. 두 `split` 모두 정상·불량 사례가 섞여 있으므로 `split` 전체를 한 종류로 분류하지 않습니다.

사진을 나누는 기준과 업로드 순서는 교재에서 확인합니다. 강사가 제공한 ‘텀블러 외관 불량 판정하기’의 사용 방법 1)~4)를 따릅니다.

이 저장소에는 기준용·연습용 사진만 있습니다. 강사용 평가 사진과 정답·매핑 자료는 포함하지 않습니다.

## 받는 방법

`git clone`으로 받습니다. ZIP으로 받지 않습니다.

사진은 일반 파일이라 Git LFS가 필요 없습니다.

### Windows

1. Git for Windows가 설치돼 있는지 PowerShell에서 확인합니다.

```powershell
git --version
```

2. 실습 폴더로 이동해 clone합니다. 폴더 위치는 교재의 안내를 따릅니다.

```powershell
git clone https://github.com/startup-life/manufacturing-quality-student-images.git
```

### macOS

터미널에서 같은 `git clone` 명령을 실행합니다.

## 파일이 온전한지 확인

`metadata/generation_manifest.csv`의 `sha256` 값과 받은 파일의 해시가 같으면 온전한 파일입니다. PowerShell 예시입니다.

```powershell
Get-FileHash manufacturing-quality-student-images\assets\dataset\images\TUM-REF-001.jpg -Algorithm SHA256
```

## 이용 범위

이용 조건은 아직 정해지지 않았습니다. 정해지면 이 절과 `LICENSE` 파일을 채웁니다.

그 전에는 수강 실습 목적으로만 사용하고 다시 배포하지 않습니다.
