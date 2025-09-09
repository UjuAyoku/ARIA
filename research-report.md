## Problem Statement
Professionals often spend hours searching, reading, and synthesizing information from multiple sources. While conversational agents can answer direct questions, they rarely provide structured, multi-source, and reliable summaries in accessible formats. This project explores whether an autonomous agent pipeline can generate podcast-style audio briefings on arbitrary topics, while addressing challenges of information retrieval, factual accuracy, and delivery.

## Methodology
- Architecture: Built with n8n orchestration for multi-step automation.
- Data Sources: Perplexity AI and Google Search API for retrieval.
- Pipeline:
  1. User submits a query/topic.
  2. System retrieves and aggregates content from multiple sources.
  3. LLM (OpenAI API) synthesizes into a structured summary.
  4. Moderation filters detect harmful/off-topic content.
  5. Text-to-Speech module converts the summary into an audio podcast.
- Evaluation Framework:
  - Information Coverage
  - Factual Accuracy
  - Audio Clarity
 
## Experiments
- Automatic Metrics: ROUGE & BERTScore against gold-standard summaries.
- Human Evaluation (n=25):
  - Accuracy (fact-checking vs source documents).
  - Coherence (logical flow of summary).
  - Usefulness (practical value for decision-making).
- Comparisons:
  - Single-source summaries vs. multi-source retrieval.
  - Raw text output vs. structured summary generation.
 
## Results
- Multi-source retrieval + synthesis achieved +28% improvement in factual accuracy over single-source outputs.
- Human evaluators rated structured audio briefings 1.5 points higher in coherence (0–5 scale).
- Limitation: occasional redundancy in synthesized text and sensitivity to conflicting source data.

## Future Work
- Explore retrieval-augmented generation (RAG) with embeddings for improved factual grounding.
- Experiment with RLHF for optimizing clarity and factuality simultaneously.
- Extend into multi-agent systems where one agent retrieves, another validates, and a third synthesizes.
