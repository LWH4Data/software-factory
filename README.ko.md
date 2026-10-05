# Software Factory 한국어 사용 안내

[영문 정본 README](README.md)와 영문 `SKILL.md`·상황 예시·종료 reference가 운영 규칙의 정본이다. 이 문서는 한국어 사용자를 위한 안내이며 모델 본문에 한국어 규칙을 중복하지 않는다. 플러그인 이름은 `software-factory`, marketplace 이름은 `software-factory-local`, 패키지 버전은 `0.1.4`다.

이 파일들은 영문 정본을 포함하는 0.1.4 릴리스 소스다. 게시·설치본 갱신에는 대상·행위별 승인과 검수가 필요하다. 소스의 존재만으로 배포·설치·실제 skill 로딩·runtime 검증을 입증하지 않는다. 영문 정본을 사용해도 출력은 사용자 명시 언어 선호, 없으면 대화 언어를 따른다. 한국어 대화의 보고는 한국어로 작성한다.

## 요청과 역할

시작 요청 예: `$software-factory로 이번 프로젝트의 개발 목표와 명세를 함께 작성해 주세요.` 재개나 완료보고는 승인된 명세와 최신 checkpoint를 먼저 확인하도록 요청한다.

두 흐름은 사용자+main 명세 합의와, 승인 명세에 따른 worker 개발 → 구현자와 다른 reviewer 검수 → main 완료보고다. main은 협의·배정·결정 기록·증거 대조·통합판정·보고를 맡고 제품 코드·테스트·설정은 worker가 작성한다. 추가 에이전트는 main만 생성하고 worker/reviewer는 재위임하거나 새 chat으로 대체하지 않는다. 필요한 다중 에이전트 도구가 없으면 해당 작업만 대기하고 한계를 보고한다. 원본 프로젝트 AGENTS/override를 우선한다.

첫 명세에서 목표·범위·제외·완료기준·쓰기권한·기록위치·명세 버전과 cycle 범위·완료 경계를 합의한다. 종료일은 필요할 때 정하며 고정 주기를 가정하지 않는다. 승인 작업·필수 검증·독립 검수·main의 증거 대조와 보고를 완료 경계로 삼을 수 있다. 필수 검증 누락이나 프로젝트의 승인된 재시도·중단 경계 도달은 통과가 아니며 해당 작업을 대기·미확인으로 보고한다. 필요한 재시도·중단 정책이 미정이면 재시도 전에 결정을 요청한다. 공통 지침은 재시도 숫자를 정하지 않는다.

프로젝트별 제품 repo 밖 absolute record root의 실제 위치를 확인한다. 기록 root 미합의 초안은 대화에 남기며 repo 내부 운영 파일을 임의 생성하지 않는다. 설치 캐시는 기록 root가 아니다.

설치만으로 개발이 승인되거나 시작되지 않는다. 외부 쓰기·티켓·Git commit/push/PR/merge·설치는 대상·행위별 권한을 확인한다. 자동 merge·상주 서비스·보고 자동 강제는 없으며 보고나 개선 채택도 후속 구현·설치·자동 메모리 활성화 승인이 아니다.

