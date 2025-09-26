# week5--Advanced-RAG-Pipelines-Evaluation
 #Week5-1_RAG_Rerank_ContextOpt.ipynb
The notebook Week5-1_RAG_Rerank_ContextOpt.ipynb builds on the Week 4 RAG setup and extends it with reranking and context optimization features. It begins by preparing a small medical-style demo corpus, tokenizing the text and generating representations with both BM25 and dense embeddings. These two retrieval strategies are then fused together using Reciprocal Rank Fusion (RRF) to improve retrieval robustness. Beyond simple retrieval, the notebook introduces enhancements such as reranking based on simulated cross-encoder scores, maximal marginal relevance (MMR) to balance relevance and diversity in results, and a passage compression function to shorten contexts without losing important information.

To measure effectiveness, the workflow defines four retrieval variants: baseline retrieval, reranking only, compression only, and rerank plus compression. Each variant is evaluated on multiple queries, with metrics collected for recall-like performance, latency, and average context length. Results are organized in a structured DataFrame and visualized through bar charts, making it easy to compare performance across variants.

The notebook also implements a SummarizeValidatorAgent, which validates generated summaries by checking relative lengths and producing basic quality ratings. This provides a lightweight way to assess summary quality alongside retrieval performance. Toward the end, the notebook connects back to Week 4 by rebuilding a Chroma DB of documents, this time using Google Generative AI embeddings, and demonstrates persistence for reuse in later weeks. Finally, it integrates a cross-encoder reranker and a contextual compression retriever, creating a more complete RAG system that not only retrieves but also ranks and optimizes context for efficiency and relevanc

The notebook Week5-2_RAG_Multimodal.ipynb extends your retrieval pipeline by incorporating both text and images into the indexing and query process. It begins with a setup step where project-related images such as context length charts, latency vs recall trade-off graphs, and recall score plots are loaded from a local directory. Each image is tagged with an ID and caption so it can be treated similarly to text documents. Alongside these visuals, a small aligned text corpus is created where each document explicitly references the images. Both text and images are then embedded using placeholder vectors, normalized, and stored for retrieval tasks

Week5-2_RAG_Multimodal.ipynb - …

.

The retrieval system supports three modes. In text-only retrieval, a query embedding is matched against the text corpus and also against the image embeddings, allowing the user to find both documents and visuals relevant to the query. In image-only retrieval, the embedding of a selected image is used to find related documents and other similar images. The notebook demonstrates this by retrieving context length and recall score references when starting from the image img2. Finally, the code assembles a prompt that fuses text and image evidence, showing how multimodal context can be injected into a generation pipeline.

Through practical examples, the notebook shows that text queries like “trend in recall vs latency” bring back both aligned documents and chart captions, while image queries surface related text explanations and companion figures. The design mirrors real-world multimodal retrieval: users can query with text, images, or both, and the system provides contextual evidence across modalities. In this way, the notebook demonstrates how RAG systems can be enriched by combining visual and textual knowledge sources

















