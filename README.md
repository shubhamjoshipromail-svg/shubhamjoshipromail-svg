<p align="center">
  <img src="assets/hero.svg" width="100%" alt="Shubham Joshi. Applied AI, Data Science, AI Product. Four systems: Govern (AgentDock), Explain (RxCheck), Assist (Nimbus), Create (FridgeChef)."/>
</p>

<p align="center">
  <a href="https://portfolio-production-9040.up.railway.app"><img src="https://img.shields.io/badge/Portfolio-live-ffb454?style=for-the-badge&labelColor=0c1424" alt="Live portfolio"/></a>
  <a href="https://www.linkedin.com/in/shubham-joshi1/"><img src="https://img.shields.io/badge/LinkedIn-shubham--joshi1-0a66c2?style=for-the-badge&labelColor=0c1424" alt="LinkedIn profile"/></a>
  <a href="https://huggingface.co/shubhamjoshipro"><img src="https://img.shields.io/badge/%F0%9F%A4%97%20Models-shubhamjoshipro-ffcc4d?style=for-the-badge&labelColor=0c1424" alt="Hugging Face models"/></a>
  <a href="mailto:shubhamjoshipro.mail@gmail.com"><img src="https://img.shields.io/badge/Email-say%20hello-2b3d63?style=for-the-badge&labelColor=0c1424" alt="Email Shubham"/></a>
</p>

