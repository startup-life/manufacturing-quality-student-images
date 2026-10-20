# manufacturing-quality-student-images

텀블러 품질관리 실습용 이미지 128장입니다. 수강생이 실습 앱에서 불러 쓰는 사진만 모았습니다.

## 이 사진은 무엇인가

- 생성형 AI로 만든 합성 이미지입니다. 실제 공장이나 실제 제품의 사진이 아닙니다.
- 사진 속 외관 판정은 실습용입니다. 중량, 누수, 출하 승인까지 뜻하지 않습니다.
- 크기는 1024x1024 JPG이고 전체 약 7MB입니다.

## 폴더

| 경로 | 장수 | 용도 |
|---|---:|---|
| `assets/tumbler/reference/` | 64 | 기준 설명용 (`TUM-REF-001` ~ `TUM-REF-064`) |
| `assets/tumbler/practice/` | 64 | 연습용 (`TUM-PRC-001` ~ `TUM-PRC-064`) |
| `MANIFEST.csv` | 1 | 파일별 경로, SHA-256, 바이트 수 |

## 받는 방법

`git clone`으로 받습니다. ZIP으로 받지 않습니다. 사진은 일반 파일이라 Git LFS가 필요 없습니다.

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

`MANIFEST.csv`의 `sha256` 값과 받은 파일의 해시가 같으면 온전한 파일입니다. PowerShell 예시입니다.

```powershell
Get-FileHash manufacturing-quality-student-images\assets\tumbler\reference\TUM-REF-001.jpg -Algorithm SHA256
```

## 이용 범위

이용 조건은 아직 정해지지 않았습니다. 정해지면 이 절과 `LICENSE` 파일을 채웁니다.
그 전에는 수강 실습 목적으로만 사용하고, 다시 배포하지 않습니다.
