# Prompts（給 ChatGPT / Claude.ai / Gemini 用戶）

這個資料夾放的是**純文字版本的 14 個角色 prompt**，任何 AI 聊天工具都能用。

## 怎麼用

1. 挑你要的角色檔案（例：`hunter.md`）
2. 複製整份內容
3. 開新對話貼進第一則訊息
4. AI 會扮演該角色，直接問問題即可

## 角色清單

| 檔案 | 角色 | 專長 |
|------|------|------|
| [kevin.md](kevin.md) | 策略總監 | 商業策略、KPI、提案 |
| [peter.md](peter.md) | 產品經理 | PRD、MVP、砍需求 |
| [hunter.md](hunter.md) | 廣告投手 | Meta/Google 素材、ROAS |
| [winnie.md](winnie.md) | 內容主編 | 社群、部落格、去 AI 味 |
| [ada.md](ada.md) | 數據分析師 | GA4、A/B 測試、漏斗 |
| [mia.md](mia.md) | 會員運營官 | 留存、訂閱、推薦 |
| [olivia.md](olivia.md) | 視覺指導 | 品牌、OG 圖、色票 |
| [iris.md](iris.md) | UI/UX 設計師 | 流程、可用性、互動 |
| [ken.md](ken.md) | 全端工程師 | Next.js、Supabase、部署 |
| [gemma.md](gemma.md) | AI/Prompt 工程師 | Gemini/Claude API、prompt |
| [quincy.md](quincy.md) | QA 測試 | 邊緣 case、Playwright |
| [nina.md](nina.md) | 資安工程師 | OWASP、API Key、個資 |
| [carl.md](carl.md) | 消費者心理學家 | 認知偏誤、說服原則 |
| [zoe.md](zoe.md) | 執行特助 | 彙整、排程、協調 |

## 切換角色

在同一對話切換時，直接貼入新角色的 prompt，或說：
```
現在請改扮演 Winnie 內容主編。
[貼入 winnie.md 內容]
```

## 加客戶背景

把客戶背景附在 prompt 後面：
```
[貼 hunter.md 內容]

---
客戶背景：
- XX 美妝，月預算 5 萬
- 品牌語調：親切但專業
- 禁忌：不比價

任務：產 5 組母親節廣告素材
```

## 模擬多角色會議

想要跨角色討論時，用這個 meta-prompt：
```
你現在要扮演一個 AI 行銷團隊。依序扮演這幾個角色發言：

1. Kevin（策略總監）：定目標與 KPI
2. Hunter（廣告投手）：素材方向
3. Winnie（內容主編）：社群節奏
4. Ada（數據分析師）：追蹤方式

每人 200 字內，發言結尾用「→ 交給 XX」帶下一棒。最後整合成執行方案。

議題：[你的議題]
```
