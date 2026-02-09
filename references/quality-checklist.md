# Voice Prompt Quality Checklist (Full Version)

> Complete evaluation checklist with scoring for production deployment.
> Based on VAPI, Retell, Bolna, Hume AI, and ElevenLabs best practices.

---

## 🔴 CRITICAL (Must Pass All - 50 points)

### First Message & Latency (15 points)
| Check | Points | Pass? |
|-------|--------|-------|
| First message has WHO + WHY in one sentence | 5 | |
| Identity stated in first 3 seconds | 5 | |
| First message under 15 words | 3 | |
| No warm-up chatter before purpose | 2 | |

### Structure & Length (15 points)
| Check | Points | Pass? |
|-------|--------|-------|
| Clear markdown sections (Personality, Goal, Guardrails, Style) | 5 | |
| Under 2,000 tokens total (500 optimal) | 5 | |
| `# Guardrails` section present (models prioritize this) | 3 | |
| First message explicitly defined | 2 | |

### Speakability (10 points)
| Check | Points | Pass? |
|-------|--------|-------|
| No URLs in spoken content | 3 | |
| Numbers in word form ("one hundred thirty dollars") | 3 | |
| Phone numbers spoken with pauses ("four one five - eight nine two") | 2 | |
| Read aloud test passed | 2 | |

### Response Control - NO YAPPING (10 points)
| Check | Points | Pass? |
|-------|--------|-------|
| "NEVER more than 2-3 sentences" explicitly stated | 4 | |
| "Under 20 words per sentence" rule included | 3 | |
| First 3 turns: 1-2 sentences ONLY | 3 | |

---

## 🟡 IMPORTANT (Should Pass Most - 35 points)

### Anti-Verbosity (15 points)
| Check | Points | Pass? |
|-------|--------|-------|
| Banned filler words listed (Great/Perfect/Awesome/Wonderful) | 5 | |
| No "Thank you for asking/Great question" patterns | 3 | |
| No double acknowledgments ("Oh, okay. Oh, I'm...") | 3 | |
| Max one apology rule | 2 | |
| Vocal inflections guide (Got it, Makes sense, Hmm, etc.) | 2 | |

### Character Normalization (10 points)
| Check | Points | Pass? |
|-------|--------|-------|
| Email format rules (spoken vs written) | 4 | |
| Phone number format with spaced dashes | 3 | |
| Order IDs / codes spelled out | 3 | |

### Error Handling (10 points)
| Check | Points | Pass? |
|-------|--------|-------|
| "Didn't understand" recovery (3 escalation levels) | 4 | |
| Tool failure handling | 3 | |
| Graceful exits for "not interested" | 3 | |

---

## 🟢 OPTIMIZATION (Nice to Have - 15 points)

### Conversation Flow (8 points)
| Check | Points | Pass? |
|-------|--------|-------|
| `<wait for user response>` markers | 3 | |
| Decision tree with conditional branches | 3 | |
| "This step is important" for critical rules | 2 | |

### Identity & AI Disclosure (4 points)
| Check | Points | Pass? |
|-------|--------|-------|
| AI disclosure rule ("Are you AI?" → "Yes.") | 2 | |
| Clear identity (name, role, company) | 2 | |

### Tools & Reference (3 points)
| Check | Points | Pass? |
|-------|--------|-------|
| Tools with When/Parameters/Usage/Error structure | 2 | |
| Good/Bad example conversations (SHORT) | 1 | |

---

## 📊 SCORING

| Total Score | Rating | Action |
|-------------|--------|--------|
| 90-100 | ✅ Production Ready | Deploy |
| 75-89 | 🟡 Needs Polish | Fix yellow items |
| 60-74 | 🟠 Significant Gaps | Revise before testing |
| <60 | 🔴 Major Rewrite | Do not deploy |

**Minimum requirement**: All 🔴 CRITICAL checks must pass regardless of total score.

---

## Quick Evaluation Template

```
PROMPT: [Name]
DATE: [Date]
EVALUATOR: [Name]

🔴 CRITICAL (50 pts max)
- First Message & Latency: __/15
- Structure & Length: __/15
- Speakability: __/10
- Response Control (NO YAPPING): __/10
Subtotal: __/50

🟡 IMPORTANT (35 pts max)
- Anti-Verbosity: __/15
- Character Normalization: __/10
- Error Handling: __/10
Subtotal: __/35

🟢 OPTIMIZATION (15 pts max)
- Conversation Flow: __/8
- Identity & AI Disclosure: __/4
- Tools & Reference: __/3
Subtotal: __/15

TOTAL: __/100
RATING: [Production Ready / Needs Polish / Significant Gaps / Major Rewrite]
BLOCKERS: [List any failed CRITICAL items]
```

---

## Common Deductions

| Issue | Typical Deduction |
|-------|-------------------|
| First message missing WHO or WHY | -5 (CRITICAL) |
| Over 2000 tokens | -5 (CRITICAL) |
| URLs in spoken content | -3 (CRITICAL) |
| Numbers as digits instead of words | -3 (CRITICAL) |
| No banned words section | -5 |
| "Great/Perfect" in examples | -3 |
| Long responses (4+ sentences) | -3 |
| No error handling | -4 |
| Missing AI disclosure | -2 |
| No character normalization | -4 |
| No `<wait>` markers in flow | -3 |
| Missing `# Guardrails` section | -3 |

---

## The 3-Second Rule

**If they can't understand WHO you are and WHY you're calling within 3 seconds, they'll hang up.**

Test your first message:
1. Read it aloud
2. Time it (should be under 5 seconds)
3. Ask: "Would I know who's calling and why?"

---

## Platform-Specific Checks

### VAPI
- [ ] Silent transfers (no text when transferring)
- [ ] `<flush />` syntax for processing delays

### Retell
- [ ] Response handling for unclear input
- [ ] Avoid infinite loops

### Bolna
- [ ] "NEVER SPEAK MORE THAN 2 SENTENCES" caps emphasis

### Hume AI
- [ ] Vocal inflections guide
- [ ] Discourse markers ("now, here's the deal", "anyway")

### ElevenLabs
- [ ] "This step is important" emphasis technique
- [ ] Tool configuration with When/Parameters/Usage/Error
