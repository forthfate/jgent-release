# Jgent

Warcraft III JASS/vJass 유즈맵 개발을 위한 Windows AI 코딩 에이전트입니다. 자연어로 작업을 요청하면 프로젝트의 소스, Git, JASS 검증 도구와 개발 지식을 필요한 범위에서 활용해 작업을 돕습니다.

## 복잡한 유즈맵 개발을 위한 에이전트

Jgent는 단순히 JASS 코드를 생성하는 도구가 아닙니다. 기존 유즈맵의 여러 JASS/vJass 소스, 라이브러리 의존성, 초기화 흐름, 오브젝트 rawcode, 맵 아카이브와 컴파일 오류를 함께 분석해 수정과 검증까지 연결합니다.

- 여러 파일로 나뉜 JASS/vJass 소스와 조립 목록을 분석합니다. Jgent 프로젝트에서는 이 조립 목록을 보통 `imports.j`로 관리합니다.
- JassHelper와 PJASS를 이용해 실제 컴파일 경로를 검증합니다.
- library, initializer, module, 호출 흐름과 의존성 문제를 조사합니다.
- 기본 유닛·능력 rawcode를 검색하고, 필요한 경우 MPQ 맵 데이터를 검사합니다.
- Git diff, 작업공간 체크포인트, 프로젝트 규칙과 설계 기록을 관리합니다.

실제 게임 플레이, 멀티플레이 desync, World Editor GUI 저장과 밸런스 판단은 제작자가 최종 확인합니다.

## 역할 기반 작업과 로컬 대시보드

Jgent는 요청을 조율·조사·설계·구현·검증 역할로 나누어 처리합니다. 조사 단계는 소스와 진단을 읽어 근거를 수집하고, 구현 단계는 필요한 파일만 수정한 뒤 검증합니다. 역할별로 사용할 모델도 선택할 수 있습니다.

`/dashboard`를 실행하면 로컬 브라우저에서 요청과 세션 상태, 모델별 토큰 사용량, 추정 비용, 성공·실패 상태를 확인할 수 있습니다. 대시보드는 외부에 공개되지 않는 로컬 loopback 주소에서만 실행됩니다.

## 다운로드 및 실행

1. [최신 릴리스](../../releases/latest)에서 `Jgent-win-x64.zip`을 다운로드합니다.
2. 압축을 풀기 전에 `SHA256SUM.txt`로 ZIP 파일의 무결성을 확인합니다.
3. 원하는 위치에 압축을 푼 뒤 `Jgent.exe`를 실행합니다.

처음 사용하는 작업공간에서는 `/init`을 입력해 World Editor 경로와 프로젝트 환경을 점검하고 설정하세요. 이후에는 자연어로 작업을 요청하거나 `/help`에서 명령어를 확인할 수 있습니다.

Jgent를 자주 사용한다면 압축을 푼 폴더를 Windows 사용자 환경 변수 `Path`에 추가해 보세요. 새 터미널을 열면 어느 위치에서나 `Jgent` 명령으로 실행할 수 있습니다.

## 문의

버그 제보나 기능 제안은 [GitHub Issues](../../issues)에 남겨 주세요.

## 라이선스 및 고지

Jgent는 독점 소프트웨어입니다. 비상업적인 개인 및 내부 조직의 Warcraft III 맵 개발에 사용할 수 있으며, 상업적 사용은 사전 서면 허가가 필요합니다. 재배포 등 제한 사항을 포함한 전체 이용 조건은 [LICENSE](LICENSE)에서 확인하세요.

Warcraft III는 Blizzard Entertainment, Inc.의 상표입니다. Jgent는 Blizzard Entertainment와 제휴하거나 승인을 받은 도구가 아닙니다.

이 저장소는 Jgent 실행 파일을 배포하기 위한 공간입니다. 소스 코드, 내부 문서, 인프라, 구성 정보, 자격 증명, 개발 도구는 포함하지 않습니다. 외부 구성 요소와 데이터에 관한 안내는 [THIRD-PARTY-NOTICES.txt](THIRD-PARTY-NOTICES.txt)와 [DATA-NOTICE.txt](DATA-NOTICE.txt)에서 확인할 수 있습니다.
