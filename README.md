# story_talker

```md
我想要寫一個 AI 的小玩具，可以讓 AI 與 AI 互動創造故事，會有以下幾個主要功能：

# 主要功能
1. 由使用者串接自己的 LLM API，可以由兩種方式串接 API
- 利用與 openai 相容的 API，所以這邊要有 base_url、model、API_Key 的填寫欄位等等
- 串接 dify.ai 的 API，就像 cline 可以用 dify 的模型一樣，讓使用者也可以選擇串接他們自己 dify 的 AI，使用 LLM 模型
2. 其中會需要兩個 LLM 模型（A、B，詳於下列解說），使用者可以分別各自選擇串接不同 API
3. 程式運行的流程大致會是 ：使用者填寫 system prompt（給 LLM 提供最主要的指導）、user prompt（使用者提出的故事設定與主題） --> 傳送給 A LLM，A 會想好怎麼使用這些故事與主題轉化成讓 B LLM 寫故事的 Prompt --> B 同時接收到 system prompt、user prompt（A LLM 給予的 prompt）--> A LLM 收到故事後評估如何修改、推進、延伸、減縮等等 --> 提出給 B LLM --> ……（依照回合數循環）
4. 需要串流顯示（逐字輸出）

# UI
1. 使用 React 技術製作，而非 Python
2. 其中會有幾個地方可以提供填寫： system prompt（給 LLM 提供最主要的指導）、user prompt（使用者提出的故事設定與主題）、AI 雙方互動詢問的回合數；故事輪迴完畢後，將可以讓使用者選擇完成或者修正/繼續，如果選擇繼續的話，則一樣挑選回合數 / 選擇修正的話，則讓使用者利用 prompt 指出那些地方有需要修正，然後選擇回合數再繼續（A 和 B 有獨立的 System Prompt）
  - A LLM 專屬 System Prompt（導演指令）— 控制 A 如何評估/引導故事
  - B LLM 專屬 System Prompt（作家指令）— 控制 B 的寫作風格
3. 在開始運行時，介面會有點像是兩方在對話，先讓 A LLM 從右方提出的顯示在畫面，接著左方的回答顯示在畫面，這樣兩邊來回運行
4. 需要匯出功能，格式：
  - Markdown / TXT / PDF / HTML（現場的左右聊天網頁形式）
  - 儲存/載入對話歷史（localStorage）
  - 兩種匯出：全部 / 僅匯出 B 的故事內容（去掉 A 的導演指令）

# 其他
請幫我想出還有什麼其他可以做設定的

請先幫我做出 Plan，告訴我我上面那些想要知道的答案，讓我選擇完畢再開始製作
```
