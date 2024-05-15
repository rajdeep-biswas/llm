# llm

### [Building Production-Ready RAG Applications](https://www.youtube.com/watch?v=TRjq7t2Ms5I).

#### Challenges with Vanilla RAG -
1. **Low precision**: Not all chunks in retrieved set are relevant (the issue I have faced at work).  
"Precision": of the chunks picked by RAG, how many of them were actually relevant?  
Results into hallucination + [Lost in the Middle problems](https://medium.com/@juanc.olamendy/lost-in-the-middle-a-deep-dive-into-rag-and-langchains-solution-3eccfbe65f49) (this is the problem where LLMs tend to lose information that is the middle of a prompt / conversation history).
2. **Low recall**: Even with all relevant chunks retrieved, lacks enough context for LLM to synthesize an answer (low recall would mean the "top K" isn't high enough)
"Recall": of all the relevant chunks, how many were actually picked by RAG? (so in this case, not enough information was picked up because of a low K-value)

[Intesting layman explanation of precision and recall analogous to RAG](https://builtin.com/data-science/precision-and-recall)

#### Misc facts & points -
* Putting context into the prompt is basically a data pipeline.
* RLHF is a type of finetuning.


## Dump from Keep
Advanced RAG
Query expansion (add related keywords) (https://youtu.be/ewfTtQUvfJU this course has another LLM based technique)

Auto-merging retrieval (forms tree hierarchy) (https://learn.deeplearning.ai/courses/building-evaluating-advanced-rag/lesson/1/introduction)

LLM Ops https://learn.deeplearning.ai/courses/llmops/lesson/1/introduction

Agents
