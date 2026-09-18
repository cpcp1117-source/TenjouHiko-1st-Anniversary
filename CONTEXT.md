# Project Context

## Background

本專案是一份一周年祝賀網站，以三首鋼琴印象曲對應三段關係故事。網站的核心不是展示技術，而是安排「先讀故事、再聽音樂」的情緒節奏。

## Audience

- Primary recipient: 祝賀對象。
- Publisher: 專案擁有者。
- Expected device: 手機優先，同時支援桌面瀏覽器。

## Experience Principles

1. Story First：先閱讀，再讓音樂成為故事的回音。
2. Gentle Control：不自動播放、不強迫聽完整首、不製造操作壓力。
3. One Continuous Letter：雖然有三章，仍維持單一 HTML 的完整旅程。
4. Privacy by Default：製作階段不需要提供或分析音訊。
5. Progressive Enhancement：MP3 缺少時使用 WAV；圖片缺少時仍可閱讀故事。

## Interaction Model

- Experience type：單一 HTML、五幕式閱讀舞台。
- Visible state：同一時間只顯示序章、單一故事章節或終章。
- Navigation：讀者在章末主動點擊後才切換，不允許捲動直接看見下一章。
- Transition：以短暫遮罩與下一章標題完成換幕；reduced motion 下立即切換。
- Back navigation：每章保留返回前一幕的控制項。
- Audio：不得因換幕而自動播放。

## Visual Reference Direction

整體參考 VTuber 天上被子的公開美術識別，僅擷取高階設計語言，不直接複製角色立繪：

- 極光所誕生的被子精靈意象。
- 白色、冰藍、柔和粉彩與淡金點綴。
- 帶有柔軟、包覆感的圓角信箋卡片。
- 雪、夜空與安靜光線的氛圍。

## Canonical Chapter Names

| Order | Chinese | English | Theme |
|---|---|---|---|
| 01 | 相遇 | Encounter | 初見的悸動與溫暖 |
| 02 | 相識 | Acquaintance | 慢慢認識的喜悅 |
| 03 | 相處 | Accompany | 溫柔、支持與陪伴 |

## Constraints

- 只有一個正式 HTML 入口。
- CSS 與 JavaScript 內嵌於 `index.html`。
- 音訊與圖片維持外部靜態檔案。
- 不使用後端、資料庫、分析追蹤、Cookie 或第三方播放器。
- 不依賴 npm 或前端框架。
- 必須能部署到 GitHub Pages。

## Known Risks

- 三個 WAV 合計約 88.1 MB，行動網路首次播放可能需要等待。
- 九張 PNG 若未壓縮，可能顯著拖慢頁面。
- GitHub Pages 無原生私人分享或密碼保護。
- 音訊與圖片一旦發布至公開網站，可能被下載。
