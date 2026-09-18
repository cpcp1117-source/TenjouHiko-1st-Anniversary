# TenjouHiko 1st Anniversary

以單一 HTML 呈現三段故事與三首鋼琴印象曲的周年祝賀網站。

## Project Goal

讓收件人在同一個網頁中依序閱讀「相遇、相識、相處」，並在每章故事結束後自行播放對應曲目。網站採靜態檔案設計，可部署至 GitHub Pages，不需要後端、資料庫或安裝套件。

## MVP Status

目前是 **MVP 0 — Planning Baseline**：

- 已定義 MVP 階段與驗證門檻。
- 已固定三首音訊與九張故事圖片的預留檔名。
- 音訊不納入本階段版本控制，避免在未確認前上傳。
- 尚未建立正式 `index.html`。

詳細規劃請見 [docs/MVP_PLAN.md](docs/MVP_PLAN.md)；內容與素材對照請見 [docs/CONTENT_AND_ASSET_PLAN.md](docs/CONTENT_AND_ASSET_PLAN.md)。

## Planned Structure

```text
index.html
assets/
  audio/
  images/
    encounter/
    acquaintance/
    accompany/
docs/
```

## Privacy Boundary

- AI 不需要讀取、播放或分析 WAV／MP3。
- 音訊由使用者在本機自行放入 `assets/audio/`。
- 正式發布前必須由使用者確認是否將音訊提交至公開 Repository。
- GitHub Pages 是公開靜態網站；取得網址的人技術上可能下載網站素材。

## Current Decisions

- Delivery: Single HTML with inline CSS and minimal JavaScript.
- Audio: MP3 optional, WAV required fallback.
- Playback: User initiated; no autoplay.
- Visual direction: Aurora night sky with translucent letter panels.
- Hosting target: GitHub Pages.

