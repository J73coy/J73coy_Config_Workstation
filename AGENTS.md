# Config_Workstation
- 무엇: 새 PC가 한 번 받아 쓰는 Claude Code·Codex 사용자 설정(공개 저장소). 받는 쪽은 설치 USB 도구(`J73coy_Config_WinMedia`)의 JCSetups **설정 적용**과 `stage-elevated.ps1`. 설명은 `README.md`.
- 실행: 갱신 `powershell -NoProfile -ExecutionPolicy Bypass -File tools\export.ps1 -Root <작업 루트>`, 검사만 `-CheckOnly`.
- 검사: `tools\export.ps1 -CheckOnly`가 `ok 4 files`. 커밋 전 `git diff`로 바뀐 키를 사용자에게 보여준다.
- 이 저장소만의 규칙: 공개 저장소다. `claude/`·`codex/`는 손으로 고치지 않고 export로 만든다. 파일 목록·자리표시자·검사 규칙을 바꾸면 받는 쪽(`J73coy_Config_WinMedia`의 `src\AppPicker.ps1`, `stage-elevated.ps1`)도 같이 고친다. 커밋·푸시는 사용자가 초기 설정 갱신을 요청할 때만.
