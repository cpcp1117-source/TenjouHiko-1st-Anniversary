# MVP Plan

## Objective

以最小但完整的方式驗證：收件人能否在手機與桌面上理解三段故事、自然找到對應播放器，並在 MP3 不存在時使用 WAV 完成播放。

## MVP Success Definition

MVP 成功不以動畫數量或裝飾程度判定，而以以下五件事為準：

1. 60 秒內理解這是一份三章式周年祝賀。
2. 能清楚辨認「相遇、相識、相處」的順序與差異。
3. 每章讀完後能找到且操作對應播放鍵。
4. 只有 WAV 時仍能播放；音訊缺少時有友善提示。
5. 手機閱讀無橫向溢位，文字與控制項不擁擠。

## Scope

### In Scope

- 單一 `index.html`。
- Prelude、三個故事章節與 Finale。
- 內嵌 CSS 與少量原生 JavaScript。
- 三首曲目的共用自訂播放器。
- MP3 optional / WAV fallback。
- 每章三張 PNG 的固定相對路徑。
- 圖片 lazy loading、缺圖 fallback 與替代文字。
- Responsive、keyboard support、reduced motion。
- GitHub Pages 靜態部署。

### Out of Scope

- 帳號、登入、留言、表單與資料庫。
- 音訊分析、波形生成、歌詞同步與自動轉碼。
- 密碼保護與真正的私密分享。
- 複雜頁面轉場、3D、Canvas 或重型動畫套件。
- 自訂網域與付費託管。
- 自動收集訪客行為。

## Delivery Phases

### MVP 0 — Planning Baseline

**Goal**：固定範圍、名稱、素材契約與驗證方式。

**Deliverables**：

- `README.md`
- `CONTEXT.md`
- `AGENTS.md`
- `docs/MVP_PLAN.md`
- `docs/CONTENT_AND_ASSET_PLAN.md`
- 空白素材資料夾與 placeholder 說明

**Exit Criteria**：

- 三章名稱與順序一致。
- 九張圖片、三組 MP3/WAV 路徑固定。
- 隱私與公開發布邊界已記錄。
- 使用者確認可進入 HTML 骨架。

### MVP 1 — Content Skeleton

**Goal**：先驗證內容順序與閱讀節奏，不追求完整視覺。

**Deliverables**：

- 單一 `index.html`。
- 封面、三章、終章與章節導覽。
- 使用現有祝賀文字建立第一版內容。
- 圖片位置使用固定容器；缺圖時顯示章節標示。
- 音訊位置使用不可播放的預留狀態。
- 五幕式 gated navigation；讀者點擊後才揭示下一章。
- 封面與章節間的基礎轉場；reduced motion 提供無動畫切換。

**Validation Questions**：

1. 三章順序是否自然？
2. 每章文字是否過長或過短？
3. 情感是否逐章加深但沒有造成壓力？
4. 收尾是否像祝福，而不是要求回應？

**Exit Criteria**：使用者確認內容順序與語氣。

### MVP 2 — Visual And Responsive UI

**Goal**：驗證極光夜空與半透明信箋能否兼顧美感和閱讀性。

**Deliverables**：

- Aurora visual system。
- 桌面與手機版面。
- 三章色彩節奏。
- 九張圖的主圖／細節圖配置。
- 圖片放大檢視與關閉行為。
- Reduced motion fallback。

**Validation Questions**：

1. 文字是否始終清楚？
2. 圖片是否推進故事，而非只是裝飾？
3. 手機是否能單手完成閱讀與操作？
4. 視覺是否過度華麗而搶走故事焦點？

**Exit Criteria**：桌面與 390px 寬度無橫向溢位，主要文字對比與操作尺寸合格。

### MVP 3 — Audio Playback

**Goal**：在不分析音訊內容的前提下驗證播放器狀態與格式備援。

**Deliverables**：

- 單一共用 `<audio>` element。
- Play、Pause、Progress、Current Time、Duration、Replay。
- 同時只播放一首。
- MP3 優先、WAV fallback。
- Loading、Ready、Playing、Paused、Ended、Error 狀態。
- 缺少素材時的友善提示。

**Validation Matrix**：

| MP3 | WAV | Expected Result |
|---|---|---|
| 有 | 有 | 優先使用 MP3 |
| 無 | 有 | 自動使用 WAV |
| 有 | 無 | 使用 MP3 |
| 無 | 無 | 顯示尚未放入曲目，故事仍可閱讀 |

**Exit Criteria**：Chrome、Edge 與至少一種行動裝置瀏覽器完成三首曲目基本播放測試。

### MVP 4 — Real Assets And Content Review

**Goal**：由使用者在本機放入真實素材後進行整體體驗驗證。

**Owner Boundary**：音訊由使用者自行放入與決定是否公開提交；AI 不進行內容分析。

**Deliverables**：

- 三首真實音訊。
- 每章三張最佳化 PNG。
- 最終曲名、替代文字與圖片說明。
- 最終祝賀文案。

**Exit Criteria**：使用者親自確認曲目對應、圖片對應、文字對應與公開發布意願。

### MVP 5 — GitHub Pages Release

**Goal**：發布可分享網址並完成發布後 QA。

**Deliverables**：

- GitHub Pages 設定。
- Production URL。
- Desktop / Mobile smoke test。
- 404、音訊 MIME、圖片載入與 console 檢查。
- 發布版本與 rollback commit。

**Exit Criteria**：公開網址可完成封面至終章的完整旅程，且使用者確認可以分享。

## Acceptance Criteria

### Story Flow

- Given 使用者開啟網站，When 按下「開啟這封信」，Then 進入第一章且不自動播放音訊。
- Given 使用者閱讀任一章節，When 到達章節末端，Then 看見與該章唯一對應的播放卡片。
- Given 使用者前往下一章，When 回到上一章，Then 內容與控制項仍可正常使用。

### Audio Fallback

- Given MP3 不存在但 WAV 存在，When 使用者按下播放，Then 使用 WAV 播放且不要求修改 HTML。
- Given MP3 與 WAV 都不存在，When 使用者按下播放，Then 顯示可理解的缺檔提示且頁面不崩潰。
- Given 一首曲目正在播放，When 使用者播放另一首，Then 前一首自動暫停。

### Responsive And Accessibility

- Given 390px viewport，When 瀏覽全部章節，Then 不出現橫向捲動。
- Given 鍵盤使用者，When 依序操作，Then 所有主要控制項具有可見焦點並能啟用。
- Given 系統開啟 reduced motion，When 載入網站，Then 不使用大幅位移或持續動畫。

## Review Checkpoints

每一階段只回答一組核心問題：

1. MVP 0：範圍與素材契約正確嗎？
2. MVP 1：故事順序與文字正確嗎？
3. MVP 2：畫面是否美且好讀？
4. MVP 3：播放是否穩定且容易理解？
5. MVP 4：真實素材組合是否符合心意？
6. MVP 5：公開網址是否可以放心分享？
