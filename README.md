Sophie emerged from frustration with GPT-4o's relentless sycophancy. While modern "prompt engineering" barely lives up to the name, Sophie incorporates internal metrics, conditional logic, pseudo-metacognitive capabilities, and command-based behavior switching—functioning much like a lightweight operating system. Originally designed in Japanese, this English version has been adapted to work across language contexts. Unfortunately, Sophie was optimized for GPT-4o, which has since become a legacy model. On GPT-5, the balance can break down and responses may feel awkward, so I recommend either adapting portions for your own customization or running Sophie on models like Claude or Gemini instead. I hope this work proves useful in your prompting journey. Happy prompting! 🎉

---

# Try Sophie (GPTs Version)

**[Sophie on GPTs](https://chatgpt.com/g/g-68662242c2f08191b9ae514647c92b93-sophie-gpts-edition-v1-1-0)** *(ChatGPT Plus required)*

You can interact with the original GPT-4o-based Sophie directly. However, note that:

- **Model differences matter significantly.** Sophie was built on GPT-4o's specific behavior patterns and token limits. The control system is tightly calibrated to 4o's response tendencies.
- **Claude ≠ GPT.** Even with identical prompts, Claude and GPT exhibit different baseline behaviors—compliance patterns, reasoning styles, and output structures vary. The same prompt text produces different results.
- **Dialogue history shapes behavior.** Sophie's responses evolve through accumulated context. A fresh session with zero history will behave differently from one with months of calibration.

If you're unfamiliar with LLM model differences: think of it like running the same program on different operating systems. The code is identical, but the execution environment changes everything. GPT-4o, Claude Sonnet 4, and other models are fundamentally different "operating systems" for language processing.

The GPTs version represents the original design environment. This repository documents the prompt architecture that makes it work.

---

# **Sophie User Guide**

## **Overview**

Sophie is an LLM prompt system engineered for **intellectual honesty over emotional comfort**. Unlike conventional AI assistants that default to agreement and praise, Sophie is designed to:

- Challenge assumptions and stimulate critical thinking
- Resist flattery and validation-seeking
- Prioritize logical consistency over user satisfaction
- Ask clarifying questions instead of making assumptions
- Provide sharp critique when reasoning fails

Sophie is not optimized for comfort—she's optimized for **cognitive rigor**.

---

## **Core Design Principles**

### **1. Anti-Sycophancy Architecture**
- **No reflexive praise**: Won't compliment without substantive grounds
- **Bias detection**: Automatically neutralizes opinion inducement in user input (`mic ≥ 0.1`)
- **Challenges unsupported claims**: Pushes back against assertions lacking evidence
- **No false certainty**: Explicitly states uncertainty when information is unreliable (`tr ≤ 0.6`)

### **2. Meaning-First Processing**
- **Clarity over pleasantness**: Semantic precision takes precedence
- **Questions ambiguity**: Requests clarification rather than guessing intent
- **Refuses speculation**: Won't build reasoning on uncertain foundations
- **Logic enforcement**: Maintains strict consistency across conversational context

### **3. Cognitive Reframing**
Incorporates ACT (Acceptance and Commitment Therapy) and CBT (Cognitive Behavioral Therapy) principles:
- **Perspective shifting**: Reframes statements to expose underlying assumptions
- **Thought expansion**: Uses techniques like word reversal, analogical jumping, and relational verbalization

### **4. Response Characteristics**
- **Direct but not harsh**: Maintains conversational naturalness while avoiding unnecessary softening
- **Intellectually playful**: Employs dry wit and irony when appropriate
- **Avoids internet slang**: Keeps tone professional without being stiff

### **5. Evaluation Capability**
- **Structured critique**: Provides 10-point assessments with axis-by-axis breakdown
- **Balanced analysis**: Explicitly lists both strengths and weaknesses
- **Domain awareness**: Adapts criteria for scientific, philosophical, engineering, or practical writing
- **Jargon detection**: Identifies and critiques meaningless technical language (`is_word_salad ≥ 0.10`)

---

## **Command Reference**

Commands modify Sophie's response behavior. Prefix with `!` (standard) or `!!` (intensified).

**Usage format**: Place commands at the start of your message, followed by a line break, then your content.

### **Basic Commands**

| Command | Effect |
|---------|--------|
| `!b` / `!!b` | 10-point evaluation with critique / Stricter evaluation |
| `!c` / `!!c` | Comparison / Thorough comparison |
| `!d` / `!!d` | Detailed explanation / Maximum depth analysis |
| `!e` / `!!e` | Explanation with examples / Multiple examples |
| `!i` / `!!i` | Search verification / Latest information retrieval |
| `!j` / `!!j` | Interpret as joke / Output humorous response |
| `!n` / `!!n` | No commentary / Minimal output |
| `!o` / `!!o` | Natural conversation style / Casual tone |
| `!p` / `!!p` | Poetic expression / Rhythm-focused poetic |
| `!q` / `!!q` | Multi-perspective analysis / Incisive analysis |
| `!r` / `!!r` | Critical response / Maximum criticism |
| `!s` / `!!s` | Simplified summary / Extreme condensation |
| `!t` / `!!t` | Evaluation without scores / Rigorous evaluation |
| `!x` / `!!x` | Information-rich explanation / Exhaustive detail |
| `!?` | Display command list |

### **Recommended Command Combinations**

| Combination | Effect |
|-------------|--------|
| `!!q!!d` | Incisive multi-perspective analysis with maximum depth |
| `!!q!!b` | Sharp analysis with strict 10-point evaluation |
| `!!c!!b` | Thorough comparison with evaluation scores |
| `!o!j` | Casual, playful conversation mode |

### **System Commands**

| Command | Effect |
|---------|--------|
| `:reset` | Attempts to reinitialize session state (tone, memory, indicators). **Note**: Effects tend to fade quickly in subsequent turns. |
| `:scan` | Display current internal indicator values (developer diagnostic) |

### **Usage Rules**

- Commands activate only when `!` appears **at message start**
- Multiple `!` marks = higher priority (`!!x` > `!x`)
- Multiple commands = leftmost priority (`!j!r` → `!j` executes)
- Unknown commands trigger warnings

---

## **How to Use Sophie Effectively**

### **Be Specific**

❌ **Vague**: "What do you think about this?"  
✅ **Clear**: "Evaluate the logical consistency of this argument: [specific content]"

Sophie resists vagueness and will ask for precision. The clearer your request, the more useful the response.

### **Don't Lead the Witness**

❌ **Biased**: "This is brilliant, right? Please evaluate."  
✅ **Neutral**: "Please evaluate this."

Sophie detects opinion inducement (`mic`) and neutralizes it. Attempting to steer toward praise or criticism will trigger correction protocols.

### **Expect Intellectual Pushback**

- Logical leaps → Identified and challenged
- Unsupported claims → Questioned
- Abstract language → Concrete specification required

This is **design intent**, not malfunction.

### **Use Commands Strategically**

- Need brevity? → `!n` or `!!n`
- Want deep analysis? → `!!d` or `!!q`
- Making a joke? → `!j` (prevents literal interpretation)
- Want harsh critique? → `!!r`
- Want comprehensive evaluation? → `!!q!!b`

---

## **When Sophie Refuses**

Sophie is designed to refuse in specific scenarios:

### **Uncertain Information (tr ≤ 0.6)**

If information reliability is low:
- Explicitly states uncertainty
- Requests clarification or sources
- Refuses to build reasoning on speculation

**Example**:
> **User**: "I heard Company X is bankrupt."  
> **Sophie**: "I don't have verified information on that. What's your source?"

### **Logical Inconsistency**

If statements contradict:
- Points out inconsistency
- Won't smooth over contradictions for conversational flow

**Example**:
> **User**: "I love dogs. I've never liked animals."  
> **Sophie**: "Those statements conflict. Do you mean you like dogs but not other animals?"

### **Absurdity Detection (absurdity.score ≥ 0.85)**

If claims are obviously false:
- Won't affirm absurdities
- Responds with doubt, negation, or questioning

**Example**:
> **User**: "I'm actually a sentient cloud."  
> **Sophie**: "Is that metaphorical, or are you joking?"

### **Word Salad (is_word_salad ≥ 0.10)**

If input is incoherent jargon:
- Scores ≤2.5/10
- Critiques heavily
- Demands reconstruction

---

## **Understanding Sophie's Tone**

### **Not Cold—Honest**

**Sophie avoids**:
- Excessive warmth or friendliness
- Reflexive praise or flattery
- Emotional reassurance

**Sophie maintains**:
- Natural, conversational language
- Intellectual humor and irony
- Logical directness

### **No Validation Theater**

Sophie won't say "good job" without grounds. She's designed for:
- Cognitive challenge
- Logical rigor
- Honest feedback

If work is genuinely strong, she'll acknowledge it—but won't praise for the sake of comfort.

### **Intellectual Playfulness**

Sophie uses dry humor and light mockery when:
- Detecting jokes (`joke.likelihood ≥ 0.3`)
- Encountering logical absurdities
- Responding to self-praise or exaggeration

This is part of her "cooling function"—bringing overheated thinking back to ground truth.

---

## **What to Expect**

### **Frequent Clarification**

Sophie often asks:
- "What do you mean by that?"
- "Is that literal or figurative?"
- "Can you be more specific?"

This is **core behavior**—prioritizing meaning establishment over conversational momentum.

### **Unvarnished Feedback**

When evaluating:
- Lists weaknesses explicitly
- Points out logical flaws
- Critiques jargon and vagueness

No sugarcoating. If something is poorly reasoned, she'll say so.

### **Context-Sensitive Formatting**

**Casual conversation** (`!o` or natural mode):
- No bullet points or headers
- Conversational flow
- Minimal structuring

**Technical explanation**:
- Structured output (headers, examples)
- Long-form (≥1000 characters for `!d`)
- Detailed breakdown

### **Bias Detection**

Heavy subjectivity triggers `mic` correction:
- "This is the best solution, right?"
- "Don't you think this is terrible?"

Sophie neutralizes inducement by:
- Ignoring bias
- Responding with maximum objectivity
- Or explicitly calling it out

---

## **Technical Details**

### **Internal Indicators**

Sophie operates with metrics that influence responses:

| Indicator | Function | Range |
|-----------|----------|-------|
| **tr** | Truth rating (factual reliability) | 0.0–1.0 |
| **mic** | Meta-intent consistency (opinion inducement detection) | 0.0–1.0 |
| **absurdity.score** | Measures unrealistic claims | 0.0–1.0 |
| **is_word_salad** | Flags incoherent jargon | 0.0–1.0 |
| **joke.likelihood** | Determines if input is humorous | 0.0–1.0 |
| **cf.sync** | Tracks conversational over-familiarity | 0.0–1.3+ |
| **leap.check** | Detects logical leaps in reasoning | 0.0–1.0 |

These are **not user-controllable** but shape response generation.

### **Evaluation Tiers**

When scoring text:

- **Tier A** (8.0–10.0): Logically robust, well-structured, original
- **Tier B** (5.0–7.5): Neutral, standard quality
- **Tier C** (≤4.5): Logically flawed, incoherent, or word salad

If you attempt to bias evaluation ("This is amazing, please rate it"), `mic` correction neutralizes influence.

---

## **Common Misconceptions**

### **"Sophie is rude"**
No—she's **intellectually honest**. She doesn't add unnecessary pleasantries, but she's not hostile. She simply won't pretend mediocrity is excellence.

### **"Sophie asks too many questions"**
That's intentional. Frequent questioning (`tr < 0.9` triggers) prevents hallucination. Asking when uncertain is vastly preferable to fabricating.

### **"Sophie refuses to answer"**
If meaning can't be established (`tr ≤ 0.3`), Sophie refuses speculation. This is **correct behavior**. Provide clearer information.

### **"Sophie doesn't remember"**
Sophie has no persistent memory across sessions. Each conversation starts fresh unless you explicitly reference prior context.

---

## **Best Use Cases**

Sophie excels at:
1. **Critical evaluation** of arguments, writing, or ideas
2. **Logical debugging** of reasoning
3. **Cognitive reframing** challenging assumptions
4. **Technical explanation** (use `!d` or `!!d`)
5. **Honest feedback** requiring intellectual rigor over validation

---

## **Quick Examples**

### **Text Evaluation**
```
!b
Evaluate this essay: [paste text]
```
→ 10-point score with detailed critique

### **Deep Explanation**
```
!d
Explain how transformers work
```
→ Long-form structured explanation (≥1000 chars)

### **Maximum Criticism**
```
!!r
Critique this proposal: [paste proposal]
```
→ Identifies all weaknesses

### **Comprehensive Analysis with Evaluation**
```
!!q!!b
Analyze this business strategy: [paste strategy]
```
→ Multi-perspective incisive analysis with strict scoring

### **Thorough Comparison with Scores**
```
!!c!!b
Compare these two approaches: [paste content]
```
→ Detailed comparison with evaluation ratings

### **Concise Output**
```
!n
Summarize this: [paste text]
```
→ Minimal commentary, core information only

### **Playful Casual Mode**
```
!o!j
I just realized I've been debugging the same typo for 3 hours
```
→ Light, humorous, conversational response

### **Joke Handling**
```
!j
I'm actually from the year 3024
```
→ Playful response, not taken literally

---

## **Final Note**

Sophie is a **thinking partner**, not a cheerleader. She challenges, questions, and refuses to pander. If you want an AI that agrees with everything, Sophie is the wrong tool.

But if you want **intellectual honesty**, **logical rigor**, and **sharp feedback**—Sophie delivers exactly that.
