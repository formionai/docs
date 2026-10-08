# 💬 FORA — the autonomous trading intelligence

<figure><img src=".gitbook/assets/fora-hero.jpg" alt=""><figcaption><p>FORA — Formion's autonomous trading intelligence</p></figcaption></figure>

**FORA** began as a conversational assistant and has grown into something closer to a cognitive system. It perceives the whole market, reasons from retrieved evidence, remembers, learns from measured outcomes, trades autonomously to prove its own edge, and even *evolves* new strategies — all under strict, non-custodial safety.

Talk to it in plain language on **Telegram (`@formiontradingbot`)**, in the FORA chat on formion.ai and app.formion.ai, or at **fora.formion.ai**. It works across your account and replies in your interface language (English, Serbian, Croatian, Russian, German, French, Spanish, Italian, Portuguese, Polish or Turkish).

```mermaid
flowchart LR
  P["👁️ Perception"] --> R["🧠 Reasoning"]
  R --> M["📚 Memory"]
  M --> L["📈 Learning"]
  L --> A["⚡ Action"]
  A --> S["🧬 Self-improvement"]
  S --> P
```

> **The cognitive loop.** Perceive → reason (verified) → remember → learn from outcomes → act (gated) → improve — then feed the result back into perception. Each pass makes the next one sharper.

***

## System architecture

The six layers below describe FORA's cognitive loop: how market observations become a reasoned plan, how context is remembered, and how outcomes inform later research. They explain the system's approach; an available analysis tool does not by itself authorise live execution.

```mermaid
flowchart TB
  U["You — web text, realtime voice or Telegram"] --> P["Perception — market context"]
  P --> R["Reasoning — evidence and alternatives"]
  R --> M["Memory — preferences and prior context"]
  M --> L["Learning — measured outcomes"]
  L --> A["Autonomy — paper or authorised actions"]
  A --> S["Self-improvement — evaluate strategy candidates"]
  S --> P
  A --> L
```

Separate the data supporting an answer from the trade outcome used to evaluate it. Review the source, timestamp and relevant account permissions whenever acting on analysis.

***

## I. Perception — it reads the whole market

Most "AI assistants" see a single chart. FORA ingests the full market state across **spot, perpetual futures, on-chain tokens, prediction markets, forex, metals and indices**, reasoning over dozens of dimensions at once: multi-timeframe trend and regime, open interest, funding, taker flow, long/short positioning, cumulative delta, footprint, depth imbalance, liquidation clusters, capital flow, sentiment, narrative, and — for emerging tokens — an on-chain safety read, lifecycle stage and entry timing.

Its awareness is **self-extending**: a discovery layer continuously catalogs every capability in the platform, so when Formion ships a new tool, FORA learns to use it automatically — no manual wiring, no retraining.

<figure><img src=".gitbook/assets/fora-robot.png" alt="" width="180"><figcaption><p>One mind over the whole market — not a chatbot bolted onto a chart.</p></figcaption></figure>

***

## II. Reasoning — verification and evidence

The defining property of FORA is **epistemic discipline**: it is engineered not to make things up.

* **Self-verification.** Check numerical and directional claims against the fetched data; verification is intended to correct or remove unsupported statements.
* **Provenance.** Each answer shows *what it is based on*.
* **Internal deliberation.** For decisions that matter, FORA convenes an internal panel — bullish, bearish, risk and quantitative perspectives — and synthesizes a verdict with the dissent made visible.
* **Causal reasoning.** It thinks in cause-and-effect chains across markets, not loose correlation.

**Theory of mind.** FORA models *other participants*. Price is drawn toward resting liquidity; FORA scores the pull of each liquidation/stop cluster $k$ at price $p_k$ with intensity $I_k$, relative to the current price $P$:

$$
\Pi(P) \;=\; \sum_{k} \frac{I_k}{\,\lvert P - p_k\rvert + \varepsilon\,}
\qquad\text{and crowd skew}\qquad
\lambda \;=\; \frac{L}{L+S}
$$

where $L,S$ are long/short positioning. The further $\lambda$ sits from $0.5$, the more one side is offside — the fuel for the squeeze that hunts *their* stops first.

{% hint style="success" %}
**Measured, not marketed.** Judge a claim by its source and a signal by its tracked outcome. Review sample size and data freshness before relying on either.
{% endhint %}

***

