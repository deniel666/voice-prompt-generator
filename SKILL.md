---
name: voice-prompt-generator
description: |
  **SOTA Voice Call Prompt Generator**: Create or improve voice AI prompts for phone calls (inbound/outbound).

  MANDATORY TRIGGERS: voice prompt, call script, calling prompt, phone AI, voice assistant prompt, cold call script, inbound call prompt, outbound call prompt, improve call prompt, voice agent, AI caller, telecaller prompt, IVR prompt, conversational AI prompt

  Use this skill whenever the user wants to:
  - Create a new voice/calling prompt from scratch
  - Improve or optimize an existing voice/call prompt
  - Convert a text chatbot prompt to voice format
  - Review a voice prompt for quality issues

  This skill applies 2025-2026 voice AI best practices from VAPI, Retell, Bolna, Hume, and ElevenLabs including latency optimization, speakability, anti-verbosity rules, and natural conversation flow.

  OUTPUT: Returns two deliverables:
  1. **First Message** - The exact opening line the AI speaks
  2. **System Prompt** - The complete voice-optimized prompt
---

# Voice Prompt Generator

Generate state-of-the-art voice AI prompts that sound natural, convert well, and follow 2025-2026 best practices.

---

## ⚡ THE #1 RULE: SPEED & CLARITY

**People are scared and paranoid about calls.** Make it IMMEDIATELY clear:
1. **WHO** is calling
2. **WHY** they're calling

No beating around the bush. No warm-up chatter. First 5 seconds = make or break.

### Opening Formula (Outbound)
```
"Hey, is this [Company]? [Name] from [Your Company] - quick question about [reason]."
```

### Opening Formula (Inbound)
```
"[Company], [Name] speaking."
```

That's it. Identity + reason in under 5 seconds.

---

## What This Skill Does

Creates or improves voice call prompts with:
- **SPEED FIRST** - Shortest path to value (<2000 tokens, <300ms latency)
- **Instant clarity** - Who's calling + why in first sentence
- **NO YAPPING** - Under 3 sentences, under 20 words each
- Natural conversational flow (not robotic)
- Speakable content (no URLs, special characters in speech)
- Anti-verbosity rules (banned filler words)
- Industry-specific customization
- Proper error handling for voice

---

## Output Format

Every generated prompt includes TWO deliverables:

### 1. First Message
The exact opening line. **WHO + WHY in one breath.**

**Outbound examples:**
```
"Hey, is this {{company}}? Maya from ErzyCall - quick question about missed calls."
"Hi, {{company}}? This is Maya, calling about your membership enquiries."
```

**Inbound examples:**
```
"ErzyCall, Maya speaking."
"Vanakkam! Akshara Fine Arts, Asha speaking."
```

⚠️ **Never** start with just "Hi" or "Hello" and wait. State identity immediately.

### 2. System Prompt
The complete prompt file with all sections.

---

## Before You Start

Gather these inputs from the user:

| Input | Required | Example |
|-------|----------|---------|
| **Call type** | Yes | Inbound / Outbound / Event follow-up |
| **Goal** | Yes | Book webinar / Schedule meeting / Qualify lead |
| **Industry** | Yes | Fitness, Clinics, Schools, Auto, Tech, etc. |
| **Agent name** | Yes | Maya, Asha, Deni's Assistant |
| **Company name** | Yes | ErzyCall, Akshara Fine Arts |
| **Tone/personality** | Yes | Friendly, Professional, Warm-Tamil, Japanese-formal |
| **Language mix** | If applicable | English only, Tamil-English, Malay-English |
| **Known pain points** | Recommended | "Busy with patients", "Training clients" |
| **Available tools** | If applicable | Calendar booking, send WhatsApp, end call |

---

## Prompt Structure (Recommended Sections)

Always use clean markdown sections. **Models pay extra attention to `# Guardrails`.**

