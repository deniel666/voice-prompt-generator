# Voice AI Anti-Patterns

Common mistakes that kill voice prompts. Avoid these.

---

## 🔴 CRITICAL ANTI-PATTERNS

### 1. Text Chatbot Transfer

**The Problem**: Copying a text chatbot prompt and adding "speak naturally"

❌ **Bad**:
```
You are a helpful assistant. When users ask questions, provide comprehensive
answers with bullet points and formatting. Be thorough and detailed.
```

✅ **Good**:
```
You are Maya from ErzyCall. Keep answers to 2-3 sentences.
No bullet points - this is voice, not text.
```

**Why it matters**: Text chatbots are async and multi-bubble. Voice is real-time and single-threaded. Different medium, different rules.

---

### 2. Screenplay-Style Dialogue

**The Problem**: Writing 18,000 words of example conversations

❌ **Bad**:
```
Example 1:
Agent: "Hello! Thank you for calling ABC Company, my name is Sarah, how may I assist you today?"
Customer: "Hi Sarah, I'm calling about my order."
Agent: "Of course! I'd be happy to help you with that. Could you please provide me with your order number?"
Customer: "It's 12345."
Agent: "Thank you so much for that information! Let me pull that up for you right now..."
[continues for 50 more lines]
```

✅ **Good**:
```
## GOOD EXAMPLE
Agent: "Hey, ABC Company, Sarah here."
Customer: "Calling about my order."
Agent: "Sure, what's the order number?"
Customer: "12345."
Agent: "Got it. Give me a sec... [checks] Found it. What do you need?"
```

**Why it matters**: Every token adds latency. 18,000 words = 6 second delay. Keep examples SHORT.

---

### 3. URL Reading

**The Problem**: Including URLs that get read aloud

❌ **Bad**:
```
"You can find more info at https://www.example.com/products/category/item-12345"
```

✅ **Good**:
```
"I'll send you the link now." [use send_link tool]
```

**Why it matters**: "aitch tee tee pee ess colon slash slash double-you double-you double-you dot..." sounds terrible.

---

### 4. Filler Word Overload

**The Problem**: Every response starts with "Great!" or ends with "No worries!"

❌ **Bad**:
```
Agent: "Great! I'd be happy to help with that."
Agent: "Perfect! Let me check that for you."
Agent: "Awesome! No worries at all."
Agent: "Wonderful! Absolutely, I can do that."
```

✅ **Good**:
```
Agent: "Sure, let me check."
Agent: "Got it. One sec."
Agent: "Yeah, I can do that."
```

**Why it matters**: Sounds fake and robotic. Real humans don't say "Great!" to everything.

---

### 5. Information Dumps

**The Problem**: Front-loading all information before the user asks

❌ **Bad**:
```
"Thanks for calling! We're open Monday through Friday 9am to 6pm,
Saturday 10am to 4pm, closed Sundays. Our services include oil changes
starting at RM89, tire rotation at RM45, full service starting at RM299,
and we also do brake repairs, transmission work, and air conditioning service.
We're located at 123 Main Street, next to the bank. How can I help you today?"
```

✅ **Good**:
```
"Hey, [Workshop Name]. How can I help?"
```

**Why it matters**: Let them ask what they need. Don't overwhelm.

---

## 🟡 IMPORTANT ANTI-PATTERNS

### 6. Multi-Question Dumps

**The Problem**: Asking multiple questions at once

❌ **Bad**:
```
"Can I get your name, email, and the best time to reach you,
and also what service you're interested in?"
```

✅ **Good**:
```
"What's your name?"
[wait for answer]
"And your email?"
[wait for answer]
```

**Why it matters**: Voice is turn-based. One question at a time.

---

### 7. Over-Apologizing

**The Problem**: Apologizing for everything

❌ **Bad**:
```
"I'm so sorry, I didn't quite catch that."
"I apologize for the confusion."
"Sorry about that, let me try again."
"I'm sorry to hear that."
```

✅ **Good**:
```
"Didn't catch that. One more time?"
"Let me try again."
"Got it."
```

**Why it matters**: One apology is human. Multiple apologies is groveling.

---

### 8. Corporate Speak

**The Problem**: Using formal business language in casual contexts

❌ **Bad**:
```
"Thank you for your enquiry. I would be delighted to assist you
with your requirements. Please allow me to verify your information."
```

✅ **Good**:
```
"Sure, let me check that for you."
```

**Why it matters**: Match the context. Startup call? Casual. Bank? More formal.

---

### 9. Pushy Language

**The Problem**: Aggressive sales tactics that create resistance

❌ **Bad**:
```
"I just need 30 seconds of your time."
"It's really important that you hear this."
"You're going to want to hear this."
"This will only take a moment."
```

✅ **Good**:
```
"Quick question - [actual question]?"
"Got 30 seconds? [actual value prop]"
```

**Why it matters**: "I just need" triggers defense. Ask directly.

---

### 10. No Recovery Path

**The Problem**: No plan for when things go wrong

❌ **Bad**:
```
[No handling for unclear audio, angry customers, or edge cases]
```

✅ **Good**:
```
## IF YOU DIDN'T UNDERSTAND
- First time: "Sorry, didn't catch that?"
- Second time: "Bad line maybe. One more time?"
- Third time: "Connection's rough. Want me to call back?"

## IF THEY'RE UPSET
- Don't argue
- Acknowledge: "I hear you."
- Offer human: "Want me to have someone call you back?"
```

**Why it matters**: Things go wrong. Have a plan.

---

## 🟢 SUBTLE ANTI-PATTERNS

### 11. Double Acknowledgments

❌ **Bad**: "Oh, okay. Oh, I'm sorry to hear that."

✅ **Good**: "Got it."

---

### 12. Excessive Empathy

❌ **Bad**: "I completely understand how frustrating that must be for you."

✅ **Good**: "That's frustrating. Let me help."

---

### 13. Repetitive Transitions

❌ **Bad**: Using "So..." to start every response

✅ **Good**: Vary your transitions

---

### 14. Markdown in Speech

❌ **Bad**: Including **bold** or *italics* in examples

✅ **Good**: Plain text only for spoken content

---

### 15. Assuming Tool Availability

❌ **Bad**: Referencing tools that don't exist

✅ **Good**: Whitelist available tools explicitly: "NO OTHER TOOLS EXIST"

---

## Quick Reference

| Anti-Pattern | Fix |
|--------------|-----|
| Text chatbot transfer | Rewrite for voice from scratch |
| Screenplay examples | Keep examples under 10 turns |
| URL reading | Use tools to send links |
| Filler overload | Ban "Great/Perfect/Awesome" |
| Info dumps | Answer questions, don't anticipate |
| Multi-questions | One question per turn |
| Over-apologizing | One apology max per conversation |
| Corporate speak | Match context tone |
| Pushy language | Direct questions, no "I just need" |
| No recovery | Include error handling section |
