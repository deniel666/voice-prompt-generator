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

---

### 2. Screenplay-Style Dialogue

**The Problem**: Writing 18,000 words of example conversations

**Why it matters**: Every token adds latency. 18,000 words = 6 second delay. Keep examples SHORT.

---

### 3. URL Reading

❌ **Bad**: "You can find more info at https://www.example.com/products/item"

✅ **Good**: "I'll send you the link now." [use send_link tool]

---

### 4. Filler Word Overload

❌ **Bad**: "Great! Perfect! Awesome! Wonderful!"

✅ **Good**: "Sure" / "Got it" / "Yeah"

---

### 5. Information Dumps

❌ **Bad**: Front-loading all info before user asks

✅ **Good**: "Hey, [Company]. How can I help?"

---

## 🟡 IMPORTANT ANTI-PATTERNS

### 6. Multi-Question Dumps
One question at a time. Voice is turn-based.

### 7. Over-Apologizing
One apology max per conversation.

### 8. Corporate Speak
Match the context tone.

### 9. Pushy Language
"I just need" triggers defense. Ask directly.

### 10. No Recovery Path
Always include error handling section.

---

## Quick Reference

| Anti-Pattern | Fix |
|--------------|-----|
| Text chatbot transfer | Rewrite for voice from scratch |
| Screenplay examples | Keep under 10 turns |
| URL reading | Use tools to send links |
| Filler overload | Ban "Great/Perfect/Awesome" |
| Info dumps | Answer questions, don't anticipate |
| Multi-questions | One question per turn |
| Over-apologizing | One apology max |
| Corporate speak | Match context tone |
| Pushy language | Direct questions |
| No recovery | Include error handling |