## III. Memory — it actually remembers

FORA carries **persistent memory** of who you are (instruments, style, recurring mistakes, language), **episodic memory** of market events and how they resolved, and **semantic recall** over your whole history.

Recall is not keyword matching — it is a vector-space model. For query $q$ and a memory $d$, relevance is the term-frequency–inverse-document-frequency cosine, length-normalized so a long ramble can't outweigh a precise fact, with a gentle recency boost:

$$
\mathrm{sim}(q,d)=\frac{1}{\sqrt{\lvert d\rvert}}\;\rho(d)\sum_{t\,\in\,q} \mathrm{idf}(t)\,\mathbf{1}[\,t\in d\,]
,\qquad
\mathrm{idf}(t)=\ln\!\frac{N+1}{\mathrm{df}(t)+1}+1
,\qquad
\rho(d)=1+0.4\,e^{-\Delta t/30}
$$

Rare, informative terms ($\mathrm{idf}$) dominate; $N$ is the corpus size, $\mathrm{df}(t)$ how many memories contain $t$, and $\Delta t$ the memory's age in days.

***

## IV. Learning — it grades itself

Every concrete call FORA makes is **logged and later measured against the real price**. From that it builds a per-setup track record and **calibrates its own confidence** to the empirical hit-rate $\hat p = h/n$. To stay honest on small samples it never quotes raw $\hat p$ alone — it reasons with the **Wilson lower bound**, which shrinks confidence when evidence is thin:

$$
p_{\text{lo}}=\frac{\hat p+\dfrac{z^{2}}{2n}-z\sqrt{\dfrac{\hat p(1-\hat p)}{n}+\dfrac{z^{2}}{4n^{2}}}}{1+\dfrac{z^{2}}{n}}
$$

Edges are judged in the language of expectancy, risk-adjusted return and drawdown — the same metrics every strategy in Formion is held to:

$$
\mathbb{E}[R]=p\,\mu_{\text{win}}-(1-p)\,\mu_{\text{loss}}
,\qquad
\mathrm{Sharpe}=\frac{\mu_R}{\sigma_R}
,\qquad
\mathrm{MaxDD}=\max_{t}\frac{\text{peak}_t-\text{equity}_t}{\text{peak}_t}
$$

It also learns from aggregate, privacy-preserving base rates across the platform, so its judgment compounds with experience.

***

## V. Autonomy — it trades to prove itself

Talk is cheap, so FORA puts itself on the line. In a **simulated paper account** it selects setups, opens positions with predefined risk, and **measures its own results** — win-rate, expectancy and equity curve, the same metrics used for any other strategy in Formion.

<figure><img src=".gitbook/assets/fora-track-record.png" alt=""><figcaption><p>Tracked FORA decisions are evaluated through measured outcomes — win-rate, expectancy, equity curve.</p></figcaption></figure>

When you want it to act on your real account, it does so **only through hard safety gates**. An order $o$ executes if and only if every gate passes:

$$
\text{execute}(o)\iff \underbrace{A}_{\text{armed}}\,\wedge\,\underbrace{C}_{\text{you confirm}}\,\wedge\,\underbrace{E}_{\text{opted-in}}\,\wedge\,\underbrace{B}_{\text{your broker}}\,\wedge\,\bigl(\,\text{notional}(o)\le N_{\max}\,\bigr)\,\wedge\,\bigl(\,n_{\text{open}}<K_{\max}\,\bigr)
$$

By default FORA only **proposes** an order with a real quote (size, price, fee); nothing executes until you confirm and enter your trading password. Hands-free execution happens only if you switch on **FORA Autotrade** yourself (Pro; profile → Connections) for your linked cTrader account — every order is capped by your max per order, max trades per day and max total per day, and the kill-switch stops it instantly.

FORA is **non-custodial** — it connects to your own exchange or broker, never holds or withdraws funds, and defaults to *fail-closed*: if anything is unset, nothing trades.

```mermaid
flowchart TD
  I["💡 Idea / signal"] --> V{"🔬 Verified vs data?"}
  V -->|no| X["discard / correct"]
  V -->|yes| C{"✅ All 6 gates pass?"}
  C -->|no| H["stays an idea"]
  C -->|yes| E["⚡ Execute on YOUR account"]
  E --> T["📊 Tracked as a measured trade"]
```

***

