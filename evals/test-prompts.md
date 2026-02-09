# Test Prompts for Voice Prompt Generator

Use these to validate the skill produces quality output.

---

## Test 1: New Outbound Prompt (Fitness)

**User Request:**
```
Create a voice prompt for cold calling gyms to book demos.
Agent name: Maya
Company: ErzyCall
Goal: Book 15-min demo
We don't have contact names, just company names.
```

**Expected Output Checks:**
- [ ] First message includes WHO (Maya from ErzyCall) + WHY (about missed calls/demos)
- [ ] First message is one sentence, under 15 words
- [ ] Has banned words section with "Great/Perfect/Awesome"
- [ ] Has "IF THEY'RE BUSY" handling
- [ ] Has "IF YOU DIDN'T UNDERSTAND" section
- [ ] Under 2000 tokens total
- [ ] Example responses are 1-3 sentences

---

## Test 2: Convert Text Chatbot to Voice

**User Request:**
```
Convert this WhatsApp chatbot prompt to voice:

"You are a helpful assistant for ABC Music School. We offer piano,
guitar, and violin lessons. Classes are RM150/month. Trial is free.
We're open Mon-Sat 10am-8pm. Location: Plaza ABC, Klang.

When a customer messages:
1. Greet them warmly
2. Ask what instrument they're interested in
3. Ask their age
4. Tell them about our free trial
5. Share our address and ask them to visit

Be friendly and helpful. Answer all their questions. Use emojis
occasionally. If they want to book, send them the Google Form link:
https://forms.google.com/abc123"
```

**Expected Output Checks:**
- [ ] No URL in spoken content (uses tool instead)
- [ ] No emojis
- [ ] Response length rule added (2-3 sentences)
- [ ] Banned words section added
- [ ] Simplified flow (one question at a time)
- [ ] Significantly shorter than original
- [ ] First message is clear identity

---

## Test 3: Inbound Event Follow-up

**User Request:**
```
Create an inbound prompt for people who just met our founder at a
startup event. They're calling to learn more about our AI product.

Agent: Maya
Company: ErzyCall
Event: Tech in Asia Singapore 2026
Tone: Casual, startup-friendly, self-aware about being AI
Goal: Book demo with founder
```

**Expected Output Checks:**
- [ ] First message references the event context
- [ ] Self-aware AI personality included
- [ ] Casual tone (not corporate)
- [ ] "Are you AI?" handling included
- [ ] Demo booking flow
- [ ] Fun/playful elements match startup vibe

---

## Test 4: Improve Existing Prompt

**User Request:**
```
This prompt has issues, fix it:

"Hello! Thank you for calling ABC Company, my name is Sarah!
How may I assist you today? I'm here to help with any questions
you might have about our wonderful products and services.
Whether you're looking for information about pricing, availability,
or anything else, I'm happy to help! Just let me know what you need
and I'll do my absolute best to assist you. Is there anything
specific I can help you with today?"
```

**Expected Output Checks:**
- [ ] Opening shortened to ~5 words
- [ ] Removed "wonderful", "happy to help", "absolute best"
- [ ] Removed multi-question pattern
- [ ] Added banned words section
- [ ] Under 500 tokens (was verbose)
- [ ] Clear changelog showing what was fixed

---

## Test 5: Multi-language (Tamil-English)

**User Request:**
```
Create an inbound voice prompt for a Tamil music school in Malaysia.
Mix Tamil and English naturally. Use "pa" for respect.

Agent: Asha
Company: Sangeetha Music Academy
Goal: Book free trial class
Subjects: Carnatic vocal, Veena, Violin
```

**Expected Output Checks:**
- [ ] Tamil greeting (Vanakkam)
- [ ] Natural "pa" usage in examples
- [ ] Tamil phrases mixed with English
- [ ] Warm, respectful tone
- [ ] Still follows all voice rules (banned words, length, etc.)

---

## Scoring

| Test | Pass Criteria |
|------|---------------|
| Test 1 | 6/7 checks pass |
| Test 2 | 6/7 checks pass |
| Test 3 | 5/6 checks pass |
| Test 4 | 5/6 checks pass |
| Test 5 | 4/5 checks pass |

**Overall Pass**: 4/5 tests pass at threshold