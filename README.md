# 대구 음식점 생존배수

대구 일반음식점이 주변 같은 업태 폐업 점포 k곳보다 얼마나 오래 버텼는지(생존배수)를 보여주는 정적 웹사이트입니다.

- `index.html` : 화면과 계산 코드 전체
- `daegu.json` : 대구 일반음식점 97,575곳 (행정안전부_식품_일반음식점 조회서비스, 2026-10-28 수집)
- `vercel.json` : 데이터 파일 캐시 설정

빌드 과정이 없는 정적 사이트라서 Vercel에서 Framework는 "Other", Build Command는 비워 두면 됩니다.

## 데이터 갱신

`daegu.json`을 새 파일로 바꿔 다시 배포하거나, 사이트에서 최신 CSV·JSON 파일을 직접 올리면 됩니다.

## 네이버 지도 켜기

1. [네이버 클라우드 플랫폼 콘솔](https://console.ncloud.com/maps/application)에서 Maps Application을 등록합니다.
   - API 선택: **Dynamic Map** 체크
   - Web 서비스 URL: Vercel 사이트 주소 (예: `https://daegu-survival-fegw.vercel.app`)
2. 발급된 **Client ID**를 `config.js`의 따옴표 안에 넣고 GitHub에 저장합니다.
3. Vercel이 자동으로 다시 배포하면 네이버 지도로 바뀝니다. 키가 없거나 인증에 실패하면 기본 지도로 표시됩니다.
