# 서울시 재건축/재개발 현황 조회 웹페이지

서울시의 재건축 및 재개발 사업 현황을 사용자 친화적인 인터페이스로 조회할 수 있는 웹페이지입니다.  
자치구, 법정동, 사업구분, 진행단계, 상태 등 다양한 조건으로 검색할 수 있으며, 검색 결과는 테이블로 제공됩니다.  
또한, 현재 페이지에 표시된 데이터를 **엑셀 파일로 다운로드**할 수 있고, **페이지네이션 기능**도 포함되어 있습니다.

## 🖥️ 주요 기능

### 🔎 필터링 검색
- 검색어 입력 (정비구역명칭, 자치구, 법정동, 조합명)
- 자치구, 법정동, 사업구분, 진행단계, 상태 선택 필터

### 📄 결과 테이블
- 총 10개의 열: 정비구역명칭, 자치구, 법정동, 조합명, 사업구분, 진행단계, 상태, 위치도, 조감도, 배치도
- 위치도/조감도/배치도는 링크로 "보기" 버튼 제공

### 📑 페이지네이션
- 한 번에 최대 5개 페이지 버튼 표시
- `«`, `»` 버튼을 통한 페이지 그룹 전환
- 현재 페이지 강조 표시

### 📥 엑셀 다운로드
- 현재 페이지에 표시된 데이터만 다운로드
- `.xlsx` 형식으로 저장

## 📁 파일 구조

```
.
├── index.html              # 메인 웹페이지
├── data/
│   └── redevelopment.json  # 서울시 재개발 JSON 데이터 (DESCRIPTION / DATA 구조)
└── README.md               # 소개 문서 (본 파일)
```

## 📦 기술 스택

- **HTML5**, **JavaScript (Vanilla JS)**
- **Bootstrap 5**: 반응형 UI 및 스타일링
- **SheetJS (xlsx.js)**: 엑셀 다운로드 기능 구현
  - CDN: `https://cdnjs.cloudflare.com/ajax/libs/xlsx/0.18.5/xlsx.full.min.js`

## 🗂️ JSON 데이터 구조 예시 (`redevelopment.json`)

```json
{
  "DESCRIPTION": { ... },
  "DATA": [
    {
      "mtnc_area_nm": "한남3구역",
      "cgg_nm": "용산구",
      "stdg_nm": "한남동",
      "asct_nm": "한남3구역 주택재개발조합",
      "biz_se": "재개발",
      "prgrs_seq": "조합설립인가",
      "stts": "진행중",
      "pstn_map": "/servlet/image/assc/2023/02/XXXX.jpg",
      "arlv": "/servlet/image/arlv/2023/02/YYYY.jpg",
      "btch_map": "/servlet/image/btch/2023/02/ZZZZ.jpg"
    }
  ]
}
```

## 🚀 실행 방법

1. `index.html`을 웹 브라우저에서 실행
2. `data/redevelopment.json` 파일을 동일 디렉터리에 준비
3. 필터를 조정하여 원하는 항목을 검색하거나, 엑셀 다운로드 버튼을 클릭

---

개선 요청이나 버그 제보는 자유롭게 남겨주세요.
