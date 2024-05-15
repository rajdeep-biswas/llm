# llm

## [Building Production-Ready RAG Applications](https://www.youtube.com/watch?v=TRjq7t2Ms5I).

### Challenges with Vanilla RAG -
1. **Low precision**: Not all chunks in retrieved set are relevant (the issue I have faced at work).  
"Precision": of the chunks picked by Retrieval, how many of them were actually relevant?  
Results into hallucination + [Lost in the Middle problems](https://medium.com/@juanc.olamendy/lost-in-the-middle-a-deep-dive-into-rag-and-langchains-solution-3eccfbe65f49) (this is the problem where LLMs tend to lose information that is the middle of a prompt / conversation history).
2. **Low recall**: Even with all relevant chunks retrieved, lacks enough context for LLM to synthesize an answer (low recall would mean the "top K" isn't high enough)
"Recall": of all the relevant chunks, how many were actually picked by Retrieval? (so in this case, not enough information was picked up because of a low K-value)

[Interesting layman explanation of precision and recall analogous to RAG](https://builtin.com/data-science/precision-and-recall)  

### Measuring performance -
Should evaluate retrieval in an isolated manner. If your Retrieval at all is looking at the right documents, that needs to be measured.  
We need to make sure that the stuff that is returned actually does answer the query / is relevant to the question.  
Jerry mentioned "[Retrieval Metrics](https://www.pinecone.io/learn/offline-evaluation/)", and this is the first Google search result I found.  

![Screenshot 2024-05-15 at 2 56 37 PM](https://github.com/rajdeep-biswas/llm/assets/32306614/f1b77f23-7095-47ca-9757-68503f9377b8)

[Precision at K](https://www.evidentlyai.com/ranking-metrics/precision-recall-at-k) measures how many items with the top K positions are relevant.  
MRR = [Mean Reciprocal Rank](https://www.evidentlyai.com/ranking-metrics/mean-reciprocal-rank-mrr).  
NDCG = [Normalized Discounted Cumulative Gain](https://www.evidentlyai.com/ranking-metrics/ndcg-metric).  

This is not an LLM problem, but an IR (Information Retrieval) problem, which has been around for a decade or two.  

Synthetic dataset can be generated. Input: Query, Output: "ID" (or similar) of the relevant document. Use above metrics to measure performance.  

![Screenshot 2024-05-15 at 6 15 28 PM](https://github.com/rajdeep-biswas/llm/assets/32306614/7418217a-27ae-4d47-9235-7ca5f803011b)


### Improving these issues -
1. Store better **Data** along with additional information beyond raw text chunks.
2. Optimize **Embedding** representations.
3. Do better **Retrieval** than top-k semantic lookup.
4. Use LLMs to **Synthesize** 

### Misc facts & points -
* Putting context into the prompt is basically a data pipeline.
* RLHF is a type of finetuning.


## Dump from Keep
Advanced RAG
Query expansion (add related keywords) (https://youtu.be/ewfTtQUvfJU this course has another LLM based technique)

Auto-merging retrieval (forms tree hierarchy) (https://learn.deeplearning.ai/courses/building-evaluating-advanced-rag/lesson/1/introduction)

LLM Ops https://learn.deeplearning.ai/courses/llmops/lesson/1/introduction



Agents
