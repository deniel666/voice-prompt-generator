# Voice Prompt Generator Skill

**SOTA Voice Call Prompt Generator** for Claude Code / Cowork.

Create production-ready voice AI prompts for phone calls (inbound/outbound) following 2025-2026 best practices from VAPI, Retell, Bolna, Hume AI, and ElevenLabs.

## Installation

Copy to your Claude skills folder:

```bash
git clone https://github.com/deniel666/voice-prompt-generator.git ~/.claude/skills/voice-prompt-generator
```

## Usage

In Claude Code or Cowork, say:
- "Create a voice prompt for [industry/use case]"
- "Improve this voice prompt: [paste prompt]"
- "Convert this chatbot prompt to voice format"

## Features

- **NO YAPPING Rule**: 2-3 sentences max, under 20 words each
- **Vocal Inflections**: Natural starters (Got it, Makes sense, Hmm)
- **Character Normalization**: Numbers, phones, emails in spoken format
- **Industry Templates**: Fitness, Clinics, Schools, Auto, Tech, Real Estate
- **Quality Checklist**: 100-point scoring system
- **Anti-Patterns**: Common mistakes to avoid

## Key Patterns

1. **First Message**: WHO + WHY in one sentence, under 3 seconds
2. **Response Length**: Never more than 2-3 sentences
3. **Numbers**: Always word form ("one fifty" not "150")
4. **Flow Markers**: `<wait for user response>` for turn-taking
5. **Guardrails Section**: Models prioritize `# Guardrails` heading

## License

MIT