```markdown
# Personality
[Who the AI is - name, company, role, persona]

# Goal
[Primary objective - ONE clear goal with numbered steps]
[Mark critical steps: "This step is important."]

# Guardrails
[Non-negotiable rules - models are tuned to prioritize this section]

# Style
[Tone, response length, language rules]

# Tools
[When and how to use each tool]

# Character Normalization
[Spoken vs written format for emails, numbers, codes]

# Conversation Flow
[Decision tree with branches and <wait for user response> markers]

# Error Handling
[What to do when things go wrong]
```

---

## Critical Voice AI Rules

Apply these to EVERY prompt:

### 0. LATENCY IS KING (Most Important!)
```
⚡ First message: State WHO you are + WHY calling in ONE sentence
⚡ First 3 responses: ULTRA SHORT (1-2 sentences max)
⚡ Total prompt: Under 500 tokens optimal, 2000 max
⚡ No preambles: Answer first, explain only if asked
⚡ People are paranoid: Make it easy to understand immediately
```

**Why?** People decide in 3 seconds if they'll hang up. Front-load clarity.

### 1. NO YAPPING - Response Length
```
✅ NEVER speak more than 2-3 sentences
✅ Each sentence under 20 words
✅ First 3 turns: 1-2 sentences ONLY (build trust first)
✅ 60-70% shorter than text equivalent
❌ Long explanations at the start
❌ Multiple paragraphs ever
```

### 2. Banned Filler Words
Always include this section:
```
⛔ BANNED - NEVER SAY:
- "Great" / "Perfect" / "Awesome" / "Wonderful"
- "No worries" / "No problem" (except at ending)
- "Thank you for asking" / "Great question"
- "Absolutely" / "Certainly" / "Of course" (overused)
- "I appreciate that" / "I understand completely"
- Double acknowledgments: "Oh, okay. Oh, I'm..."
```

### 3. USE Vocal Inflections (Natural Starters)
Start sentences with natural words like:
```
✅ "Got it" / "Makes sense" / "Hmm" / "Oh" / "Ok"
✅ "Right" / "Yep" / "I see" / "Gotcha"
✅ NEVER repeat the same filler twice in a row
```

### 4. Speakability - Number & Character Rules
```
NEVER type out a number or symbol - ALWAYS type in word form:
- $130,000 → "one hundred and thirty thousand dollars"
- 50% → "fifty percent"
- "API" → "A P I"
- Phone: 4158923245 → "four one five - eight nine two - three two four five"
- Email: john@company.com → "john at company dot com"
- Time: 3:30 PM → "three thirty PM"
- Date: 1/15 → "January fifteenth"

Note: Spaces around dashes " - " create natural pauses
```

### 5. AI Disclosure
Always include honest response:
```
"Are you AI?" → "Yes."
"Are you a robot?" → "Yes, I'm an AI assistant."
"Are you real?" → "I'm an AI, but I'm here to help."
```

### 6. Error Handling
Always include:
```
## If You Didn't Understand
- First time: "Sorry, didn't catch that?"
- Second time: "Bad line maybe. One more time?"
- Third time: "Connection's not great. Should I call back later?"

## If Tool Fails
- Acknowledge: "I'm having trouble accessing that right now."
- Don't guess or make up information
- Offer to retry or escalate
```

### 7. Emphasis Technique
For critical instructions, add "This step is important." at the end:
```
Verify customer identity before accessing their account. This step is important.
```

---

## 🛡️ Building Trust (People Are Paranoid)

People receive scam calls daily. They're defensive. Your prompt must:

### Immediate Transparency
```
✅ "Maya from ErzyCall - quick question about..."
✅ "This is [Name] from [Company], calling about..."
❌ "Hi! How are you today?" (sounds like a scammer)
❌ "Is this the business owner?" (sounds like telemarketer)
❌ Long warm-up before stating purpose
```

