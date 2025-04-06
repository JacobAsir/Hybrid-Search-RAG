# Hybrid-Search-RAG

𝗕𝘂𝗶𝗹𝗱𝗶𝗻𝗴 𝗮 𝗛𝘆𝗯𝗿𝗶𝗱 𝗦𝗲𝗮𝗿𝗰𝗵 𝗥𝗮𝗴 𝗦𝘆𝘀𝘁𝗲𝗺 𝘄𝗶𝘁𝗵 𝗣𝗶𝗻𝗲𝗰𝗼𝗻𝗲
(𝗦𝗲𝗺𝗮𝗻𝘁𝗶𝗰 𝗦𝗲𝗮𝗿𝗰𝗵 + 𝗦𝘆𝗻𝘁𝗮𝗰𝘁𝗶𝗰 𝗦𝗲𝗮𝗿𝗰𝗵)

𝗪𝗵𝗮𝘁 𝗶𝘀 𝗛𝘆𝗯𝗿𝗶𝗱 𝗦𝗲𝗮𝗿𝗰𝗵?

Hybrid Search is a powerful search methodology that combines semantic search (dense vector search) and syntactic search (sparse vector search).

𝗦𝗲𝗺𝗮𝗻𝘁𝗶𝗰 𝗦𝗲𝗮𝗿𝗰𝗵: Focuses on understanding the meaning of the query and documents. It uses dense vector embeddings to find results that are conceptually similar to the query, even if the exact keywords don’t match.

𝗦𝘆𝗻𝘁𝗮𝗰𝘁𝗶𝗰 𝗦𝗲𝗮𝗿𝗰𝗵: Relies on keyword matching, using sparse vectors to find exact matches or highly relevant terms.

When a document is stored in a vector database, it is converted into both dense vectors (for semantic search) and sparse matrices (for syntactic search). When a user submits a query, the system retrieves results from both search methods, combines them using techniques like 𝗥𝗲𝗰𝗶𝗽𝗿𝗼𝗰𝗮𝗹 𝗥𝗮𝗻𝗸 𝗙𝘂𝘀𝗶𝗼𝗻, and provides a final ranked response. This hybrid approach ensures that the search results are both contextually relevant and precise.

𝗪𝗵𝗮𝘁 𝗜 𝗕𝘂𝗶𝗹𝘁: 𝗔 𝗛𝘆𝗯𝗿𝗶𝗱 𝗦𝗲𝗮𝗿𝗰𝗵 𝗥𝗮𝗴 𝗦𝘆𝘀𝘁𝗲𝗺

Using 𝗣𝗶𝗻𝗲𝗰𝗼𝗻𝗲 I implemented a hybrid search system that leverages both semantic and syntactic search techniques. Here’s a quick overview of the process:

𝗦𝗲𝘁𝘁𝗶𝗻𝗴 𝗨𝗽 𝗣𝗶𝗻𝗲𝗰𝗼𝗻𝗲:
I initialized a Pinecone client and created a vector index to store both dense and sparse representations of the documents. Pinecone’s serverless infrastructure made it easy to deploy and manage the index.

𝗘𝗺𝗯𝗲𝗱𝗱𝗶𝗻𝗴 𝗮𝗻𝗱 𝗦𝗽𝗮𝗿𝘀𝗲 𝗘𝗻𝗰𝗼𝗱𝗶𝗻𝗴:
For semantic search, I used 𝗛𝘂𝗴𝗴𝗶𝗻𝗴𝗙𝗮𝗰𝗲 𝗲𝗺𝗯𝗲𝗱𝗱𝗶𝗻𝗴𝘀 (all-MiniLM-L6-v2) to generate dense vector representations of the text.
For syntactic search, I implemented 𝗕𝗠𝟮𝟱 𝗲𝗻𝗰𝗼𝗱𝗶𝗻𝗴 to create sparse matrices that capture keyword relevance.

𝗖𝗼𝗺𝗯𝗶𝗻𝗶𝗻𝗴 𝘁𝗵𝗲 𝗥𝗲𝘀𝘂𝗹𝘁𝘀:
Using Pinecone’s 𝗛𝘆𝗯𝗿𝗶𝗱 𝗦𝗲𝗮𝗿𝗰𝗵 𝗥𝗲𝘁𝗿𝗶𝗲𝘃𝗲𝗿, I combined the results from both search methods. This retriever ensures that the final output balances semantic relevance with keyword precision.

By combining the strengths of semantic and syntactic search, hybrid search ensures that users get the most accurate and meaningful results.