해당 상황에서만 [운영 예시 정본](software-factory/skills/software-factory/references/operating-examples.md)을 읽는다. 기존 recipe의 현재 적합성·검증 수단은 [준비](software-factory/skills/software-factory/references/operating-examples.md#preparation), 최신 정본 연결은 [현재 상태](software-factory/skills/software-factory/references/operating-examples.md#current-state), 필요한 근거 조회·경로/필드 오류는 [범위 제한 근거](software-factory/skills/software-factory/references/operating-examples.md#bounded-evidence), 단계 실패·검증 미완료 재개는 [실패와 재개](software-factory/skills/software-factory/references/operating-examples.md#failure-and-resumption)를 참조한다. 매 task의 전체 감사나 새 인덱스 파일을 요구하지 않는다. 실제 경로·명령·증거 캡처 방법은 프로젝트 기록에 둔다.

## 종료보고

개발 종료 후 cycle 최종 완료보고 전에만 [종료 점검 정본](software-factory/skills/software-factory/references/cycle-close-checklist.md)을 읽는다. 컨텍스트·반복 역할의 하네스 편입 후보·의존성·파일 인덱싱·코드 품질 다섯 항목을 기존 독립 검수·main 대조에 통합한다. 시작·일반 개발·개별 task 완료마다 반복하지 않고 항목별 에이전트 수를 고정하지 않는다.

보고는 최신 고정 대상·spec version·변경 파일·근거·검증 한계·미해결 질문·다음 행동·소유권과 세 짧은 소절을 포함한다.

- **필요·불편:** task·근거·영향·선택 개선안을 main이 정리하고 사용자가 채택한다. 실제 blocker만 관련 작업을 대기시킨다.
- **하네스:** 실제 사용한 지침·skill·도구·검증·환경의 관찰된 누락·충돌·실패·갱신 필요를 보고한다.
- **에이전트 메모리 관리:** context 선별·반복 투입·요약 손실·오래된 결정·인계·checkpoint·재개 문제를 보고한다. 보고 때문에 개인 메모리·인증파일을 읽거나 자동 메모리 상태·사용·효과를 추정하지 않는다.

관찰·추론·미확인을 구분하며 근거 없으면 `미확인`, 관찰된 문제가 없으면 `없음(미관찰)`로 쓴다. 문서 작성·validator 결과를 실제 제품 테스트나 skill 자동 로딩·운영 준수의 증거로 바꾸지 않는다. 구현자는 자기 완료를 최종 승인할 수 없다.

## 설치 안내

공개 배포 소스는 [LWH4Data/software-factory](https://github.com/LWH4Data/software-factory)다. Codex CLI가 필요하며 공개 안내 자체는 설치·출처 전환 승인이 아니다. 먼저 기존 출처를 조회한다.

```sh
codex plugin marketplace list --json
codex plugin list --json
```

`software-factory-local`이 이미 있으면 `marketplaceSource`·출처를 확인하고 사용자 승인을 받는다. 승인 전 등록·설치를 실행하지 않고 같은 이름의 marketplace를 자동 덮어쓰기하거나 `remove`로 삭제하지 않는다. 출처가 불명확하면 전환을 대기한다.

이름 충돌이 없거나 출처 확인과 전환 승인이 끝나면 배포된 검수 완료 커밋으로 등록·설치한다. `<reviewed-commit-sha>`는 전달받은 검수 완료 커밋의 전체 SHA로 바꾼다. README 자체의 커밋 해시를 삽입하지 않는다.

```sh
codex plugin marketplace add LWH4Data/software-factory --ref <reviewed-commit-sha>
codex plugin add software-factory@software-factory-local --json
```

설치 후 조회 명령으로 출처·버전·installed/enabled 값을 확인한다. 설치 확인과 실제 대화에서의 skill 로딩·운영 준수 확인을 구분한다. 인증정보는 배포 소스에 저장하지 않는다. 명령의 공식 근거는 [Package your plugin](https://developers.openai.com/plugins/build/plugins), [Developer commands](https://learn.chatgpt.com/docs/developer-commands)다.

## 개발 검증과 배포 범위

기본 개발 검증 의존성은 `requirements-dev.txt`의 `PyYAML==6.0.3`이며 Python 3.8 이상을 사용한다. 일반 플러그인 설치의 runtime 요구와 별개다. 배포·제품 repo 밖의 분리된 venv를 사용하고 전역 Python·PATH·pip 설정·설치본은 변경하지 않는다.

배포 root에서 아래 placeholder를 실제 경로로 대체한다. `<skill-creator-dir>`는 독자 자신의 Codex 설치에 포함된 Skill Creator 폴더다. 이 패키지는 `quick_validate.py`를 배포하지 않는다.

```powershell
python -B -X utf8 -m venv "<external-validation-dir>/.venv"
$validationPython = "<external-validation-dir>/.venv/Scripts/python.exe"
& $validationPython -B -X utf8 -m pip --isolated install --no-cache-dir --only-binary=:all: -r ./requirements-dev.txt
& $validationPython -B -X utf8 "<skill-creator-dir>/scripts/quick_validate.py" ./software-factory/skills/software-factory
```

POSIX에서는 venv의 `bin/python`으로 같은 requirements와 `-B -X utf8` 인수를 사용한다. `-B`는 bytecode 쓰기를 억제하고 `-X utf8`은 UTF-8 모드를 선택한다. 실제 interpreter·dependency import 출처, 고정 source hash, validator exit/output을 남긴다. 자동 validator는 frontmatter·이름·미완성 scaffold placeholder를 확인할 뿐, 번역 의미·판단 품질·제품 동작·실제 skill 선택/로딩·GUI/접근성 검증을 대신하지 않는다. source freeze 후 검증하고 독립 의미 검수와 main 대조를 거친다.

배포 소스의 Git 허용목록은 10파일이다. 전체 목록은 [영문 README](README.md#distribution-source-isolation)와 `.gitignore`에 맞춘다. 강제 추가·이미 추적 중인 파일은 ignore 규칙과 별도로 확인한다. `.gitattributes`는 패키지 5파일의 줄바꿈 변환을 막아 검수 바이트를 보존한다. venv·원문 보존본·설치 로그·records/work·개발 산출물·env/auth·비밀값·임시파일은 배포에서 제외한다. 배포 소스 자체는 Git 쓰기·게시·설치 갱신을 승인하지 않는다.
