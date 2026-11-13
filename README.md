# WISHME

이미지를 바탕으로 만든 모바일 간식 쇼핑 프로토타입입니다.
상품 및 영양정보는 예시이며 실제 주문이나 결제는 진행되지 않습니다.

## 로컬 실행

```sh
python3 -m http.server 8000 --directory dist
```

브라우저에서 http://localhost:8000 을 엽니다.

## Cloudflare Workers 배포

Cloudflare에서 GitHub 저장소 `tldutk-bot/wishme1`을 연결하고 다음을 설정합니다.

- 프로젝트 이름: `wishme1`
- 프로덕션 브랜치: `main`
- 루트 디렉터리: 저장소 루트
- 빌드 명령: 비워둠 (정적 파일이 이미 `dist`에 있음)
- 배포 명령: `npx wrangler deploy`

`wrangler.jsonc`에서 `dist`를 정적 파일 디렉터리로 지정합니다.
Cloudflare 프로젝트 이름을 변경하면 설정 파일의 `name`도 함께 변경하세요.

터미널에서 직접 배포할 때는 다음 명령을 실행하고 Cloudflare에 로그인합니다.

```sh
npx wrangler deploy
```

## 기능

간식 검색, 메뉴 필터, 식이조건 변경, 상품 상세, 찜, 장바구니, 주문 체험을 제공합니다.
찜과 선택한 식이조건, 장바구니는 브라우저의 로컬 저장소에 저장됩니다.
