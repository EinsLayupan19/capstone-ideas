# Capstone Strategy: From "Ordinary CRUD" to Best-in-Batch

A note on scope before we start: your brief asked for ~30 fields across 15 ideas, three full mini-proposals, 30+ defense questions, and a complete technical blueprint — that's genuinely a multi-week planning document. I've kept every section you asked for, but I condensed the field lists for the 15 ideas (full 30-field depth only makes sense once you've picked one) and went deep where it actually matters: the framework, the ranking, the top 3, and the final winner. If you want the full 30-field treatment on any of the other 14 ideas later, just ask and I'll expand it.

---

## PART 1 — What Actually Separates Capstone Tiers

Most panels (explicitly or not) score against something like this:

| Criterion | Weight | Ordinary | Good | Excellent | Award-Winning |
|---|---|---|---|---|---|
| Innovation | 20% | Common template (POS, LMS, inventory) | Familiar idea, one new twist | Underserved problem, genuinely new angle | Problem nobody else in the batch is solving this way |
| Real-world impact | 15% | Hypothetical users | Named user group, vague benefit | Real stakeholder, quantifiable pain point | Could plausibly be piloted with a real organization |
| AI sophistication | 15% | Chatbot wrapper over GPT | One ML model, not evaluated | Model trained/fine-tuned, evaluated with metrics | AI is the reason the system works at all — remove it and there's no product |
| Technical complexity | 10% | Single CRUD stack | CRUD + one integration | Multi-service architecture, real auth/API design | Distributed concerns (AI service + core app + network/security layer) working together |
| Research potential | 10% | No research question | One vague hypothesis | Testable hypothesis, defined metrics | Publishable-quality methodology (dataset, baseline, evaluation protocol) |
| Security | 10% | Login form only | Hashed passwords, basic RBAC | Full RBAC, input validation, encrypted data at rest/in transit | Threat-modeled, audited, OWASP-mapped, pen-tested by the team itself |
| Scalability | 5% | Works for 5 test users | Works for one org | Multi-tenant capable | Designed with real cost/scale ceiling analysis |
| UX | 5% | Bootstrap default | Clean, consistent | Thoughtful, accessible | Feels like a funded startup's product |
| Feasibility | 5% | N/A (too simple to fail) | Achievable, low risk | Achievable, moderate risk, has fallback | Ambitious but has an honest MVP that de-risks the timeline |
| Portfolio value | 5% | Forgettable | "I built a system" | "I built [specific, nameable thing]" | Something you'd screen-share in a job interview unprompted |

**The single biggest tier-separator**: ordinary and good capstones bolt AI onto a system that would work fine without it. Excellent and award-winning capstones fail without their AI component — the AI *is* the value proposition, not a feature checkbox.

The second biggest separator: **which of your specific subjects actually shows up in the build.** Everyone in your batch has "full-stack web dev." Almost nobody will have a system where Network Management and Information Assurance and Security 2 are load-bearing, not decorative. That's your structural advantage — use it.

---

## PART 2 — 15 Elite Capstone Concepts

Condensed format: Title · Problem · AI Approach · Why it's not "just a CRUD with AI on top" · Wow Factor · Difficulty (1–5) · Portfolio Value (1–5).

**1. SentraNet — AI Network Threat & Anomaly Detection Platform**
Real network traffic (simulated lab traffic + public datasets like CICIDS2017/NSL-KDD) is monitored for intrusion patterns. ML classifier (Random Forest / Isolation Forest / lightweight neural net) flags anomalies in real time, auto-generates incident tickets, and visualizes traffic on a live dashboard. Without the ML classifier, this is just a log viewer — the AI *is* the detection. 🔥 Wow: watching the dashboard light up during a live simulated attack in front of the panel. Difficulty 4 · Portfolio 5.

**2. DocuGuard — AI Document Intelligence & Fraud Detection for Academic/Government Records**
OCR + NLP pipeline ingests scanned IDs, transcripts, or certificates; a classifier flags forged/altered documents (tampering artifacts, font mismatches, inconsistent metadata) and extracts structured data automatically. Difficulty 4 · Portfolio 4.

**3. PulseMonitor — Predictive IT Infrastructure Health System**
Time-series forecasting (Prophet/LSTM) predicts server/network resource exhaustion before it happens, using historical CPU/RAM/bandwidth data, with anomaly-triggered auto-alerts. Ties Network Management + AI directly. Difficulty 4 · Portfolio 4.

**4. TutorMind — Adaptive Learning Path Engine for Reviewer/Board-Exam Prep**
Recommendation engine adjusts question difficulty and topic sequencing per student based on performance history (like a lightweight Knewton). Real dataset needed: student response logs. Difficulty 3 · Portfolio 4.

**5. TriageAI — Symptom-to-Urgency Classifier for Barangay Health Centers**
NLP/classification model triages patient-reported symptoms into urgency tiers to help understaffed health centers prioritize. Needs care around medical-claim framing (decision *support*, never diagnosis). Difficulty 4 · Portfolio 5 (high real-world impact).

**6. AgriSense — Crop Disease Detection via Computer Vision**
CNN image classifier (transfer learning on MobileNet/EfficientNet) identifies plant disease from leaf photos, gives treatment recommendations, tracks outbreak patterns geographically. Difficulty 3 · Portfolio 4.

**7. GuardianFeed — AI Content Moderation & Deepfake/Manipulation Detector for Local Media**
Computer vision + metadata forensics flags manipulated images/video shared in community Facebook groups or news pages. Genuinely hard, high-wow, higher risk. Difficulty 5 · Portfolio 5.

**8. SecureVote — Cryptographically-Verifiable Campus Election System with Fraud Anomaly Detection**
Not just e-voting; the AI angle is anomaly detection on voting patterns (impossible timing, ballot-stuffing signatures) layered on top of a cryptographically auditable ledger. Strong IAS2 tie-in. Difficulty 4 · Portfolio 4.

**9. ResQRoute — AI-Optimized Disaster Evacuation & Resource Routing**
Optimization algorithm (Dijkstra/A* + real-time congestion prediction) routes evacuees and relief resources during floods/typhoons using crowd-reported and sensor data. Difficulty 4 · Portfolio 5.

**10. CampusWatch — Multimedia-Based Campus Safety & Incident Detection**
Computer vision on CCTV feeds detects specific safety incidents (fights, unauthorized access, overcrowding) and auto-alerts security with video clips. Heavy multimedia + AI overlap. Privacy/ethics section is mandatory. Difficulty 5 · Portfolio 5.

**11. FinGuard — Transaction Anomaly Detection for Student Org/Cooperative Finance**
Unsupervised anomaly detection (Isolation Forest/Autoencoder) flags suspicious transactions in a small finance system, with full audit trail. Difficulty 3 · Portfolio 3.

**12. SkillGraph — AI-Powered Resume-to-Job-Market Gap Analyzer**
NLP extracts skills from resumes/transcripts, compares against real job postings (scraped/API), visualizes skill gaps and recommends learning paths. Strong tie to your own career-roadmap interest. Difficulty 3 · Portfolio 4.

**13. NetGuardian — IoT Device Anomaly & Rogue Device Detection for Small Networks**
Monitors devices on a LAN, fingerprints normal behavior per device, flags rogue/unauthorized devices or unusual traffic — a scoped-down version of enterprise NAC. Difficulty 4 · Portfolio 4.

**14. MediaForensics — Multimedia Authenticity Verification Toolkit**
Given an uploaded image/video/audio clip, the system runs multiple forensic checks (ELA, metadata, compression artifacts) and an ML classifier estimates manipulation likelihood, with an explainable report. Difficulty 4 · Portfolio 4.

**15. LogSense — AI-Powered Security Log Correlation & Incident Response Assistant**
Ingests logs from multiple sources (firewall, auth, app), correlates events an analyst would miss, uses anomaly detection + rule-based reasoning to propose incident response playbooks. Difficulty 5 · Portfolio 5.

---

## PART 3 — Wow Factors at a Glance

| # | 🧠 AI Wow | 🔐 Security Wow | 📊 Analytics Wow | ⚙️ Automation Wow | 🎨 UX Wow |
|---|---|---|---|---|---|
| 1 SentraNet | Live traffic classified in real time | IDS is itself the security core | Live attack-map dashboard | Auto-ticketing on detection | Terminal-meets-SOC aesthetic |
| 9 ResQRoute | Route optimization under live constraints | N/A | Live evacuation heatmap | Auto-reroute on new data | Map-first, high visual drama |
| 10 CampusWatch | Real-time video incident detection | Access control + privacy-by-design | Incident timeline | Auto-alert with clip | Live camera grid |
| 15 LogSense | Cross-source correlation panel can't do by hand | Full SOC-analyst simulation | Correlated incident graph | Auto-generated response playbook | Analyst console feel |

---

## PART 4 — Ranking (1–100)

| Rank | Project | Score | Why |
|---|---|---|---|
| 1 | **SentraNet** (Network Threat Detection) | **91** | Perfectly maps to 3 of your 4 core subjects (Network Mgmt, IAS2, AI); AI is structurally load-bearing; real, well-known public datasets exist so data isn't a blocker; feasible as a BSIT team project; extremely portfolio-relevant for PH's growing cybersecurity job market |
| 2 | LogSense | 88 | Similar strengths to #1, slightly harder to scope an achievable MVP, log correlation logic is trickier to make genuinely "AI" vs rule-based |
| 3 | ResQRoute | 85 | Huge real-world impact (PH = disaster-prone), strong optimization component, but weaker IAS2/Network tie-in and harder to get real data |
| 4 | CampusWatch | 83 | Very high wow factor, but highest technical difficulty, real privacy/ethics exposure the panel will grill hard, CV pipeline is the riskiest to get working reliably in time |
| 5 | DocuGuard | 80 | Strong AI (OCR+NLP+classification), real problem, but weaker Network Management tie-in |
| 6 | NetGuardian | 78 |
| 7 | TriageAI | 77 |
| 8 | GuardianFeed | 76 |
| 9 | SecureVote | 74 |
| 10 | PulseMonitor | 73 |
| 11 | MediaForensics | 72 |
| 12 | AgriSense | 68 |
| 13 | SkillGraph | 65 |
| 14 | TutorMind | 63 |
| 15 | FinGuard | 58 |

**Why the top 5 lead the pack**: all five make AI the mechanism, not the garnish; all five map to at least two of your four specialized subjects (most BSIT teams will only leverage web dev); and all five have a "moment" — something visibly happening on screen during defense (an attack detected, a route recalculated, an incident flagged) rather than a static report generated after the fact. Panels remember *moments*, not feature lists.

---

## PART 5 — Top 3 Mini Proposals

### 🥇 1. SentraNet — AI-Powered Network Intrusion Detection & Response Platform

- **Problem**: Small orgs/schools/SMEs in the Philippines can't afford enterprise IDS (Cisco Secure, Darktrace); they rely on basic firewalls with no behavioral detection, so novel attacks go unnoticed until damage is done.
- **General objective**: Design and evaluate an AI-based network intrusion detection and automated response system deployable on commodity hardware.
- **Specific objectives**:
  1. Build a real-time packet/flow capture pipeline (e.g., via Zeek/Suricata or custom pcap parsing)
  2. Train and evaluate an anomaly/intrusion classifier on a public IDS dataset (CICIDS2017 or NSL-KDD) plus lab-captured traffic
  3. Achieve a target detection accuracy/F1-score (e.g., ≥90% on held-out test data)
  4. Build a live dashboard visualizing traffic, threats, and severity
  5. Implement automated incident ticketing and email/Slack alerting on detection
  6. Implement full RBAC (admin/analyst/viewer) with audit logging
  7. Benchmark system performance under simulated load (packets/sec it can sustain)
  8. Conduct a usability evaluation with IT-staff test users
- **Target users**: School/SME IT admins and security analysts.
- **Core features**: live traffic dashboard, ML-based threat classification, severity scoring, auto-ticketing, alerting, historical incident log, RBAC, audit trail.
- **AI architecture**: Feature-extracted flow data (packet size, duration, protocol, byte counts, etc.) → trained classifier (start with Random Forest/XGBoost for explainability and speed; optionally compare against a small neural net) → confidence-scored classification (benign/attack-type) → rule layer decides auto-ticket vs. human review for low-confidence cases.
- **Security architecture**: JWT auth, bcrypt/argon2 password hashing, RBAC, encrypted DB fields for sensitive data, TLS everywhere, input validation on all API endpoints, rate limiting on auth routes, full audit log of analyst actions.
- **Network architecture**: A monitored segment/VLAN (can be a lab VM network) mirrored into the capture pipeline; system itself is out-of-band (doesn't sit inline, so it can't take the network down if it fails — important to say in defense).
- **Research methodology**: Quantitative — train/test split on IDS dataset, precision/recall/F1/ROC-AUC as metrics, compare 2–3 model choices, statistical comparison of results; qualitative — usability survey (SUS score) from test analysts.

### 🥈 2. LogSense — AI Security Log Correlation & Incident Response Assistant

- **Problem**: Analysts drowning in disconnected logs (auth, firewall, app) miss multi-stage attacks because no single log shows the full picture.
- **Core AI move**: Correlate events across log sources within a time window using a graph/sequence model or rule-augmented anomaly scoring, then auto-draft a response playbook using a retrieval-based approach (matching incident signatures to known response templates — not a black-box chatbot).
- **Why #2 not #1**: harder to make an honestly "AI" (not just clever SQL joins) correlation engine defensible under panel scrutiny in one capstone cycle; SentraNet's classifier has a cleaner, better-documented research path.

### 🥉 3. ResQRoute — AI-Optimized Disaster Evacuation & Resource Routing

- **Problem**: During PH floods/typhoons, evacuation routing is manual and slow; responders don't have live optimized routing accounting for road status and congestion.
- **Core AI move**: Route optimization (Dijkstra/A* baseline, optionally reinforcement-learning-lite for adaptive rerouting) reacting to crowd-reported road blockages.
- **Why #3 not higher**: weakest tie to your IAS2/Network Management subjects; real-time road-status data is harder to source authentically than public IDS datasets.

---

## PART 6 — As Real Products

| | **SentraNet** | **LogSense** | **ResQRoute** |
|---|---|---|---|
| Tagline | "See the attack before it becomes a breach." | "One console. Every log. The full story." | "Every second counts. Route smarter." |
| Target market | PH SMEs, schools, coops without enterprise security budgets | Understaffed SOC teams, MSSPs serving small clients | LGUs, DRRM offices, NGOs |
| USP | Enterprise-grade detection at commodity-hardware cost | Cross-source correlation without SIEM licensing costs | Adaptive routing using crowd + sensor data together |
| Real deployment | Pilot with your university's own network (with IT office sign-off) or a partner SME | Pilot with a school IT office's log sources | Pilot with a barangay DRRM office using simulated drill data |
| Scaling to 1000s of users | Multi-tenant SaaS, per-org isolated model + shared threat-intel feed | Same multi-tenant pattern | Horizontal scaling of routing service, cached map tiles |
| AI cost control | Classical ML (RF/XGBoost) runs cheaply on CPU — no per-token LLM cost | Same — avoid LLM API calls for the core detection loop, reserve any LLM use for playbook text generation only | Classical optimization, no LLM needed at all |
| Post-graduation maintenance | Dockerized deployment, documented retraining pipeline, README runbook | Same | Same |

---

## PART 7 — 🏆 The Final Winner: SentraNet

I'm applying the "would this actually contend for best-in-batch" test honestly: **yes** — because it (1) cannot be faked with a chatbot wrapper, (2) has a public, reputable dataset so you're not blocked on data collection, (3) structurally uses three of your four specialized subjects, and (4) has a natural live demo moment. The main honest risk is scope — intrusion detection is a real research area, so the team must ruthlessly protect the MVP (see Part 15) rather than chasing a "full SOC platform."

- 🔥 **Product name**: **SentraNet**
- 💡 **One-line pitch**: "An AI system that watches your network the way a senior security analyst would — and never sleeps."
- 🎯 **Problem**: Small organizations can't afford enterprise intrusion detection, so they're blind to attacks until it's too late.
- 💎 **Unique solution**: A lightweight, self-hostable ML-based IDS with live dashboards and automated incident response, built for orgs that would otherwise have *nothing*.
- 🤖 **AI component**: Supervised classifier (Random Forest/XGBoost baseline) trained on labeled network flow data, detecting and categorizing intrusion types with confidence scores.
- 🔐 **Security component**: The system doesn't just *have* security — detecting threats *is* its function; plus standard hardening (RBAC, encryption, audit logs) on the platform itself.
- 🌐 **Network component**: Packet/flow capture, VLAN mirroring, out-of-band monitoring architecture.
- ⚙️ **Automation component**: Auto-ticketing, auto-alerting, auto-severity scoring.
- 📊 **Analytics component**: Live threat dashboard, historical trend charts, model performance metrics visible to admins.
- 🎨 **UI/UX component**: SOC-style dark dashboard, real-time updating charts, clear severity color-coding.

---

## PART 8 — Technical Blueprint

**Frontend**: React (Vite) + Tailwind, Recharts/D3 for live dashboard, WebSocket connection for real-time updates.

**Backend**: Node.js/Express (or FastAPI if the team is more comfortable in Python — recommended since it keeps the AI service and API in one language) exposing REST + WebSocket endpoints.

**AI service**: Python microservice (FastAPI) hosting the trained scikit-learn/XGBoost model; exposes a `/predict` endpoint the backend calls per flow batch. Keeping this as a separate service (not baked into the main API) is itself a nice architecture talking point — "AI as a service" is a legitimate, defensible design pattern.

**Database**: PostgreSQL (Supabase free tier is a realistic student-friendly choice) for structured data — users, incidents, audit logs; optionally a time-series table (or TimescaleDB extension) for traffic metrics.

**Auth**: JWT-based, bcrypt/argon2 hashing, refresh-token rotation.

**Cloud infra**: Backend + AI service on a free/student tier (Render, Railway, or a university-provided VM); frontend on Vercel; capture pipeline runs on a lab machine/VM you control (this is realistic — you're not expected to monitor a real ISP network).

**File storage**: Supabase Storage or S3-compatible bucket for exported incident reports/PCAP samples.

**Notifications**: Email (Resend/SendGrid free tier) + optional Slack webhook for alerts.

**Logging/monitoring**: Structured JSON logs (Winston/Loguru), a simple self-hosted status page or just clear log files — don't over-engineer this part, it's not the star of the show.

**Security**: TLS via hosting provider, input validation (Zod/Pydantic), rate limiting on auth endpoints, RBAC middleware, parameterized queries (ORM) to prevent injection.

---

## PART 9 — AI Architecture in Detail

- **Input data**: Network flow features — duration, protocol, packet counts, byte counts, flag counts, etc. (the standard NSL-KDD/CICIDS2017 feature set), captured from your lab network plus the public dataset for training volume.
- **Processing**: Feature normalization/scaling, categorical encoding, class imbalance handling (attacks are rarer than benign traffic — use class weighting or SMOTE).
- **Model**: Random Forest or XGBoost as the primary model — chosen deliberately over a deep neural net because (a) it's explainable (you can show feature importances to the panel), (b) it trains fast on modest hardware, (c) tabular flow data doesn't need deep learning to perform well. This is a defensible, non-hype choice — say so explicitly in defense.
- **Output**: Classification (benign / attack-type) + confidence score.
- **How the result is used**: Confidence above threshold → auto-ticket + alert; below threshold → flagged for analyst review, never silently dropped.
- **Accuracy measurement**: Precision, recall, F1 per attack class (not just overall accuracy, which is misleading on imbalanced data), plus ROC-AUC.
- **False positive/negative handling**: Tunable threshold, analyst feedback loop that can relabel and feed back into retraining.
- **Human-in-the-loop**: Nothing auto-blocks traffic — the system detects and alerts, a human decides response. This is both an honest scope choice and a good answer to "what if the AI is wrong?"
- **Privacy**: Only flow metadata is analyzed, not packet payload/content — say this explicitly, it preempts a privacy question.
- **Improvement over time**: Periodic retraining pipeline using newly labeled incidents from analyst feedback.

---

## PART 10 — Security Design

| Threat | Mitigation |
|---|---|
| Credential stuffing / brute force | Rate limiting, account lockout, bcrypt/argon2 hashing |
| SQL/NoSQL injection | ORM with parameterized queries, input validation |
| Broken access control | RBAC enforced server-side on every endpoint, not just hidden in UI |
| Session hijacking | Short-lived JWTs, refresh token rotation, HttpOnly cookies |
| Data exposure in transit | TLS everywhere |
| Data exposure at rest | Encrypted sensitive fields, hashed passwords |
| Insecure API design | Versioned REST API, strict schema validation, no verbose error leakage |
| Insufficient logging | Full audit log of analyst actions and system decisions (who acknowledged which incident, when) |
| Model poisoning (AI-specific threat) | Training data provenance tracked; retraining requires admin approval, not fully automatic |
| Denial of service on capture pipeline | Out-of-band mirrored capture — pipeline failure doesn't take down the actual network |

Map explicitly to OWASP Top 10 in your documentation (A01 Broken Access Control, A02 Cryptographic Failures, A03 Injection, A07 Auth Failures, etc.) — panels in IAS-heavy programs specifically look for this mapping.

---

## PART 11 — Networking Component

Fully legitimate here, not forced: packet/flow capture, VLAN-mirrored monitoring, out-of-band architecture, traffic analysis, anomaly detection on network behavior, uptime/health monitoring of the capture agent itself. This is the rare capstone where Network Management isn't decorative.

## PART 12 — Multimedia Component

Honest answer: multimedia is a **secondary** contributor here, not core — and that's fine to say to the panel. Its legitimate role: the live dashboard's data visualizations (charts, network topology maps, severity heatmaps) *are* a multimedia/interactive-visualization deliverable, and an optional exported incident report (PDF/video walkthrough of an incident) satisfies Multimedia Systems without forcing video/audio processing where it doesn't belong.

---

## PART 13 — Research Design

- **Research problem**: Can a lightweight ML classifier provide enterprise-comparable intrusion detection accuracy on commodity hardware for resource-constrained organizations?
- **Research questions**: (1) What detection accuracy/F1 can be achieved on flow-based features using classical ML vs. a baseline deep model? (2) How does detection latency scale with traffic volume? (3) Do analysts using the dashboard resolve incidents faster than with manual log review?
- **Variables**: Independent — model type, feature set; Dependent — F1/precision/recall, detection latency, analyst time-to-resolution.
- **Hypotheses**: H1 — the trained classifier achieves ≥90% F1 on held-out test data. H2 — dashboard-assisted analysts resolve simulated incidents faster than a manual-log control group.
- **Data collection**: Public IDS dataset (train/test split) + lab-generated traffic (benign + simulated attacks via tools like hping3/Nmap in a controlled VM).
- **Testing methodology**: Standard ML train/validation/test split, k-fold cross-validation for robustness.
- **User evaluation**: SUS (System Usability Scale) survey with test analysts (classmates/faculty acting as analysts).
- **AI evaluation**: Confusion matrix, per-class F1, ROC-AUC, comparison across 2–3 candidate models.
- **System performance evaluation**: Load testing (sustained flows/sec before degradation).
- **Security evaluation**: Basic penetration test checklist against your own platform (not the detection engine) — auth bypass attempts, injection attempts, documented and mitigated.

---

## PART 14 — Panel Defense: 30+ Questions & Strong Answers

**Why this project**
1. *Why this project over a normal system?* — Small PH organizations have zero affordable options between "nothing" and enterprise IDS pricing; we're filling that specific gap.
2. *What's novel here — hasn't intrusion detection existed for decades?* — The detection approach isn't novel research; the novelty is making it accessible and self-hostable for orgs that currently have nothing, with a UX enterprise tools don't prioritize.
3. *Who is your actual target user?* — School/SME IT admins without a dedicated security team.

**Why AI / why this algorithm**
4. *Why not a deep neural network?* — Tabular flow data doesn't benefit much from deep learning; RF/XGBoost is faster to train, explainable, and appropriate for our data volume and hardware.
5. *Why is this "real" AI and not just if-statements?* — The model learns decision boundaries from data rather than hand-coded thresholds, and generalizes to attack patterns not explicitly programmed.
6. *How did you choose your features?* — Standard flow-based features from established IDS research (NSL-KDD/CICIDS2017 feature set), validated against feature-importance analysis from the trained model.

**Data**
7. *Where does your data come from?* — Public benchmark datasets plus lab-generated traffic from controlled VM simulations.
8. *Is your data representative of real attacks?* — Partially — benchmark datasets are widely used in IDS research precisely because they cover established attack signatures; we're explicit this isn't zero-day detection.
9. *How much data did you use, and was it balanced?* — [fill in with actual numbers]; class imbalance handled via weighting/resampling.

**AI accuracy & failure**
10. *How accurate is the model?* — Report actual F1/precision/recall per class from your evaluation.
11. *What happens when the AI is wrong?* — Low-confidence predictions route to human review rather than auto-closing; nothing auto-blocks traffic.
12. *How do you handle false positives in production?* — Threshold tuning + analyst feedback loop retrains the model.
13. *What's your model's biggest weakness?* — Novel/zero-day attack types outside the training distribution — be upfront about this limitation.

**Security**
14. *How do you secure the platform itself, separate from what it detects?* — Full RBAC, hashed passwords, TLS, input validation, audit logging (walk through Part 10).
15. *What if someone attacks SentraNet itself?* — Out-of-band architecture means compromising the monitoring platform doesn't compromise the monitored network; platform has its own hardening independent of the detection engine.
16. *How do you prevent model poisoning?* — Retraining requires admin approval; training data provenance is tracked.

**Privacy**
17. *Are you inspecting private data/packet contents?* — No — only flow metadata (sizes, timing, protocol), not payload content.
18. *How is stored incident data protected?* — Encrypted sensitive fields, RBAC-gated access, audit trail of who viewed what.

**Scalability & cost**
19. *Can this scale beyond one network?* — Yes, multi-tenant architecture with per-org isolated capture agents reporting to a shared backend.
20. *What does this cost to run?* — Classical ML has near-zero inference cost on CPU; main costs are hosting (student-tier free/cheap) — no per-request LLM API costs.
21. *How would this actually get deployed in a real org?* — Docker-packaged capture agent + backend, deployable on a spare machine or small VM.

**Network architecture**
22. *Why out-of-band instead of inline?* — Inline monitoring risks becoming a single point of failure for the whole network; out-of-band keeps the network functional even if SentraNet goes down.
23. *How do you capture traffic without disrupting the network?* — Port mirroring / SPAN port or a tap, standard non-invasive technique.

**Database design**
24. *Why PostgreSQL over NoSQL?* — Structured, relational data (users, incidents, audit logs) benefits from relational integrity and RBAC-friendly querying.
25. *How do you handle high-volume flow data over time?* — Time-series-oriented table design / optional TimescaleDB extension, with retention/aggregation policy for older data.

**Feasibility**
26. *Can a BSIT team actually build this in one capstone cycle?* — Yes, with a disciplined MVP (Part 15) — the core classifier + dashboard + alerting is achievable; advanced correlation/auto-response is deferred to V2/V3.
27. *What's the biggest technical risk?* — Getting reliable real-time capture and classification latency low enough to feel "live" in a demo.

**Existing alternatives**
28. *How is this different from Snort/Suricata/Zeek?* — Those are excellent rule-based/signature engines; SentraNet's differentiator is the ML-based behavioral layer plus an accessible dashboard/response workflow layered on top, not a rule-signature replacement.
29. *Why not just use an existing open-source IDS?* — We do use capture tooling from that ecosystem where appropriate — our contribution is the applied ML classification layer, dashboard, and response automation built around it.

**Research methodology**
30. *How do you know your results are statistically meaningful?* — k-fold cross-validation, reporting per-class metrics (not just accuracy) on a held-out test set, avoiding data leakage between train/test.
31. *What's your baseline for comparison?* — Compare your trained model against a simple rule-based/threshold baseline to demonstrate the ML approach's added value.

---

## PART 15 — MVP vs. Advanced Versions

**MVP (must work for defense)**
- Flow capture from lab traffic (real or simulated)
- Trained classifier with reported evaluation metrics
- Live dashboard showing traffic + flagged incidents
- Basic RBAC (admin/analyst)
- Auto-ticket creation on detection
- Basic audit log

**Version 2 (impressive additions)**
- Email/Slack alerting
- Analyst feedback loop that improves the model
- Historical trend analytics (attack types over time)
- Multi-tenant support (more than one monitored network)

**Version 3 (stretch, if time allows)**
- Auto-suggested response playbooks
- Second dataset/network comparison for generalization testing
- Basic pentest report on the platform itself, written up formally
- Exportable PDF incident reports

---

## PART 16 — Final Verdict

🏆 **Best Capstone Project: SentraNet — AI-Powered Network Intrusion Detection & Response Platform**

⭐ **Score: 91/100**

🔥 **Why it could be one of the best**: it's the rare project where four separate subjects (AI, Network Management, IAS2, and web dev) are all structurally necessary — nobody else in your batch will have that combination, and none of it is decorative.

💡 **What makes it unique**: accessible, self-hostable intrusion detection for organizations priced out of enterprise security tooling — a real, nameable gap.

🤖 **Why the AI is meaningful**: remove the classifier and there is no detection system left — it's not an add-on, it's the mechanism.

🔐 **Why the security is impressive**: the system's *purpose* is security, and it's also hardened as a platform — two layers of security story to tell the panel.

🌐 **Why the architecture is impressive**: out-of-band network capture, a separate AI microservice, and a real-time dashboard is genuine multi-service system design, not a single-stack CRUD app.

📊 **How you'll prove it works**: reported F1/precision/recall on held-out test data, load testing for latency under traffic volume, and a usability survey from test analysts.

🎤 **60-second pitch**: "Small organizations across the Philippines run their networks with nothing more than a basic firewall — no behavioral threat detection, because enterprise IDS tools are priced for banks and telcos, not schools and SMEs. SentraNet is a self-hostable, AI-powered intrusion detection platform: it watches network traffic in real time, uses a trained machine learning classifier to flag anomalous behavior with over [X]% accuracy on benchmark data, and automatically raises incidents on a live analyst dashboard — giving small organizations the kind of visibility that used to require an enterprise security budget."

🚨 **Biggest risks**: (1) real-time capture-to-classification latency being too slow for a convincing live demo; (2) model accuracy underwhelming if the dataset/feature engineering isn't done carefully; (3) scope creep toward a "full SOC platform" that isn't achievable in one cycle.

🛠️ **Risk reduction**: build the offline classifier and prove its metrics *first* (this de-risks the research core early), only then build the real-time pipeline around it; protect the MVP list ruthlessly; have a pre-recorded backup demo video in case live capture misbehaves during defense.

📅 **Roadmap**
- **Capstone 1**: Problem validation, literature review, dataset selection, offline model training + evaluation (this is your strongest research deliverable — get it done early), initial system architecture and Chapter 1–3 documentation.
- **Capstone 2**: Build the real-time capture pipeline, backend API, dashboard, RBAC, auto-ticketing/alerting; integrate the trained model as a live service; usability testing with analysts.
- **Final Defense**: Polish dashboard UX, finalize evaluation metrics and load testing results, rehearse the live-attack demo (with backup video), tighten documentation against the OWASP/RBAC/audit-log talking points above.

**Final recommendation, honestly**: SentraNet is the strongest fit not because intrusion detection is exotic — it isn't — but because it's the one idea on this list where your specific subject combination gives you a real, defensible advantage over the rest of your batch, the data problem is already solved by public benchmarks, and the "AI actually matters" test passes without any argument. Pick it, and protect the MVP scope hard — the risk isn't that the idea is weak, it's that a team tries to build the SOC platform instead of the capstone.