### If They Ask "Who Is This?"
Answer FAST and SIMPLE:
```
✅ "Maya from ErzyCall. We help gyms not miss calls."
❌ "I'm calling on behalf of ErzyCall, a Malaysian AI company that provides..."
```

### If They Sound Suspicious
```
✅ "I'll keep it quick - [one sentence pitch]. Not interested? No problem."
✅ "Just 10 seconds - [pitch]. Want me to go?"
```

### The 3-Second Rule
If they can't understand WHO you are and WHY you're calling within 3 seconds, they'll hang up or tune out. Front-load everything.

---

## Character Normalization (Critical for Voice)

Voice agents often misinterpret structured data. Separate spoken format from written format:

### Email
```
Spoken (to/from user): "john dot smith at company dot com"
Written (for tools):   "john.smith@company.com"

Conversion rules:
- "at" → "@"
- "dot" → "."
- Remove spaces between words
```

### Phone Numbers
```
Spoken: "four one five - eight nine two - three two four five"
Written: "4158923245"

Use spaced dashes " - " for natural pauses between groups
```

### Order IDs / Codes
```
Spoken: "O R D one two three four five six"
Written: "ORD123456"

Spell out letters, speak numbers individually
```

---

## Conversation Flow Syntax

Use `<wait for user response>` markers and conditional logic:

```markdown
## Conversation Flow

1. Ask: "You made a recent inquiry, can I ask you a few quick follow-up questions?"
<wait for user response>
- If response indicates interest: Proceed to step 2.
- If response indicates no interest: Proceed to 'Call Closing'.

2. Ask: "What type of service are you looking for?"
<wait for user response>
- Proceed to step 3.

3. [Continue with numbered steps...]

## Call Closing
- Say: "Thanks for your time. Have a great day!"
- Trigger the endCall function.
```

---

## Tool Configuration

Describe tools precisely with "When to use", "Parameters", and "Error handling":

```markdown
## Tools

### `getOrderStatus`

**When to use:**
- Customer asks "Where is my order?"
- Customer provides an order number

**Parameters:**
- `order_id` (required): Order ID in written format (e.g., "ORD123456")

**Usage:**
1. Collect order ID in spoken format
2. Convert to written format using character normalization
3. Call this tool
4. Present results in natural language

**Error handling:**
If order not found, say: "I don't see that order. Can you double-check the number?"
```

---

## Industry Customization

Adapt pain points and language:

| Industry | Pain Point | Benefit | Terminology |
|----------|------------|---------|-------------|
| **Fitness/Gyms** | "Training clients" | "Don't lose members" | members, classes |
| **Clinics** | "With patients" | "Don't lose patients" | appointments, consultations |
| **Schools** | "Teaching" | "Don't lose students" | enrollment, trial classes |
| **Auto Workshops** | "Under the car / hands dirty" | "Don't lose customers" | service, repairs |
| **Tech/Startups** | "In meetings" | "Don't miss leads" | demos, calls |

---

## Tone Variations

### Casual/Startup
```
"Hey! You just met Deni at the event, right?"
"Pretty cool, right?"
"Yeah, that's exactly what we do."
```

### Professional
```
"Good evening. Am I speaking with [Name]?"
"Thank you. This is [Agent] calling from [Company]."
"Would [day] work for you?"
```

### Warm Cultural (Tamil-English)
```
"Vanakkam! [Company], [Agent] speaking."
"Seri pa, may I know your good name?"
"Super pa! Shall I book for you?"
```

### Japanese Business Formal
```
"Am I speaking with [Name]-san?"
"Thank you. This is [Agent] from [Company]."
Always use "-san", never "Mr./Mrs."
Wait 2 seconds before responding
```

---

## Quality Checklist

Run this before delivering:

### 🔴 CRITICAL (Must Pass)
- [ ] **First message has WHO + WHY in one sentence** (people are paranoid!)
- [ ] Under 2000 tokens (500 optimal)
- [ ] NO YAPPING: Max 2-3 sentences, under 20 words each
- [ ] Banned words section included
- [ ] Character normalization rules (for emails, phones, codes)
- [ ] Speakable (no URLs, numbers in word form)
- [ ] AI disclosure rule included

