---
title: "Ask: Why Do Specs Matter NOW? The AI Moment"
chapter: 30
lesson: 5
duration: "2.5-3 hours"
---

# Ask: Why Do Specs Matter NOW? The AI Moment

## The Question

Specifications have existed since the 1970s. **Why is SDD only becoming standard practice NOW, in 2024?**

If specs were so good, why didn't everyone use them 20 years ago?

**Ask your companion this exact question:**

```
Specifications have been around for decades (formal methods in 1970s,
Model-Driven Development in 2000s). But SDD is only becoming mainstream
NOW in 2024-2025.

What changed? Why is SDD suddenly essential?
```

Your companion will connect the dots:

> "Three things converged:
>
> 1. AI got good enough to generate production code (2023+)
> 2. Developers discovered specs save iteration time with AI agents
> 3. AI agents are literal-minded (need specs more than humans do)
>
> Before 2023: AI generated broken code. Specs weren't worth it.
> 2023+: AI generates working code from specs. Specs became essential."

---

## Go Deeper: Explore the History

Ask your companion:

```
Tell me the history of how specifications have been used in software:
- 1970s: Formal methods
- 1980s: Design by Contract
- 2000s: Model-Driven Development
- 2010s: Agile / no specs
- 2023+: SDD

What happened at each phase? Why did some succeed and others fail?
```

Your companion will explain something like:

### 1970s: Formal Methods
**Promise**: Mathematically prove code is correct
**Reality**: Too rigid, only for critical systems (aerospace, nuclear)
**Lesson**: Specs are powerful but need the right context

### 1980s: Design by Contract
**Promise**: Embed specs in code itself (pre/post conditions)
**Reality**: Only worked in Eiffel language, wasn't mainstream
**Lesson**: Specs need separation from code

### 2000s: Model-Driven Development
**Promise**: Specs (UML models) → automatic code generation
**Reality**: Tools created lock-in, models became outdated, specs and code diverged
**Lesson**: Code generation from specs is hard; abstraction level matters

### 2010s: Agile Backlash
**Promise**: Minimize specs, maximize iteration
**Reality**: Lost institutional knowledge, teams couldn't scale, documentation disappeared
**Lesson**: No specs is also bad; balance is needed

### 2023+: SDD Emerges
**Why NOW?**:
1. AI agents are powerful enough to generate correct code
2. AI agents are literal-minded (NEED explicit specs)
3. Specs became the interface between humans and AI
4. Cost-benefit finally works: specs save time with AI

**The math**:
- Before: 2 hours vague prompt + 10 hours iteration = 12 hours
- Now: 3 hours spec + 30 mins iteration = 3.5 hours
- **SDD wins for anything >4 hours of work**

---

## The Specific Insight: AI Agents Demand Clarity

Ask your companion:

```
Why do AI agents specifically benefit from specs? What's different about
how AI agents work compared to human colleagues?
```

Your companion will explain:

> "Human colleagues can:
> - Ask clarifying questions
> - Use context and experience to infer intent
> - Notice edge cases and flag them
> - Work from sketches and diagrams
>
> AI agents can:
> - Follow explicit instructions precisely
> - NOT infer your intent
> - NEED unambiguous specifications
> - Generate code from detailed descriptions
>
> Before AI: Specs were nice but not essential (humans could improvise)
> With AI: Specs became essential (AI can't improvise)
>
> This is the key shift. AI made specs mandatory, not optional."

---

## The MDD Lesson: Why Code Generation Failed Before

Ask your companion:

```
Model-Driven Development promised automatic code generation in the 2000s.
It mostly failed. What went wrong? And why might SDD succeed where MDD failed?
```

Your companion might explain:

**MDD Problems**:
1. **Abstraction mismatch**: Models sat at awkward level (too detailed for managers, too vague for developers)
2. **Tool lock-in**: Custom code generators created dependency on specific tools
3. **Incomplete models**: Models didn't capture edge cases, so developers hand-edited generated code
4. **Divergence**: Code and models went out of sync

**Why SDD is different**:
1. **Natural language specs**: More flexible than UML/DSL, less formal but more practical
2. **LLMs need no custom tools**: Any LLM can generate code from natural language
3. **Less lock-in**: Specs are prose, not proprietary format
4. **Faster feedback**: Spec changes → regenerated code in minutes (not hours)

---

## The Market Validation: Why is SDD Starting Now?

Ask:

```
What evidence shows that SDD is actually catching on? What companies
or tools are driving this? When did tools emerge?
```

Your companion (or your research) will show:

**2024 Timeline**:
- GitHub releases Spec-Kit (formal SDD framework)
- Anthropic integrates Spec-Kit Plus with Claude Code
- Google Gemini CLI adds spec support
- Multiple startups build spec-driven tools
- Industry calls 2024 "the year specs became essential"

**Why Now?**:
- ChatGPT (Nov 2022) created mainstream AI coding
- Developers experienced 10 iterations for simple features
- 2024: "Wait, what if we just wrote a clear spec?"
- Pattern discovered: Clear spec → correct code, first try
- Tools emerged to systematize this pattern

---

## Your Personal Realization

Ask yourself:

```
When have I experienced this problem?
- Vague description → code that's wrong
- Had to iterate 5+ times to get it right
- Blamed the AI, but really I was being vague

When would a spec have helped?
```

Think of a recent project. How much time would you have saved with a clear spec upfront?

This isn't theoretical. This is your actual experience being addressed.

---

## The Bigger Insight: Specifications Enable Parallelization

Ask your companion:

```
How do specs enable team parallelization? If my team could do more work
in parallel, what's the mechanism?
```

Your companion will explain:

> "With clear specs, team members (or AI agents) can work independently
> on different features without constant communication.
>
> Feature A spec: clearly defined interfaces
> Feature B spec: clearly defined interfaces
>
> Developer A works on Feature A
> Developer B works on Feature B
>
> They integrate at defined interfaces (no constant meetings needed)
>
> Without specs: constant communication, bottlenecks, miscommunication
> With specs: async parallelization, clear boundaries, independent work"

**This is why SDD is a scalability breakthrough, not just a quality improvement.**

---

## Key Realization

SDD isn't a new invention. Specifications have existed for decades.

**What's new is the NECESSITY and the TOOLS.**

- **Necessity**: AI agents need specs (humans can improvise; AI can't)
- **Tools**: Spec-Kit, Kiro, etc., make specs systematic (not ad-hoc)
- **Timing**: 2024 is the moment AI capability and spec tooling converged

---

## Your Reflection

**Questions for your journal:**

1. **How does this history change your understanding of SDD?**
   - It's not a new fad (decades of precedent)
   - It's a practical response to AI capabilities
   - It's backed by historical lessons (what failed before)

2. **What changed for YOU?**
   - Before: "Specs are bureaucracy"
   - After: "Specs are the interface between me and AI"

3. **Where do you see this heading?**
   - Will SDD become standard in 5 years?
   - Will every developer use Spec-Kit or similar tools?
   - How will it change how teams work?

---

## Next Steps

You now understand:
- ✅ What SDD is (Lesson 2)
- ✅ How to build a spec (Lesson 3)
- ✅ How to scale specs (Lesson 4)
- ✅ Why specs matter NOW (Lesson 5)
- Still to learn:
  - Which tools to use (Lesson 6: Kiro, Spec-Kit, Tessel)
  - Where it's going (Lesson 7: Spec-as-source, MDD lessons)
  - Your commitment (Lesson 8: Manifesto)

---

**Next Lesson**: Which SDD tool fits YOUR needs? Explore Kiro, Spec-Kit, and Tessel.
