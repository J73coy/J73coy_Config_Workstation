# 워크스테이션 초기 설정

새 PC에서 Claude Code·Codex 사용자 설정을 한 번 받아 쓰는 파일. 동기화가 아니라 초기값이다.

| 파일 | 적용 위치 | 방식 |
|---|---|---|
| `claude/settings.json` | `~/.claude/settings.json` | 덮어씀(기존 파일은 `.bak-<시각>`) |
| `claude/CLAUDE.md` | `~/.claude/CLAUDE.md` | 덮어씀 |
| `codex/AGENTS.md` | `~/.codex/AGENTS.md` | 덮어씀 |
| `codex/config.toml` | `~/.codex/config.toml` | 키 단위 병합(앱이 만든 항목 보존) |

## 자리표시자
- `{{WORK_ROOT}}`: 작업 루트(Windows 경로)
- `{{WORK_ROOT_SLASH}}`: 같은 경로를 `/`로 쓴 것

적용하는 쪽이 그 PC의 작업 루트로 바꾼다. 다른 `{{…}}`가 남으면 적용하지 않는다.

## 넣지 않는 것
인증 파일·토큰·비밀, 계정 이름·메일 주소·절대 경로, Codex 앱이 관리하는 키(`notify`, `marketplaces`, `plugins`, `mcp_servers`, `windows`), 저장소별 신뢰 항목, 메모리·문서.

## 받는 쪽
설치 USB의 JCSetups 설정 탭 **설정 적용**이 이 저장소 main 브랜치 zip을 받아 검사한 뒤 적용한다. 받지 못하면 USB에 든 사본을 쓰고, USB 사본이 다르면 검사를 통과한 새 내용으로 바꾼다.

`settings.json`에는 명령을 실행하는 훅을 넣을 수 있으므로, 이 저장소에 푸시할 수 있는 계정은 2단계 인증으로 지킨다.

## 갱신
원본 PC에서 `tools\export.ps1 -Root <작업 루트>` → `git diff` 확인 → 커밋·푸시. 스크립트는 허용 목록의 키만 꺼내고, 경로·메일 주소·계정 이름·알 수 없는 자리표시자가 있으면 파일을 바꾸지 않는다. `-CheckOnly`는 검사만 한다.