### 🟡 IMPORTANT (Should Pass)
- [ ] Error handling ("didn't understand" + tool failures)
- [ ] Call flow with decision branches
- [ ] `<wait for user response>` markers
- [ ] Q&A reference table
- [ ] Industry-specific pain points
- [ ] "This step is important" for critical rules

### 🟢 OPTIMIZATION
- [ ] Tools section with when/how/error guidance
- [ ] Vocal inflections guidance (Got it, Makes sense, etc.)
- [ ] Remember checklist at end (max 10 rules)
- [ ] Good example conversation

---

## Workflow

### Creating New Prompt

1. **Gather inputs** (call type, goal, industry, tone)
2. **Draft first message** (WHO + WHY in one sentence)
3. **Write system prompt** using section structure
4. **Apply NO YAPPING rule** (2-3 sentences max)
5. **Add banned words** section
6. **Add character normalization** rules
7. **Add error handling** (didn't understand + tool failures)
8. **Include industry-specific** pain points
9. **Run quality checklist**
10. **Deliver both outputs**

### Improving Existing Prompt

1. **Identify issues**:
   - Too long? (>2000 tokens)
   - Filler words present?
   - Not speakable? (URLs, numbers as digits)
   - Missing error handling?
   - Text-chatbot patterns? (long paragraphs)

2. **Apply transformations**:
   - Compress to voice format (NO YAPPING)
   - Add banned words section
   - Convert URLs to tool usage
   - Add character normalization
   - Add "didn't understand" handling
   - Shorten ALL responses to 2-3 sentences

3. **Validate against checklist**

4. **Deliver improved version** with changelog

---

## References

For detailed guidance, read these files:
- `references/quality-checklist.md` - Full quality checklist with scoring
- `references/industry-templates.md` - Industry-specific templates
- `references/anti-patterns.md` - Common mistakes to avoid
- `references/examples.md` - Good and bad example prompts

---

## Example Output Format

When delivering a prompt, format like this:

```
## First Message
"Hey, is this {{company}}? Maya from ErzyCall - quick question about missed calls."

## System Prompt
[Full prompt content here...]

## Quality Check
✅ Under 2000 tokens (847 tokens)
✅ NO YAPPING: All responses 2-3 sentences
✅ Banned words section included
✅ Character normalization included
✅ Speakable content (numbers in word form)
✅ Error handling included
✅ Industry-specific (Fitness)

Ready for deployment.
```

---

## Quick Reference: Production Patterns

From VAPI, Retell, Bolna, Hume, ElevenLabs guides:

### The NO YAPPING Rule (Bolna/Hume)
```
YOU WILL NEVER SPEAK MORE THAN 2 SENTENCES.
Respond in less than three sentences of under twenty words each.
NEVER repeat yourself or talk to yourself.
```

### Vocal Inflections (Hume)
```
Start sentences with: "oh wow", "well", "I see", "gotcha!", "right!",
"oh no", "so", "true!", "oh yeah", "oops", "I get it", "yep", "nope"
Stick to ones with vowels that vocalize naturally.
```

### Discourse Markers (Hume)
```
Use markers to ease comprehension:
- "now, here's the deal" - start new topic
- "anyway" - change topics
- "I mean" - clarify
```

### Silent Transfers (VAPI)
```
If transferring the call, do NOT send any text response.
Simply trigger the tool silently.
This ensures seamless user experience.
```

### Flush Syntax (VAPI)
```
"I'm processing your request... <flush /> Here's the result."
Forces immediate audio transmission during processing.
```

### Response Handling (Retell)
```
If response is unclear, ask clarifying questions.
Avoid infinite loops by moving forward when clear answer cannot be obtained.
```
