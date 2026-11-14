# 제3자 구성 요소와 라이선스 고지

띄움(Ddium) 자체는 [Apache License 2.0](LICENSE)입니다(Copyright 2026 Dawnilove). 아래는 이 앱에 들어 있거나 참고한 외부 자료입니다. 이 앱은 실행할 때 따로 내려받는 패키지가 없습니다.

## plc-mcp (Apache License 2.0)
- 출처: 공개 저장소 `plc-mcp`(BlackBuddle/plc-mcp), Apache License 2.0. 라이선스 전문: [licenses/Apache-2.0-plc-mcp.txt](licenses/Apache-2.0-plc-mcp.txt)
- **이 앱에 옮겨 쓴 것**: 미쓰비시 Q 시리즈 CPU 의 프로그램 파일(`MAIN.QPG`) 형식 조사 결과와 쓰기 순서. 실제 Q03UDV 에서 확인된 규칙만 TypeScript 로 새로 옮겨 구현했습니다(원본은 Rust·Python).
  - `src/project/qpg-codec.ts` — `MAIN.QPG` 인코더·디코더 (원본: `research/qpg_codec.py`, `docs/research/qpg-format.md`)
  - `src/link/ftp.ts` — Q03UDV 내장 FTP 서버용 능동 모드 클라이언트 (원본: `src/ftp.rs`)
  - `src/link/program-write.ts` — STOP · DELE · STOR · pm-write · 되읽기 비교 · RUN 순서 (원본: `src/filewrite.rs`)
  - 명령어 사전 분류와 엔진 명령어(WAND·WOR·WXOR·BCD·BIN·CML·FF, 32비트 명령, MEP·MEF)의 형태와 스텝 수 근거 (원본: `docs/research/instruction-coverage.md`)
- **변경한 점**: 언어를 옮겼고, 이 앱의 안전 규칙(승인 창, 쓰기 전 백업, 승인 중 PLC 파일 변경 확인, 백업 복구)과 시험을 새로 더했습니다. 원본 코드를 그대로 복사한 것은 없습니다.
- 시험용 실기 파일(`tests/fixtures/qpg`)은 원본 저장소의 자료이며 설치 파일에는 들어가지 않습니다.

## Electron / Chromium (MIT 및 각 구성 요소 라이선스)
- 앱의 실행 환경입니다. 설치 폴더의 `LICENSE.electron.txt` 와 `LICENSES.chromium.html` 에 전체 고지가 들어 있습니다.

## 글꼴 (SIL Open Font License 1.1)
- **IBM Plex Sans KR** — Copyright 2018 IBM Corp.
- **JetBrains Mono** — Copyright 2020 The JetBrains Mono Project Authors
- 라이선스 전문은 앱 폴더의 `fonts/LICENSE-ibm-plex-sans-kr.txt`, `fonts/LICENSE-jetbrains-mono.txt` 입니다.

## 상표
- MELSEC, GX Works2, MELSOFT 는 미쓰비시전기의 상표입니다. 이 앱은 미쓰비시전기와 관련이 없으며, 호환 형식(CSV·`.gxw`)과 통신 규격을 설명하려고 이름만 씁니다.
- Windows 는 Microsoft 의 상표입니다.
