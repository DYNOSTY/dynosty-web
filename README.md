> **통합 안내:** 현재 개발은 [DYNOSTY/dynosty](https://github.com/DYNOSTY/dynosty)에서 진행합니다.
> 아래 내용은 이전 4개 레포 구성의 기록입니다. 최신 구조와 역할은 통합 레포 README를 확인해 주세요.

# DYNOSTY Web — 게임 화면

DYNOSTY는 웹 브라우저에서 즐기는 3D 생존·도시 경영 게임입니다.
이 레포는 **플레이어가 보고 조작하는 화면**을 담당합니다.

> 현재는 개발 계획을 정리한 단계입니다. 아래 기능은 앞으로 구현합니다.

## 맡은 일

- 공룡·건물·도시를 3D로 보여줍니다.
- 카메라 이동과 건설·발주·배급 화면을 만듭니다.
- 플레이어의 조작을 게임 계산에 전달하고, 결과를 화면에 보여줍니다.

## 사용할 기술

| 기술 | 쉽게 말하면 |
| --- | --- |
| Babylon.js | 브라우저에 3D 세상을 그리는 도구 |
| React | 버튼·메뉴·관리 화면을 만드는 도구 |
| TypeScript | 게임 코드를 작성하는 언어 |
| Web Worker | 화면과 별도로 게임 계산을 돌리는 브라우저 기능 |

## 다른 레포와의 연결

```text
플레이어의 조작 → Web → Core에서 계산 → Web에 결과 표시
                    ↕ 저장·불러오기
                   API
```

- [Core](https://github.com/DYNOSTY/dynosty-core)의 게임 규칙을 가져와 플레이어 PC에서 실행합니다.
- [API](https://github.com/DYNOSTY/dynosty-api)에 로그인과 온라인 저장·불러오기를 요청합니다.
- [Infra](https://github.com/DYNOSTY/dynosty-infra)는 웹 배포와 서버 운영 설정을 관리합니다.

처음에는 **3D 도시와 카메라 → 미션 1 → 저장·불러오기** 순서로 연결합니다.
