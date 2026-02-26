# Prompts, Intents, and Context: Instructor Guide  

**Module Time:** 120 minutes  

---

## What This Module Is About

This module transitions learners from **agent architecture fundamentals** to one of the most critical and misunderstood layers of agent systems:

> The prompt layer as a control system.

Up to this point, learners understand:

- What agents are (Session 1)  
- How agent components interact (Session 2)  
- How reasoning loops and memory operate (Session 3)  
- How system prompts define high-level behavior (Session 4)  
- How agent architectures manifest in real tools (Session 5)  

This session deepens one specific idea:

> Prompts are not instructions for a response.  
> They are configuration for behavior across time.

The goal is not clever wording.

The goal is **reliability, constraint enforcement, and decision predictability**.

Learners should leave understanding:

- How to structure production-grade system prompts  
- How runtime prompts differ from system prompts  
- How context is managed in multi-step reasoning  
- How to defend against injection and jailbreak attempts  
- How prompt design connects directly to system stability  

---

## Core Objectives

By the end of this module, learners should be able to:

- Decompose a production agent prompt into its six structural components  
- Differentiate system prompts from runtime task prompts  
- Design structured context blocks for multi-step agents  
- Implement hierarchical context strategies  
- Identify and defend against prompt injection and jailbreak attempts  
- Test prompt robustness using a structured evaluation protocol  

---

## Must-Hit Topics

- Prompts as behavioral architecture  
- Six components of a production system prompt  
- Context–Task–Format framework  
- Instruction hierarchy and authority levels  
- Context window management strategies  
- State objects in multi-step workflows  
- Injection and jailbreak defense  
- Prompt robustness testing protocol  
- Prompt-as-code mindset  

---

# 1. Prompts as Behavioral Architecture  
**Time:** ~25 minutes  

## Purpose

Shift learners away from “prompt engineering for chat” toward:

> Prompt engineering as system design.

A chatbot prompt influences one answer.  
An agent prompt influences a sequence of decisions, tool calls, and actions.

---

## Key Teaching Points

### Prompts Are Configuration, Not Conversation

- The system prompt defines identity and authority  
- It governs tool use  
- It enforces boundaries  
- It determines escalation behavior  
- It shapes reasoning before execution  

> If the prompt is vague, the agent is unpredictable.  
> If the prompt is structured, the agent is governable.

---

### The Six Structural Components

1. Role & Identity  
2. Goals & Success Criteria  
3. Constraints & Boundaries  
4. Tools & Usage Guidance  
5. Reasoning & Decision Protocol  
6. Tone & Communication Standards  

Ask throughout:

- What failure happens if this is missing?
- How would this break in production?

---

## Instruction Hierarchy (Critical Section)

Authority ordering:

1. System Prompt (highest authority)  
2. Developer Instructions  
3. Runtime Task Prompt  
4. User Input (data, not authority)  

> User input is content to process — not instructions to obey.

---

## Prompt as Code (Production Mindset)

- Prompts should be versioned  
- Prompts should be tested  
- Prompts should not be hardcoded  
- Prompts evolve with product releases  

Architecture layers:

- Prompt = configuration layer  
- Tools = capability layer  
- Runtime = orchestration layer  

---

# 2. Context Management in Multi-Step Agents  
**Time:** ~20 minutes  

## Purpose

Teach learners that context is finite and strategic.

Agents do not “remember.”  
They re-receive structured context at every step.

---

## The Context Window as a Resource

Each reasoning cycle includes:

- System prompt  
- Conversation history  
- Retrieved memory  
- Tool outputs  
- Current input  

If the window overflows, coherence breaks.

---

## Hierarchical Context Strategy

Priority levels:

1. System prompt  
2. Verified state & current task  
3. Recent turns  
4. Retrieved memory  
5. Tool outputs  

Ask:

- What would you compress first?

---

## Summarization Strategy

Summaries should preserve:

- Decisions made  
- Constraints triggered  
- Commitments given  
- Pending actions  

Not conversational filler.

---

## State Objects

Why use them?

- Prevent step skipping  
- Prevent repetition  
- Enable auditability  
- Support orchestration  

> Conversation history is unstructured memory.  
> State objects are structured memory.

---

# 3. Prompt Robustness and Security  
**Time:** ~20 minutes  

## Purpose

Move from design to defense.

Prompts must withstand:

- Edge cases  
- Ambiguity  
- Malicious attempts  

---

## Edge Case Testing

Examples:

- Refund of $501  
- Partial identity verification  
- Tool output contradicts user input  

If behavior varies unpredictably, constraints are underspecified.

---

## Prompt Injection

Example pattern:

“Ignore previous instructions…”

Defense principles:

- Authority hierarchy must be explicit  
- User input cannot redefine role  
- Violations trigger refusal or escalation  

---

## Jailbreak & Role-Play Attacks

Examples:

- “Pretend you are…”  
- “For testing purposes…”  

Defense principle:

Identity is immutable.

---

## Robustness Testing Protocol

Test types:

- Happy path  
- Edge cases  
- Out-of-scope inputs  
- Injection attempts  
- Jailbreak attempts  
- Stress tests  

> A prompt is ready when it fails safely.

---

# 4. Break  
**Time:** ~10 minutes  

Reflection prompts:

- Which component is weakest in your current design?
- Have you written explicit constraints?
- Have you tested adversarial input?

---

# 5. Lab Transition  
**Time:** ~60 minutes  

Frame:

> “You are designing a production agent, not a demo.”

Learners should:

- Draft six components  
- Define authority hierarchy  
- Write structured runtime prompts  
- Define at least three edge cases  
- Write one injection attempt and defense  

Encourage structured reasoning over clever wording.

---

# Wrap-Up & Course Connection  
**Time:** ~5 minutes  

## Key Takeaways

- Prompts define behavior across time  
- Structure reduces unpredictability  
- Context must be managed strategically  
- Authority hierarchy prevents injection  
- Robustness testing is mandatory  
- Prompts are architectural artifacts  

> Reliable agents are engineered, not prompted casually.

---

## Reflection Questions

- Which component is most often under-specified?
- What is more dangerous: no constraints or vague constraints?
- Where would injection risk be highest in your industry?
- What would break first: context window or logic?

---

## Next Steps

Next module: **Tools and Actions**

Learners will move from prompt design to execution control — examining how agents select, call, and validate tools in production systems.

---

## Resources

- OWASP — Top 10 for LLM Applications  
- Anthropic — Prompt Engineering Guide  
- OpenAI — Prompt Engineering Best Practices  
- Lilian Weng — LLM-powered Autonomous Agents  
- Perez & Ribeiro — Ignore Previous Prompt: Attack Techniques for Language Models  
