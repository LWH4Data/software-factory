# Software Factory

사용자와 명세를 합의하고 개발·독립 검수·완료보고를 운영하는 Codex 플러그인이다. 플러그인 이름은 `software-factory`, marketplace 이름은 `software-factory-local`, 패키지 버전은 `0.1.1`이다. 현재 공개(public) 배포 저장소는 [LWH4Data/software-factory](https://github.com/LWH4Data/software-factory)다. 이 로컬 변경의 게시·설치본 갱신은 별도 승인과 검수 후에 수행한다.

## 두 흐름과 역할

1. 사용자와 main이 목표·범위·제외 사항·완료기준·쓰기권한·기록위치·명세 버전·cycle 종료일을 합의한다.
2. 승인된 명세에 따라 worker가 허용 파일을 개발하고, 구현자와 다른 reviewer가 고정 산출물을 검수한다. main은 명세와 증거를 대조해 결과를 보고한다.

main은 협의·배정·결정 기록·통합판정·보고를 맡고 제품 코드·테스트·설정은 worker가 작성한다. 추가 에이전트 생성은 main만 맡으며 worker/reviewer는 재위임하지 않는다. 필요한 다중 에이전트 도구가 없으면 해당 개발·검수 작업을 대기하고 제한을 보고한다. 원본 프로젝트 지침을 우선한다.

설치만으로 개발이 승인되거나 시작되지 않는다. 자동 merge·상주 서비스·보고 자동 강제도 없다. 외부 쓰기·티켓·commit/push·PR/merge·설치는 대상과 행위별 권한을 따로 확인한다.

개발 종료 후 사이클 최종 완료보고 전에만 [사이클 종료 점검](software-factory/skills/software-factory/references/cycle-close-checklist.md)을 읽어 컨텍스트·반복 역할의 하네스 편입 후보·의존성·파일 인덱싱·코드 품질을 기존 독립 검수와 main 대조에 통합한다. 시작·일반 개발·개별 task 완료마다 반복하지 않으며 결과와 최신 고정 대상 식별을 완료보고에 연결한다. 완료 차단 결함과 다음 cycle 개선을 구분하고 운영자가 채택을 결정한다.

## 보고와 기록

완료보고에는 결과·명세 버전·변경 파일·검증 한계·미해결 질문·다음 행동·소유권과 아래 짧은 소절을 포함한다.

- **필요·불편:** task·근거·영향·선택 개선안을 main이 정리하고 사용자가 채택한다. 실제 blocker만 관련 작업을 대기시킨다.
- **하네스:** 실제 사용한 지침·skill·도구·검증·환경의 누락·충돌·실패·갱신 필요를 관찰 근거로 보고한다.
- **에이전트 메모리 관리:** context 선별·반복 투입·요약 손실·오래된 결정·인계·checkpoint 문제를 보고한다. 개인 메모리나 인증정보를 보고 목적으로 읽지 않고 자동 메모리 상태·사용·효과를 추정하지 않는다.

관찰·추론·미확인을 구분한다. 근거가 없으면 `미확인`, 관찰된 문제가 없으면 `없음(미관찰)`으로 기록한다. 보고나 개선 채택은 후속 구현 승인이 아니다.

## 배포 소스 격리

이 저장소의 루트는 제품 저장소와 분리된 플러그인 배포 소스다. Git 대상은 다음 7파일로 한정한다.

```text
.agents/plugins/marketplace.json
software-factory/plugin.json
software-factory/skills/software-factory/SKILL.md
software-factory/skills/software-factory/references/cycle-close-checklist.md
README.md
.gitignore
.gitattributes
```

프로젝트 운영 기록·개발 산출물·비밀값·환경파일·임시파일은 포함하지 않는다. `.gitignore`는 위 파일만 허용하고 `.gitattributes`는 패키지 4파일의 텍스트 줄바꿈 변환을 끈다. 첫 명세에서 프로젝트별 제품 repo 밖의 절대 기록 root를 합의하고 실제 경로가 repo 밖인지 확인한다. 설치 캐시는 기록 root가 아니다.

## 검수된 커밋으로 설치

Codex CLI가 필요하다. 현재 공개 배포 소스를 읽기 위해 private GitHub 저장소 접근 권한을 전제하지 않는다. 공개 안내도 설치·출처 전환 승인을 대신하지 않는다. 인증정보는 배포 소스에 저장하지 않는다.

먼저 기존 출처를 조회한다.

```sh
codex plugin marketplace list --json
codex plugin list --json
```

`software-factory-local`이라는 marketplace가 이미 있으면 `marketplaceSource`와 출처를 확인하고 사용자 승인을 받는다. 승인 전 아래 등록·설치 명령을 실행하지 않는다. 같은 이름의 marketplace를 자동 덮어쓰기하거나 `remove`로 삭제하지 않는다. 출처가 불명확하면 전환을 대기한다.

이름 충돌이 없거나 출처 확인과 전환 승인이 끝난 경우, 배포된 검수 완료 커밋으로 등록·설치한다. 아래 `<reviewed-commit-sha>`는 placeholder이며 전달받은 검수 완료 커밋의 전체 SHA로 바꾼다. 이 README에 자신의 커밋 해시를 삽입하지 않는다.

```sh
codex plugin marketplace add LWH4Data/software-factory --ref <reviewed-commit-sha>
codex plugin add software-factory@software-factory-local --json
```

설치 후 위 조회 명령으로 출처·버전·installed/enabled 값을 확인한다. 설치 확인과 실제 대화에서의 skill 로딩·운영 준수 확인은 구분한다.

호출 예: `$software-factory로 이번 프로젝트의 개발 목표와 명세를 함께 작성해 주세요.` 재개·완료보고도 승인된 명세와 최신 checkpoint를 확인해 요청한다.

명령과 marketplace 형식의 공식 근거: [Package your plugin](https://developers.openai.com/plugins/build/plugins), [Developer commands](https://learn.chatgpt.com/docs/developer-commands).
