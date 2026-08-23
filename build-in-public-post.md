# Build in Public: The AI Risk Register Generator

*Part of my FlyRank AI Fluency internship (Week 8).*

Manually classifying AI systems under the EU AI Act's risk tiers takes too long for busy compliance teams — and it's easy to miss an obligation buried somewhere in the regulation's text. That was the problem I set out to solve.

**What I built:** a Python tool (originally wrapped in a Streamlit web app) that asks structured yes/no questions about how an AI system is used — does it fall under a prohibited use, does it operate in a high-risk domain like employment or credit, does it interact directly with users in a way that could deceive them — and maps the answers to the correct EU AI Act risk tier, plus the specific mitigations that tier requires.

**One real decision:** I chose a structured decision-tree format over a free-text or open-ended chat interface. Compliance classification needs to be defensible and repeatable — if two people run the same system through the tool, they should get the same tier and the same mitigations, every time. A conversational format would have been faster to build and more flexible, but it also would have made the output harder to trust and harder to audit. I traded flexibility for consistency on purpose.

**Example run:** classifying a sample AI-powered resume-screening tool, the system flagged it as **High Risk** (used in the employment domain) and automatically listed the four required mitigations: a conformity assessment, technical documentation, a risk management system with human oversight and override capability, and activity logging for auditability.

**One real limitation:** the tool only classifies based on how I've told it a system is used — it can't independently verify anything about the system it's classifying. If someone answers the yes/no questions inaccurately (intentionally or not), the tool will confidently produce the wrong tier. It's a structured thinking aid, not an audit — the person using it still needs to actually know their system.

**What it replaces:** a manual read-through of the regulation. Instead, someone can run a ~2-minute interactive session and get the exact list of compliance obligations a system needs, without needing to be a policy expert first.

**A demo, live:**

[Watch the walkthrough](https://youtu.be/h-XIegYmY-s) *(replace with the portfolio site video link once uploaded)*

---

Part of the [FlyRank AI Fluency internship](https://github.com/itretzehra-max/flyrank-project). Full write-up and other case studies: [itretzehra-max.github.io](https://itretzehra-max.github.io/)
