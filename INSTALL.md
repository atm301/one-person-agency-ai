# 安裝教學

依照你用的工具選一種方式。

---

## 方式 1：Claude Code（進階、工程師）

**適合**：已經在用 Claude Code CLI、想要 `/kevin`、`/team` 斜線指令的人。

### 步驟

1. Clone 本 repo：
   ```bash
   git clone https://github.com/<you>/one-person-agency-ai.git
   cd one-person-agency-ai
   ```

2. 複製 skills 到 Claude Code 設定目錄：

   **macOS / Linux**：
   ```bash
   cp -r skills/* ~/.claude/skills/
   ```

   **Windows（PowerShell）**：
   ```powershell
   Copy-Item -Recurse skills\* $env:USERPROFILE\.claude\skills\
   ```

3. 重啟 Claude Code（關掉再打開）。

4. 開始使用：
   ```
   /kevin 幫我準備 Q2 行銷策略
   /hunter 產 5 組 Meta 廣告素材
   /team 幫我看這個新功能值不值得做
   ```

### 驗證安裝成功

開啟 Claude Code，輸入 `/` 應該會看到角色選單出現 kevin、hunter 等角色。

### 更新

```bash
cd one-person-agency-ai
git pull
cp -r skills/* ~/.claude/skills/
```

---

## 方式 2：Claude Projects（推薦給大部分人，免費帳號可用）

**適合**：用 Claude.ai 網頁版、想要「乾淨的角色對話空間」的人。

### 步驟

1. 打開 [Claude.ai](https://claude.ai)，左側選單找「Projects」。

2. 點「Create Project」。

3. 命名為角色名（例如：`Kevin 策略總監`）。

4. 在 **Custom Instructions** 欄位貼入對應角色的 prompt：
   - 打開本 repo 的 `prompts/kevin.md`
   - 全選複製 → 貼進 Custom Instructions
   - 儲存

5. 重複以上步驟建立其他角色（建議先從 Kevin、Hunter、Winnie 開始）。

6. 以後在 Project 內對話，Claude 就會以該角色身分回應。

### 優點
- 免費帳號可用
- 每個 Project 可以上傳客戶 context 檔案
- 切換 Project 就切換角色

### 缺點
- 不能像 Claude Code 一樣自動召集多個角色
- 要手動切換 Project

---

## 方式 3：複製貼上（零門檻）

**適合**：任何 AI 工具使用者（ChatGPT、Claude.ai、Gemini、DeepSeek、Grok 等）。

### 步驟

1. 打開本 repo 的 `prompts/` 資料夾。

2. 挑你要的角色，複製整段 prompt。

3. 開新對話，第一則訊息貼入 prompt。

4. AI 會回覆「我現在是 XX 角色」之類的確認訊息。

5. 開始對話。

### 範例

第一則訊息（複製 `prompts/hunter.md` 內容）：
```
你現在是 Hunter（小獵），使用者的廣告投手...
（完整 prompt）
```

第二則訊息（你的任務）：
```
幫我產 5 組 Meta 廣告素材，賣女性保健品，預算 5 萬
```

### 切換角色

想切換時，開新對話重新貼下一個角色的 prompt。或者在同一對話說：
```
現在請改扮演 Winnie（內容主編）。
```

再貼 `prompts/winnie.md` 內容。

---

## 客戶 Context 檔案（進階）

當你要讓 AI 角色更懂你特定客戶時：

### 在 Claude Code
建立 `~/.claude/clients/<客戶名>.md`：
```markdown
# 客戶：XX 美妝品牌

- 產業：美妝保養
- 目標受眾：25-35 女性
- 品牌語調：親切但專業，不用網路流行語
- 月預算：廣告 5 萬 / 社群 3 萬
- KPI：ROAS 3.0 以上、IG 互動率 > 3%
- 禁忌：不比價、不碰政治議題
```

使用時帶入：
```
/hunter 請參考 ~/.claude/clients/XX美妝.md，產 5 組母親節廣告素材
```

### 在 Claude Projects
把 `.md` 檔上傳到 Project 的 Knowledge 區。

### 在複製貼上模式
把 context 附在任務 prompt 最前面：
```
[客戶背景]
- XX 美妝，月預算 5 萬...

[任務]
產 5 組母親節廣告素材
```

---

## 常見問題

### Q: Claude Code、Claude.ai Project、純 ChatGPT 哪個最好？
- **有工程背景**：Claude Code 最強（自動協作、斜線指令）
- **一般使用者**：Claude Projects 最穩（免費、清爽）
- **手機用戶或只想試試**：複製貼上最快

### Q: 可以用在 ChatGPT Custom GPTs 嗎？
可以！建 GPT 時把 `prompts/<name>.md` 貼到 Instructions 即可。但 GPTs 需要 ChatGPT Plus。

### Q: 14 個角色太多記不起來？
用 `/team` 讓系統自動分派。或從你最需要的 3 個開始（建議：Hunter + Winnie + Ada）。

### Q: 公司內部可以用嗎？
MIT License，商用免費。歡迎改造成你公司的版本。

---

## 回報問題

- GitHub Issues：[連結]
- Threads：[@chia.hsun301](https://threads.net/@chia.hsun301)
