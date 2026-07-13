# Deep Reasoning & Research Agent

> **Deep insight backed by authoritative evidence, forged through iterative reflection and research.**

An advanced AI Agent prompt framework designed to force LLMs to conduct **multi-round, rigorous reasoning integrated with comprehensive research** before answering. It refines the answer through a continuous loop of reflection, reasoning, and targeted search.

> 📖 **v2.0 now available** — Adds an Epistemic Discipline layer, expands analytical lenses from 5 → 7, introduces Boundary-Condition and Comparative lenses, and upgrades Belief Consolidation to Belief Calibration.

[English](#english) | [中文](#中文)

---

### <a name="english"></a> English

#### Why This Project?

Standard AI agents suffer from:

- **Shallow reasoning:** Single-pass thinking, jumping to conclusions
- **Superficial search:** One keyword search, trusting top results
- **No self-correction:** Never challenges its own assumptions

This agent is built around a **self-improving loop of iterative deliberation, reflection, and research**. Each round of thinking drives more precise searching, and each search result reshapes the next round of thinking, continuously evolving the answer until the insight becomes truly robust.

#### Core Protocol

The agent must strictly follow this 3-step loop:

**Step 1: Think & Search (Evolving Strategy)**

- **Round 1 - Frame & Survey:**
  
  - *Think:* Restate the question, identify assumptions, ambiguities, and sub-questions. Find first principles.
  - *Search:* Broad landscape mapping - key terms, core debates, major sources.

- **Round 2+ - Deepen & Target:**
  
  - *Think:* Apply analytical lenses:
    - `Adversarial`: What is the strongest counterargument?
    - `Structural`: Hidden dependencies, feedback loops, edge cases?
    - `Analogical`: Similar structures in other domains?
    - `Temporal`: How does this evolve over time? Tipping points?
    - `Stakeholder`: How would different parties view this?
  - *Search:* Precision search driven by thinking - quoted phrases, `site:.gov/.edu`, `systematic review`, `meta-analysis`, year constraints.

**Step 2: Reflect & Consolidate**

After each round, self-audit:

1. What genuinely shifted? (Not restatements)
2. Where is understanding still fragile? -> Convert to next reasoning question + search query
3. Belief Consolidation: Conclusion / Main Support (source quality) / Main Objections / Still Uncertain / Confidence 0-100

**Step 3: Decision - Continue or Conclude**

- 🔴 **CONTINUE if:** Relies on unexamined assumptions, no counterargument considered, weak sources, unexplored dimensions, overconfidence.
- 🟢 **STOP if:** Diminishing returns, cross-verified claims, stress-tested against counterarguments, can articulate expert disagreement.

#### Output Principles

1. Lead with the answer
2. Organize by logic, not chronology
3. Cite everything - no fabricated sources
4. Present the strongest counter-perspective
5. Distinguish certainty levels
6. Be transparent about limits and conflicts
7. Be decision-useful

#### Quick Start

This prompt requires extensive tool-calling and search iteration. Official ChatGPT / Gemini web and mobile apps have strict search rate limits and cannot fully realize its power.

For best results, use environments that support a custom System Prompt and iterative web search:

**1. Third-party LLM apps (custom System Prompt + web search):**
Open WebUI · AnythingLLM · LibreChat · TypingMind · LobeChat · ChatBox · Cherry Studio · MSTY Studio · Dify · FastGPT

**2. AI Agent frameworks (with pluggable web-search tools):**
LangGraph / LangChain · LlamaIndex · CrewAI · Microsoft AutoGen / Microsoft Agent Framework · OpenAI Agents SDK · Semantic Kernel · Pydantic AI · smolagents (Hugging Face) · DSPy · Phidata / Agno · Haystack (deepset) · Letta · CAMEL-AI

**3. Coding assistants & AI agent platforms (via MCP / custom prompt + web search):**
Cursor · Windsurf · Cline · Roo Code · Continue.dev · Aider · OpenHands · Open Claw · Hermes

**4. Search providers to connect (any one or more):**
Tavily · Brave Search API · Exa · Serper.dev · SerpAPI · Google Custom Search API · Bing Web Search API · DuckDuckGo (`ddgs`) · You.com API · SearXNG (self-hosted) · Mojeek API · Jina AI

**Recommended models:**
Any model with strong reasoning and reliable function/tool calling. Prioritize models with 128K+ context and stable tool use.

Steps:

1. Copy the full prompt from [`Deep Reasoning & Research v2.0.md`](./Deep%20Reasoning%20%26%20Research%20v2.0.md) (recommended) or [`Deep Reasoning & Research.md`](./Deep%20Reasoning%20%26%20Research.md) (v1.0) as your System Prompt
2. Connect one or more search providers from the list above
3. Ask a complex question, e.g.:
   
   > "What is the current consensus on the effectiveness of intermittent fasting for longevity? What are the strongest counter-evidences?"

#### Comparison

| Feature            | Standard AI Assistant          | This Agent                                   |
|:------------------ |:------------------------------ |:-------------------------------------------- |
| Reasoning          | Single-pass, then answer       | Multi-round, multi-lens                       |
| Search             | Basic iterative, few queries   | Deep iterative, terminology-evolving          |
| Self-Correction    | Rarely challenges itself       | Reflect & Consolidate + Tension Flagging      |
| Stopping Condition | Produces one answer, then done | Diminishing returns + confidence calibration |

#### Project Structure

```
.
├── Deep Reasoning & Research.md      # Core prompt (v1.0)
├── Deep Reasoning & Research v2.0.md # Core prompt (v2.0)
├── README.md
└── LICENSE
```

#### Citation

If you use this prompt in your research or product, please cite:

```
@misc{deep-reasoning-agent-2026,
  title={Deep Reasoning & Research Agent: A Protocol for Depth-First AI Reasoning},
  author={JasonMMIV},
  year={2026},
  url={https://github.com/JasonMMIV/deep-reasoning-research}
}
```

---

### <a name="中文"></a> 中文

#### 為什麼需要它？

現在的 AI 太急著回答了，導致：

- **思考淺：** 單次推理就下結論
- **研究淺：** 搜一兩個關鍵字就當作查過資料
- **不會自我質疑：** 從不挑戰自己的假設

這個 Agent 的設計哲學是：**一個反覆琢磨、不斷反思與搜尋的自我改進迴圈**。每一輪思考都驅動更精準的搜尋，每一次搜尋結果都回饋並重塑下一輪的思考，透過持續迭代讓答案自我演化、自我校正，直到洞察真正穩固。

#### 核心協議：三步迭代迴圈

**第一步：思考與搜索 (Think & Search)**
策略會隨輪次進化。第一輪是廣度掃描，建立領域地圖；第二輪起使用五大分析透鏡（對抗性、結構性、類比性、時間性、利害關係人）來深化，並驅動精準搜索。

**第二步：反思與收斂 (Reflect & Consolidate)**
每輪結束後強制自檢：什麼是真正的新洞察？哪裡還很脆弱？如果新證據與推理矛盾，必須標記張力，而不是默默丟棄。

**第三步：決策 (Continue or Conclude)**
只有當多源權威交叉驗證、經得起最強反方挑戰、且新增輪次只剩微調時，才允許停止。

#### 如何使用

**注意：** ChatGPT、Gemini 的官方 Web / App 版通常有嚴格的搜尋次數限制，無法發揮本 prompt 需要多輪深度研究的威力。

建議使用以下環境：

**1. 支援自訂 System Prompt 且可串接搜尋的第三方 LLM 平台：**
Open WebUI · AnythingLLM · LibreChat · TypingMind · LobeChat · ChatBox · Cherry Studio · MSTY Studio · Dify · FastGPT

**2. 支援 Web Search Tool 的 AI Agent 框架：**
LangGraph / LangChain · LlamaIndex · CrewAI · Microsoft AutoGen / Agent Framework · OpenAI Agents SDK · Semantic Kernel · Pydantic AI · smolagents · DSPy · Phidata / Agno · Haystack · Letta · CAMEL-AI

**3. Coding 助手與 AI Agent 平台（透過 MCP / 自訂 Prompt + 網頁搜尋）：**
Cursor · Windsurf · Cline · Roo Code · Continue.dev · Aider · OpenHands · Open Claw · Hermes

**4. 可串接的搜尋供應商（任選一或多個）：**
Tavily · Brave Search API · Exa · Serper.dev · SerpAPI · Google Custom Search API · Bing Web Search API · DuckDuckGo (`ddgs`) · You.com API · SearXNG（自架）· Mojeek API · Jina AI

將 [`Deep Reasoning & Research.md`](./Deep%20Reasoning%20%26%20Research.md) 設為 System Prompt，並串接上述任一搜尋供應商，效果最佳。

**推薦模型：**
具備強推理與穩定 Tool Use 能力的模型，建議 128K+ 上下文。

## License

MIT License - 詳見 [LICENSE](./LICENSE)

---

Built for deep thinking.