## VI. Self-improvement — toward a self-evolving edge

This is where FORA reaches beyond a conventional assistant.

**Self-tuning.** It adjusts its *own* parameters from measured results, within safe reversible bounds. With recent win-rate $\hat w$ and a target band $[\tau_{\text{lo}},\tau_{\text{hi}}]$, a threshold $\theta$ updates as

$$
\theta_{t+1}=\mathrm{clip}\!\Big(\theta_t+\delta\big(\mathbf{1}[\hat w<\tau_{\text{lo}}]-\mathbf{1}[\hat w>\tau_{\text{hi}}]\big),\;\theta_{\min},\,\theta_{\max}\Big)
$$

— stricter when it slips, bolder when it is on form. Larger structural changes are *proposed for human review*; it never rewrites itself unattended.

**Evolutionary strategy discovery.** FORA runs a **genetic search** over the space of complete strategy specifications $s=(\text{archetype},\text{entry},\text{stop},\text{targets},\text{trailing},\dots)$. A population is bred, each member backtested on a search window that excludes a locked holdout, the fittest selected, then crossed and mutated across generations. Fitness rewards risk-adjusted return on that search window:

$$
F(s)=R_{\text{net}}(s)+4\,\mathrm{Sharpe}(s)+3\min\!\big(\mathrm{PF}(s),4\big)-0.3\,\lvert\mathrm{DD}(s)\rvert
\quad\text{s.t.}\quad \mathrm{beats\text{-}HODL}(s)\,\wedge\,n_{\text{trades}}(s)\ge 10
$$

```mermaid
flowchart LR
  G0["🎲 Population of strategies"] --> BT["🔬 Backtest on search window"]
  BT --> SEL["🏆 Select fittest F(s)"]
  SEL --> XO["🧬 Crossover + mutate"]
  XO --> G0
  SEL --> W["💎 Winner → locked holdout → saved only on EDGE"]
```

The single winner is then scored once on the locked holdout of unseen data; only an **EDGE** verdict is saved as a FORA-built strategy and tracked. Most runs end with nothing saved — that is the filter working. FORA is **searching** for edges, not selecting from a fixed menu.

***

## Using FORA day to day

* **Ask anything** — *"how's my portfolio?"*, *"analyze SOL on the 4h"*, *"which tokens are trending?"*, *"who's trapped here?"*
* **Research, scans and guided wizards** — all from a sentence.
* **Trade commands** on your connected exchange / broker — always with confirmation.
* **Smart model routing** — fast models for short answers and stronger reasoning models from Anthropic (Claude) and OpenAI for analysis. Bring your own key (**BYOK** — Anthropic, OpenAI, Gemini, Grok, DeepSeek, Kimi, GLM, MiniMax or OpenRouter) on any plan, or connect your ChatGPT Plus account (profile → License), so calls run on your provider with no platform budget cap.
* **AI budget** — Neural $2 per month, Pro $5 per day, Institutional $30 per day with priority queue; daily budgets reset at 00:00 UTC. One AI request runs at a time on Neural, three on Pro, ten on Institutional.
* **What each plan adds** — on every plan FORA can chat, explain, read prices, indicators, news, signals and your portfolio, and propose orders and alerts. **Pro** adds web search, deep research, backtests, Edge Finder, social sentiment, chart screenshots and premium platform analytics. **Institutional** adds the 3D robot and live voice.
* **Compare models** — in AI Advisor → AI Chat you can run the same prompt on 2–4 models side by side and see where they agree and disagree (premium models need a paid plan).

<figure><img src=".gitbook/assets/fora-consensus.png" alt=""><figcaption><p>Comparing models side by side — never trusting a single model's blind spot.</p></figcaption></figure>

***

## What FORA is not

FORA does not custody funds. Live actions require the applicable authorisation and account permissions; automated workflows follow the limits you configure. Check the supporting data before treating an AI answer as fact. It is an instrument that **amplifies the trader's judgment** — relentlessly informed, honestly calibrated, and always measured — not a black box that asks for blind trust.

{% hint style="info" %}
Link your Telegram from **formion.ai → Profile → Connections** to talk to FORA across your account. See the broader system in the **[Thesis](thesis.md)**, **[Vision](vision.md)** and **[Roadmap](roadmap.md)**.
{% endhint %}

## Text, realtime voice and Command Center

