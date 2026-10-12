# painter-4.1--zzap-bootleg-

---

### ⚠️ IMPORTANT NOTICE / DISCLAIMER

**Original Author:** MoxoPixel (SPT 4.0 port: Jayoh99)
**Original Repository:** Painter
**Original Link:** https://github.com/emilanderss0n/Painter
**License:** MIT

1. **Reflection & Take-Downs:** I deeply reflect on the ECOT incident. As an AI-assisted "vibe coder," I will immediately delete files if the original authors ask.
2. **No Re-Distribution:** These ported builds are unverified, temporary fixes. Please do NOT re-upload or share them anywhere else.
3. **Do Not Pester Original Authors:** Never report bugs or pester original modders regarding issues from my unofficial ports.
4. **Full Credit & Respect:** I will always credit original creators on GitHub and prioritize their decisions above all else.
5. **Support Original Creators:** Instead of using my ports, please visit the original authors' Forge pages to leave kind words or tips.

---

## 변경 이력

릴리즈 노트: [RELEASE_NOTES.md](RELEASE_NOTES.md)

- 2026-10-12 23:29 — 아이템 무게·패널티를 원래대로 되돌림. 개인 설정으로 모든 Painter 아이템(176개)의 무게가 0, 소음기·라이트·총열·탄창의 인체공학 감소와 방탄복 3종·백패널의 이동속도/마우스/인체공학 패널티가 0으로 덮여 있었음 → 무게는 이전 포팅판(SPT 4.0) 값으로, 패널티는 0 덮어쓰기를 지워서 원본 아이템 값이 그대로 적용되게 함.
- 2026-10-12 23:01 — 퀘스트 'The Dark Knight'(배트맨 피규어 찾아서 넘기기)를 깰 수 없던 문제 고침. 퀘스트가 원작의 옛 배트맨 피규어 ID(`672e2e75d78…`)를 찾는데, 이 버전에는 그 아이템이 없고 새 ID(`6a29afb0…`)로 다시 만든 배트맨 피규어만 있어서 주워도 인정이 안 됐음 → 퀘스트가 새 피규어를 보도록 바꿈. 참고: 원작 데이터 그대로 쓰는 다른 포팅판에서 '모스코븀' 완료 시 램 폭주로 멈추는 버그는 없는 아이템을 보상으로 주려다 서버가 무한 반복에 빠지는 것인데, 이 버전은 그 보상이 'Mystery Box of Loot'로 바뀌어 있어서 해당 없음(모든 퀘스트 보상·조건 아이템 존재 확인).
- 2026-10-12 22:46 — 상인 판매 목록에서 빠져 있던 아이템 2개(PMAG GEN M3 탄창 Tape White, VPO-101 개머리판 Black)를 다시 넣음. 가격·신뢰도 레벨만 남고 물건이 없어서 두 아이템을 구할 방법이 없던 문제 고침. 구매 제한은 다른 아이템처럼 12개.
- 2026-10-12 22:46 — 도색 방탄복 11종(CGPC3 TQS, AVS, JPC, APC, SOHPC 등)의 기본 프리셋에 플레이트를 넣음. 기본 프리셋에 소프트 아머만 있어서, 고물상(Fence)이 이 방탄복을 매물로 만들 때 `Unable to randomise armor items ... slot as it cannot be found` 경고가 계속 나던 문제 고침. 넣은 플레이트는 원본 방탄복의 기본 플레이트와 같음.
- 2026-10-12 22:46 — 저장소를 실제로 쓰고 있는 SPT 4.1.5용 로컬 버전으로 맞춤. 소스는 설치된 `Painter.dll`을 되살린 것(동작 동일), 빌드는 .NET 10 + SPT 4.1 설치 폴더의 DLL 참조. 예전 저장소에는 퀘스트 정의가 비어 있었고 퀘스트 해금 상점 연결이 반대로 되어 있었음.

## 소개

Painter 상인을 추가하는 서버 모드입니다. 도색된 총기 부품·방탄복·총기 프리셋과 전용 퀘스트 12개가 들어 있습니다.

- 대상: SPT 4.1.5 이상 (4.1.6에서 사용 중)
- 필요 모드: WTT-ServerCommonLib 3.0.x
- 설치 위치: `SPT_Runtime\user\mods\Painter`

이 저장소에는 `bundles` 폴더(약 1.1GB, 3D 모델)가 없습니다. 원본 모드의 `bundles` 폴더를 같이 넣어야 합니다.

## 빌드

```
dotnet build -c Release -p:SptPath="E:\SPT 4.1\SPT_Runtime"
```

`SptPath`는 SPT 설치 폴더(`SPTarkov.Server.Core.dll`이 있는 곳)입니다. WTT-ServerCommonLib은 `user\mods\WTT-ServerCommonLib`에서 참조합니다.