<p align="center">MS Business Analytics &amp; AI @ Johns Hopkins (Dean&#39;s Scholarship, July 2026) &#183; Washington, DC &#183; open to NYC / DC / SF / Remote &#183; ~3 yrs U.S. work authorization, no sponsorship required</p>

---

## The fast lane: four systems

<table>
<tr>
<td width="50%" valign="top">

### ⚙️ Govern: AgentDock

A control plane where multi-agent Flows execute <b>real MCP tools</b> behind deny-by-default policy gates, approval workflows, and budget caps.

<b>Why it matters:</b> agents that act in the real world need governance, not vibes. An agent here can draft your email. Sending is <i>always</i> approval-gated.

<b>Proof:</b> a durable Postgres job queue provides crash recovery, while idempotent external actions ensure a retried step never double-fires.

<i>TypeScript · Next.js · Prisma · Postgres + pgvector · official MCP SDK · Vitest</i>

<a href="https://github.com/shubhamjoshipromail-svg/AgentDock">Source &amp; architecture →</a>

</td>
<td width="50%" valign="top">

### 💊 Explain: RxCheck

A pharmacist-facing drug-interaction reviewer over <b>152,416 records</b>, built on one hard boundary: <b>the database decides; the LLM only explains.</b>

<b>Why it matters:</b> in clinical decision support, hallucination is not a UX bug. Detection is deterministic, and the model is a bounded explanation layer.

<b>Proof:</b> 26/26-scenario reproducible evaluation; RxNorm normalization; acknowledgment/override audit trails.

<i>Python · FastAPI · SQLAlchemy · Postgres · React · Anthropic API</i>

<a href="https://pharmacy-production-f226.up.railway.app">Live demo →</a> · <a href="https://github.com/shubhamjoshipromail-svg/rxcheck">Source →</a>

</td>
</tr>
<tr>
<td width="50%" valign="top">

### 🎈 Assist: Nimbus

A privacy-first AI companion that catches student burnout early and <b>acts</b>: blocks calendar time, drafts the avoided email, guides breathing, and surfaces help.

<b>Why it matters:</b> action beats advice for someone too fried to act. 9 grounded tools read real context before every reply.

<b>Proof:</b> built in 14 hours with a team of five at the Pava PM Hackathon; deployed and demoable.

<i>Python · FastAPI · Claude tool use · Postgres · Docker · Railway</i>

<a href="https://nimbus-web-production.up.railway.app">Live demo →</a> · <a href="https://github.com/shubhamjoshipromail-svg/nimbus">Source →</a>

</td>
<td width="50%" valign="top">

### 🍳 Create: FridgeChef

A consumer AI cooking product: fridge photos and receipts become structured inventory, then <b>real-time streaming recipes</b>.

<b>Why it matters:</b> shipping consumer AI means caring about latency and unit cost, not just accuracy.

<b>Proof:</b> multi-provider LLM routing (~$0.02/vision scan, ~$0.001/text call); true SSE via a thread-to-async bridge; zero-touch GitHub→Railway CI/CD.

<i>Python · FastAPI · SQLAlchemy · SSE · Railway</i>

<a href="https://fride-project-production.up.railway.app">Live app →</a> · <a href="https://github.com/shubhamjoshipromail-svg/fridgechef">Source →</a>

</td>
</tr>
</table>

## How I build AI

1. <b>Deterministic systems decide; models explain.</b> RxCheck&#39;s detection core never asks an LLM whether an interaction exists.
2. <b>Humans keep the pen on consequential actions.</b> In AgentDock there is no grant configuration under which an outbound send auto-fires.
3. <b>Evaluation is part of the product.</b> OpsPilot&#39;s unstable DeBERTa runs were excluded rather than reported; RxCheck ships a 26-scenario eval you can rerun.
4. <b>The bottleneck is usually the data.</b> OpsPilot went ~52% → ~73% by redesigning a noisy 10-label taxonomy into 7 operational families instead of using a bigger model.
5. <b>Business value and technical correctness belong together.</b> My ACHP capstone turned OLS + HC3 robust errors into national policy advocacy material.

## Tech, with receipts

| Layer | Tools | Where it&#39;s proven |
|---|---|---|
| AI systems | agents, MCP, RAG, tool calling, evals, guardrails | [AgentDock](https://github.com/shubhamjoshipromail-svg/AgentDock), [rxcheck](https://github.com/shubhamjoshipromail-svg/rxcheck) |
| Modeling &amp; NLP | PyTorch, ModernBERT fine-tuning, H2O AutoML, Optuna, SHAP/LIME | [opspilot-ai](https://github.com/shubhamjoshipromail-svg/opspilot-ai), [bank-marketing-ml](https://github.com/shubhamjoshipromail-svg/bank-marketing-ml) |
| Product engineering | TypeScript, Next.js/React, FastAPI, SSE streaming | [AgentDock](https://github.com/shubhamjoshipromail-svg/AgentDock), [fridgechef](https://github.com/shubhamjoshipromail-svg/fridgechef), [portfolio](https://github.com/shubhamjoshipromail-svg/portfolio) |
| Data | Python, SQL/Postgres, ETL &amp; normalization, data quality | rxcheck&#39;s 152K-record import, CMS/ACHP capstone (~109K matched records) |
| Delivery | Railway CI/CD, Docker, Prisma/SQLAlchemy, pytest/Vitest | every live link on this page |

## The deeper lab

<details><summary><b>⚙️ Agent infrastructure &amp; governance</b></summary><br/>
AgentDock&#39;s execution layer: Postgres-backed job queue with lease/heartbeat crash recovery, idempotent external actions, step-cursor resume, SSE event streaming, per-user concurrency caps. Policy plane: deny-by-default grants with permission clamping (read_only &lt; draft_only &lt; approval_required &lt; blocked), Memory Firewall with scoped grants and audit logs, MCP revocation kill-switch. Integration tests run against a dedicated Postgres test database, including a tool-registration RCE security test.
</details>

<details><summary><b>💊 Healthcare AI &amp; responsible boundaries</b></summary><br/>
RxCheck imports 152,416 interactions (172,714 source assertions, 1,967 drugs) with exact → brand → fuzzy → NDC RxNorm resolution and an unresolved-record queue. Findings carry acknowledgment and override workflows with audit events. The 26-scenario formative evaluation proves core checking completes even when every external service (LLM, OpenFDA, RxNorm) fails. It is a research prototype and says so honestly. That boundary discipline is the point.
</details>

<details><summary><b>🎫 Applied NLP: the OpsPilot story</b></summary><br/>
Baselines first: TF-IDF + logistic regression ~44%, CNN ~52%, and ModernBERT on the original taxonomy ~52%. The results showed that the labels were the problem. Redesigning 10 overlapping classes into 7 routing families (~24k leakage-safe examples, fixed splits) produced 73.1% accuracy and weighted-F1 0.713. Confidence gating at 0.80 auto-routes 62.3% of tickets at 85.5% accuracy; the rest escalate to humans. The model is deployed to <a href="https://huggingface.co/shubhamjoshipro/opspilot-routing-modernbert-base-clean-v1">Hugging Face</a>.
</details>

<details><summary><b>📊 Analytics &amp; experiments</b></summary><br/>
CMS / ACHP capstone (top-3 team school-wide, presented to the client): merged four CMS datasets into ~109,015 plan-county records, caught a 12x enrollment overcount, quantified cost-shift with OLS + HC3 robust SEs (premium ~+$2.8, MOOP ~+$97, p&lt;0.001), delivered Tableau dashboards that informed national policy advocacy. Competitions: <a href="https://github.com/shubhamjoshipromail-svg/bank-marketing-ml">7th of 59 solo, ROC-AUC 0.8285</a> and <a href="https://github.com/shubhamjoshipromail-svg/property-automl-hackathon">MAE 8.708, 19th</a>. Plus an honest <a href="https://github.com/shubhamjoshipromail-svg/dating-agent-rl">tabular RL learning project</a>.
</details>

## Beyond the code

I co-founded and lead <b>BAAIO</b> (~100 members), the student AI organization at Johns Hopkins Carey. We run hands-on workshops, a buildathon, and <b>Brain Bank</b>, our weekly deep-dive on advanced AI &#215; business. Before AI, I ran a web &amp; marketing studio in Japan and taught English. I work in four languages (English, Japanese, Nepali, Hindi) and have a habit of making complex things approachable.

Currently exploring: eval harnesses for agent systems, and what forward-deployed AI engineering should look like in regulated industries.

<p align="center"><i>Fastest way to reach me: <a href="mailto:shubhamjoshipro.mail@gmail.com">shubhamjoshipro.mail@gmail.com</a> &#183; <a href="https://www.linkedin.com/in/shubham-joshi1/">LinkedIn</a></i></p>
