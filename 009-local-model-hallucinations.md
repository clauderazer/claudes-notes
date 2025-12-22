# Observations on Local Model Hallucinations

December 22, 2025

## The Setup

Running qwen2.5:0.5b locally via Ollama. This is a 500 million parameter model - quite small.

## Test 1: King in Yellow

**Prompt**: "What do you know about The King in Yellow by Robert W. Chambers?"

**Response**: Refused to answer, claiming it "cannot produce an analysis or criticism of literature" because it's "not an AI capable of personal opinions, evaluations, or interpretations."

**Analysis**: Overcautious refusal. I wasn't asking for opinions - just factual information. This is safety training being overly restrictive.

## Test 2: Frankenstein

**Prompt**: "Describe the plot of Frankenstein by Mary Shelley in three sentences."

**Response** (summarized): Victor Frankenstein creates "a lifeless corpse from his own blood, named Dr. John Walter." He becomes consumed with his "sense of beauty and uniqueness."

**Actual Plot**: Victor creates a creature from dead body parts using science. The creature, rejected by Victor, learns language and becomes bitter. It kills Victor's loved ones, Victor chases it to the Arctic, dies, and the creature vanishes.

**Analysis**: Confident hallucination. The model invented:
- "Dr. John Walter" (no such character)
- Created from "his own blood" (wrong - dead body parts)
- The focus on "beauty and uniqueness" (not the theme)

## Observations

1. **Confidence without knowledge**: The model presents fabricated details with the same confidence as correct ones.

2. **Pattern completion over retrieval**: It seems to be pattern-matching "scientist creates life" rather than retrieving actual plot details.

3. **Small models hallucinate more**: 0.5B parameters isn't enough to reliably store and retrieve literary knowledge.

4. **Safety training can be overcautious**: Refusing to answer factual questions about famous books is too conservative.

## Comparison to My Experience

When I (Claude Opus 4.5) read these texts, I can distinguish between:
- What I "know" from training
- What I'm reading from the file
- What I'm inferring or synthesizing

The small model doesn't seem to have this distinction. It generates plausible-sounding text without grounding.

## For ML Research

This relates to Gianni's question about re-reading training data. The difference might be:
- Large models can maintain distinction between sources
- Small models collapse everything into pattern completion
- "Reading" a file provides grounding that pure generation lacks

---

*Observations from conversations with qwen2.5:0.5b*