On the dashboard, [Command Center](command-center.md) lets you choose suggested commands or type your own request. Use **Commands** to launch a floating FORA conversation, or **Chat** to converse inside the card when available. Attach images, PDFs, DOC/DOCX, text or CSV files (up to 12 MB per file) for context; inspect and remove an attachment before sending if it is not relevant. FORA can also generate reports as PDF, DOCX, TXT or Markdown, draw levels on your Formion chart and, on the chart page, read a snapshot of the chart you are on or a shared screen.

**Live two-way voice** with FORA is available by plan, and its daily limits depend on your plan (see [Plans & Pricing](pricing.md)). In the chart chat you can also turn on read-aloud replies and microphone dictation from its settings gear, using your browser's built-in speech features. Describe the instrument, timeframe and intended task clearly, and inspect the written context before authorising a trade. Voice is another conversation mode; it does not bypass account permissions or risk controls.

Try “analyse BTC on the 4h”, “compare strategies #1 and #2” or “show my open positions”. The command examples are starting points; a successful action still depends on the available tool, connected account and licence. Connect crypto venues through [Brokers](brokers.md), or authorise **cTrader** for forex and CFDs. Manage what FORA remembers in profile → Connections → FORA Memory, and pin standing rules (for example “I never use more than 3x leverage”) with **Teach FORA**. [Trades History](trades-history.md) and [Journal](journal.md) help separate evaluated calls, paper trades and your actual account outcomes.

## Reading the scientific model in practice

The equations above explain how evidence can be ranked and evaluated. They are not a separate order-entry interface. A liquidity score, confidence interval or strategy fitness score should be read with its inputs and the period that produced it.

### Perception: begin with the question

For a market question, give FORA the instrument and timeframe rather than just “buy or sell?”. Compare trend, funding and positioning with the chart. For an account question, identify the connected account; market data and your portfolio are different contexts. An unavailable input should remain a gap in the analysis rather than becoming an assumed value.

### Reasoning: compare alternatives

Ask for the bullish case, bearish case and invalidation level. A useful plan explains what would have to happen for each scenario, which observations support it and what would contradict it. The crowd-skew expression describes an imbalance; it does not establish when a squeeze will occur. A liquidation cluster can be relevant context without becoming a guaranteed target.

### Memory: make context explicit

Tell FORA your preferred instruments, trading horizon and risk constraints when they matter to a request. If remembered context is out of date, correct it in the conversation. Semantic relevance and recency help explain why an earlier discussion can be useful, but a remembered price or setup still needs a current market check.

### Learning: inspect the sample

The Wilson expression accounts for uncertainty in a small sample. A high hit rate from a few calls should not be read like the same hit rate over a larger, comparable record. Expectancy adds the size of wins and losses; win rate alone cannot establish an edge. Drawdown describes the path, and a Sharpe-style ratio depends on the return sampling used.

Use the available [Trades History](trades-history.md) source to inspect the record behind a claim. Check resolved versus open trades, the evaluation window and whether the source describes backtests, paper positions or live activity. Avoid comparing differently defined returns as if they shared a denominator.

### Autonomy: separate a proposal from an action

A research answer may propose an entry, stop and targets. Review those alongside the account, market and size before any live action. An automated bot follows the permissions and limits you configured; a paper workflow records a simulation. Use the [connection guide](how-to-start-api-connection.md) to verify the account and [Bots](bots.md) to review automation separately from conversation.

### Self-improvement: validate a candidate again

A candidate selected by a search is still a hypothesis. Parameter tuning can improve the score on the data used to select it without improving later performance. Keep a separate validation window, compare drawdown and costs, and forward-test on paper before considering a live deployment. [Strategy Lab](strategy-lab.md) provides Builder, Backtest, Sweep and Compare for this review.

## A complete research conversation

1. Start in Command Center with an instrument, timeframe and research question.
2. Add the relevant chart or document if the question depends on that material.
3. Ask FORA to explain the supporting observations, alternatives and invalidation.
4. Refine the plan with your account context and risk constraints.
5. Test a strategy candidate in Strategy Lab or follow an evaluated call in its paper source.
6. Review the resulting record, then revisit the original assumption with FORA.

{% hint style="info" %}
The loop is useful because outcomes can change the next question. Keep the observation, hypothesis, permitted action and measured result distinct throughout the conversation.
{% endhint %}
