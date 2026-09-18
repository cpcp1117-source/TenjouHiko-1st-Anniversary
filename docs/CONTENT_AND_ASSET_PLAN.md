# Content And Asset Plan

## Narrative Structure

### Prelude

- Purpose：說明這是一份由三段故事與三首印象曲構成的周年祝賀。
- Required fields：網站主標題、對方稱呼、周年日期、簡短獻詞。
- Primary action：開啟這封信。

### Chapter 01 — 相遇 Encounter

- Story focus：初次相遇、陽光開朗的性格、甜美溫柔的聲音、期待下一次相遇。
- Emotional movement：好奇 → 吸引 → 溫暖。
- Listening transition：邀請收件人聽見「初遇被寫成旋律」的樣子。

### Chapter 02 — 相識 Acquaintance

- Story focus：推特互動、YT 直播、話題與交談、慢慢認識彼此。
- Emotional movement：互動 → 累積 → 喜悅。
- Listening transition：邀請收件人聽見那些一點一滴被收藏的片刻。

### Chapter 03 — 相處 Accompany

- Story focus：溫柔與關懷、堅強背後也需要陪伴、默默支持每段日常與周年。
- Emotional movement：理解 → 守候 → 安定。
- Listening transition：邀請收件人聽見一句不打擾的「我會在這裡」。

### Finale

- Purpose：將情緒收束成祝福，不要求對方回應。
- Content：感謝相遇、珍惜認識的過程、祝福往後日子、三首曲目回顧。

## Audio Contract

| Chapter | Preferred Optional File | Required Fallback File |
|---|---|---|
| 相遇 Encounter | `assets/audio/track-01.mp3` | `assets/audio/track-01.wav` |
| 相識 Acquaintance | `assets/audio/track-02.mp3` | `assets/audio/track-02.wav` |
| 相處 Accompany | `assets/audio/track-03.mp3` | `assets/audio/track-03.wav` |

音訊標題與檔名分離；未來可更改畫面上的曲名，不需要重新命名檔案。

## Image Contract

### 相遇 Encounter

| File | Story Role | Draft Alt Text Direction |
|---|---|---|
| `assets/images/encounter/scene-01.png` | 初見主視覺 | 光芒照亮初次相遇的景象 |
| `assets/images/encounter/scene-02.png` | 性格與聲音留下印象 | 柔和光線與琴鍵交織的景象 |
| `assets/images/encounter/scene-03.png` | 期待再次相遇 | 極光延伸向遠方的道路 |

### 相識 Acquaintance

| File | Story Role | Draft Alt Text Direction |
|---|---|---|
| `assets/images/acquaintance/scene-01.png` | 最初的社群互動 | 兩道訊息般的光點在夜空相遇 |
| `assets/images/acquaintance/scene-02.png` | YT 直播與交談 | 夜晚螢幕映照溫暖陪伴的景象 |
| `assets/images/acquaintance/scene-03.png` | 慢慢認識 | 星點逐漸連成一條溫柔軌跡 |

### 相處 Accompany

| File | Story Role | Draft Alt Text Direction |
|---|---|---|
| `assets/images/accompany/scene-01.png` | 日常的溫柔 | 安靜日常中亮著柔光的房間 |
| `assets/images/accompany/scene-02.png` | 堅強背後的疲憊 | 雨夜窗邊被月光包圍的身影 |
| `assets/images/accompany/scene-03.png` | 始終在這裡 | 兩道身影與遠方不熄的燈火 |

## Image Requirements

- Format：PNG required；未來可以另加 WebP 作為優先來源。
- Color space：sRGB。
- Main image target：1600 × 900 px。
- Detail image target：長邊 1400–1600 px。
- Target file size：每張約 500 KB–2 MB。
- Loading：`loading="lazy"` 與 `decoding="async"`。
- Accessibility：正式替代文字必須描述畫面與其故事作用，不能只寫「故事圖片」。

## Missing Asset Behavior

- 圖片不存在：保留章節色彩與文字，不顯示破圖圖示。
- MP3 不存在：改用 WAV。
- WAV 與 MP3 都不存在：播放器顯示「曲目將在完成後放入」。
- 任一素材缺少：不得阻止讀者進入下一章。

## Open Content Fields

- 網站正式名稱。
- 對方顯示名稱或暱稱。
- 一周年日期。
- 三首正式曲名。
- 封面獻詞。
- Finale 最終祝賀詞。
- 九張正式圖片的完整替代文字。

