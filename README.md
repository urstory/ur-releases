# ur 시리즈 내려받기

ur 시리즈 앱의 **설치 파일**을 내려받는 곳입니다. 소스 코드는 여기에 없습니다.
앱 소개와 설치 안내는 [urai.kr/apps](https://urai.kr/apps)에서 보는 것이 가장 편합니다.

| 앱 | 하는 일 | 소개 페이지 |
|---|---|---|
| UrBuddy (유어 버디) | 앱·파일·명령을 한 칸에서 찾아 실행하는 런처 | https://urai.kr/apps/urbuddy |
| UrZip (유어집) | 결과가 보이는 압축 도구(ZIP·7z 만들기, RAR·ALZ·EGG 풀기) | https://urai.kr/apps/urzip |
| UrSnap (유어 스냅) | 화면을 캡처하고 바로 설명을 더하는 캡처·편집 도구 | https://urai.kr/apps/ursnap |

- 세 앱 모두 **개인·회사 구분 없이 무료**입니다.
- Windows 10·11(64비트)용과 macOS 14 이상(Apple Silicon·Intel 공용)용이 있습니다. 두 OS의 최신 판 번호는 다를 수 있습니다(예: UrZip은 Windows 0.1.1, macOS 0.1.2).
- 1.0 전의 판은 **미리보기 판**으로 표시합니다.

## 받기

[Releases](https://github.com/urstory/ur-releases/releases)에서 앱과 버전을 고릅니다. Release 이름은 `<앱> <버전>`, 태그는 `<앱 ID>-v<버전>`(예: `ursnap-v0.6.3`)입니다.

| 파일 | 설명 |
|---|---|
| `<앱>-<버전>-win-x64-setup.exe` | 설치 프로그램(대부분은 이것을 받으면 됩니다) |
| `<앱>-<버전>-win-x64-portable.zip` | 설치 없이 압축을 풀어 바로 쓰는 판 |
| `<앱>-<버전>-mac-universal.dmg` | macOS용(열고 앱을 Applications로 끌어 놓기) |
| `SHA256SUMS.txt` | 파일마다 SHA-256 값 |

## 받은 파일 확인하기

PowerShell에서 해시를 재어 `SHA256SUMS.txt`의 값과 같은지 봅니다.

```powershell
Get-FileHash .\UrSnap-0.6.3-win-x64-setup.exe -Algorithm SHA256
```

macOS에서는 터미널에서:

```sh
shasum -a 256 ~/Downloads/UrSnap-0.6.3-mac-universal.dmg
```

## 처음 실행할 때 경고가 뜨면

아직 코드 서명 전이라 Windows가 "Windows의 PC 보호" 같은 경고를 띄울 수 있습니다.
넘기는 방법은 [설치 도움말](https://urai.kr/apps/install-help)에 그림과 함께 있습니다.

macOS에서는 처음 열 때 "열 수 없음" 창이 뜹니다. [완료]를 누른 뒤 시스템 설정 › 개인정보 보호 및 보안 맨 아래 [그래도 열기]를 누르세요([설치 도움말 — Mac](https://urai.kr/apps/install-help#mac)).

## 앱이 읽는 최신 판 정보

`releases/v1/<앱 ID>.json`에 앱마다 판 목록(버전·날짜·파일 이름·크기·SHA-256·받는 주소)이 있고, `releases/v1/index.json`에 세 앱의 최신 판이 모여 있습니다. 소개 페이지와 앱의 새 버전 알림이 이 파일을 읽습니다.

---

© 2026 Carami, ToTo, Esther
