# Health Insurance Claim First-Response AI Agent

> Evaluation, failure analysis, and deployment economics for an AI health insurance claim agent.

## Overview

This project was developed as a team project for NTU's Emerging AI Technologies course.

The system addresses the **first-response stage of health insurance claims**. Given claim information such as member details, hospital, service date, and line items, a single-agent ReAct workflow dynamically queries relevant records and determines whether to:

- approve the claim in principle,
- request specific missing documentation, or
- escalate the case to a human assessor.

The project focuses not only on whether the agent can make the correct decision, but also on whether it can do so **reliably, efficiently, and at a reasonable deployment cost**.

---

## Team Scope

As a team, we worked on:

- designing a single-agent ReAct workflow for claim first-response decisions,
- implementing tool-based checks for policy, coverage, pre-authorisation, duplicate claims, and other claim conditions,
- building an evaluation benchmark with normal and difficult / boundary cases,
- comparing multiple live LLMs under the same evaluation setup,
- analysing failure modes and guardrail behaviour,
- measuring token usage, workflow efficiency, and deployment cost.

---

## My Contribution

My work focused primarily on **evaluation and deployment economics**.

### 1. Evaluation Design

- Designed **6 boundary / limit cases** within the team's **50-case evaluation benchmark**.
- Focused on difficult policy, coverage, duplicate-claim, and pre-authorisation conditions.
- Participated in cross-review and live-model evaluation.
- Used evaluation results to analyse model reliability beyond simple average accuracy.

### 2. Model & Failure Analysis

I contributed to evaluating model behaviour across different claim scenarios and analysing where models failed or became unreliable.

The evaluation considered:

- task success,
- boundary-case behaviour,
- incorrect escalation or approval,
- repeated or inefficient tool usage,
- model consistency,
- human fallback requirements.

A key lesson from the project was that **pass rate alone is not sufficient**. An agent may still reach a correct final answer while using an inefficient or unstable reasoning path.

---

## Deployment Economics

I built a **three-layer AI cost model and token / cost ledger** to connect model performance with real deployment economics.

The framework considers:

1. **Model inference cost**
2. **Workflow / token cost**
3. **Human fallback cost**

I also designed four categories of cost optimisation levers and conducted:

- sensitivity analysis,
- break-even analysis,
- model quality vs. cost comparison,
- monthly deployment cost modelling.

Under the assignment assumptions of **8,000 claims per month**, the modeled monthly handling cost decreased from approximately:

**US$44.9K → US$2.3K (-94.8%)**

when moving from a weaker model configuration to the strongest cost-quality configuration.

> Note: These figures are modeled estimates under assignment assumptions, not realised savings from a production insurance company.

---

## Product Perspective

This project changed how I think about AI product evaluation.

For an AI agent, the question is not simply:

> "Which model is the most accurate?"

A deployment decision also needs to consider:

- What happens when the model fails?
- How much human review is required?
- How expensive are repeated tool calls?
- Are the agent's workflows stable?
- Does a more expensive model reduce downstream operational cost?
- Which failures require guardrails rather than better prompting?

This led me to evaluate the system across:

**Quality × Reliability × Cost × Human Fallback × Deployment Scale**

rather than model accuracy in isolation.

---

## Key Takeaways

- Evaluation datasets should deliberately include difficult boundary cases, not only typical user flows.
- Agent quality should be measured at both the **final-answer level** and the **workflow level**.
- Token optimisation matters, but human fallback cost can dominate deployment economics.
- A cheaper model is not always cheaper at the system level if it creates more failures.
- AI product decisions require balancing model quality, cost, safety, and operational constraints.

---

## Team Demo

A team product demo is available here:

**[Watch the Team Demo](https://www.youtube.com/watch?v=BoABxRL6Eu0)**

My contribution shown in this project focused on **evaluation design, model analysis, AI cost modelling, and deployment economics**.

---

## Original Team Repository

This case study documents my individual contribution to a collaborative team project.

Original team repository:

**[Lapis0x0/pe6201-claims-agent](https://github.com/Lapis0x0/pe6201-claims-agent)**

---

## Topics

`AI Agents` · `LLM Evaluation` · `ReAct` · `Failure Analysis` · `AI Product` · `Cost Modeling` · `Human-in-the-Loop` · `Deployment Economics`

---

## Author

**Liu Weiqi**  
MSc in Artificial Intelligence for Enterprise @ NTU Singapore

[LinkedIn](https://www.linkedin.com/in/liu-weiqi/)
