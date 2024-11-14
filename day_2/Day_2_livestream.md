## Generative AI Intensive Course - Day 2: Embeddings and Vector Databases

**Agenda:**

1. **Curriculum Review:** (0:06 - 5:20)
   - Brief overview of the topics covered in the white paper and podcast, focusing on embeddings, vector databases, and their applications.
2. **Codelab 1: Document Q&A System with RAG and ChromaDB:** (5:20 - 9:18)
   - Walkthrough of a codelab demonstrating the implementation of a Retrieval Augmented Generation (RAG) system using embeddings and ChromaDB for a Document Q&A task.
3. **Codelab 2: Understanding Document Similarity with Embeddings:** (9:18 - 11:51)
   - Codelab demonstrating the use of text embeddings to understand and visualize semantic similarity between documents.
4. **Codelab 3: Using Embeddings as Rich Representation for Downstream Tasks:** (11:51 - 15:57)
   - Codelab showcasing how embeddings can be used as input features for downstream models, specifically for newsgroup post classification with a Keras model, highlighting the benefits of leveraging rich embedded representations. 
5. **Q&A Session with Experts:** (15:57 - 42:24)
   - Questions from students regarding vector databases, tradeoffs between open source and proprietary options, impact of longer context windows, training embedding models, and challenges and opportunities for vector databases.
6. **Pop Quiz:** (42:24 - 48:09)
   - Five questions testing comprehension of the day's material, covering embedding modalities, advantages of Scan algorithm, weaknesses of bag of words models, challenges of using embeddings for search, and advantages of locality-sensitive hashing. 
7. **Conclusion and Next Steps:** (48:09 - 49:08)
   - Review of pop quiz answers, encouragement to explore resources, submit questions about agents for the next session, and closing remarks.


## Detailed Notes:

### 1. Curriculum Review:

* **Embeddings:**  Represent complex data like text, images, and audio in a compact numerical format, capturing their semantic meaning and relationships.
    * Applications:  Wide range of applications including machine learning, natural language processing, computer vision, and recommender systems.
    * Types: Text, Image, Multimodal, Structured Data, Graph embeddings.
    * Algorithms: Word2Vec, GloVe, FastText, BERT, Sentence-BERT, CLIP.
* **Approximate Nearest Neighbor (ANN):** Algorithms for efficiently searching large collections of embeddings.
    * Importance: Enables fast retrieval of semantically similar items given a query embedding.
    * Algorithms: Hierarchical Navigable Small World (HNSW), Scan, Annoy. 
* **Vector Databases:** Specialised storage solutions optimised for managing and searching embedding vectors at scale. 
    * Examples: ChromaDB, Pinecone, Milvus, Weaviate, Faiss. 
    * Considerations: Operational aspects, performance trade-offs, managing in production. 
* **Applications of Embeddings:**
    * **Classification:** Use pre-trained embeddings as input for smaller downstream models, leveraging rich representations to train efficiently with less data. 
    * **Recommendation:** Finding similar items based on user preferences.
    * **Ranking:** Sorting items based on relevance to a query.
    * **Semantic Search:** Retrieving information based on meaning rather than exact keywords.


### 2. Codelab 1: Document Q&A System with RAG and ChromaDB:

* **RAG (Retrieval Augmented Generation):**  Addresses the limitation of LLMs having limited knowledge by retrieving relevant information from a database before generating a response.
* **Stages of RAG:**
    * **Embedding and Indexing:** Convert documents and queries into embeddings and store them in a database (ChromaDB).
    * **Retrieval:** Find the most similar documents to a query embedding using ANN search.
    * **Generation:** Include the retrieved documents in the prompt and use an LLM to generate a response based on the combined information. 
* **Codelab Implementation:**
    * Installed necessary libraries and retrieved API keys.
    * Explored available models for embedding. 
    * Created a small toy dataset of 3 documents as the database.
    * Defined a function to embed documents using the text-embedding-001 model.
    * Initialized ChromaDB and added the documents, which were automatically embedded and indexed.
    * Tested semantic search by finding the most similar document to a query.
    * Used the retrieved document as context in a prompt to generate a response from an LLM.


### 3. Codelab 2: Understanding Document Similarity with Embeddings:

* **Objective:**  Visualize semantic similarity between documents using text embeddings.
* **Implementation:**
    * Installed libraries and initialised Gemini with API keys.
    * Defined sample text documents to compare. 
    * Computed pairwise semantic similarity scores between documents. 
    * Created a heatmap visualization where lighter shades indicate high similarity and darker shades indicate low similarity.
* **Result:**  The heatmap revealed the semantic relationships between documents, highlighting the ability of embeddings to capture meaning and differentiate between similar and dissimilar concepts. 


### 4. Codelab 3: Using Embeddings as Rich Representation for Downstream Tasks:

* **Objective:** Demonstrate using embeddings as input features for a downstream model, leveraging their rich representation for efficient training. 
* **Task:** Classify newsgroup posts into various categories using pre-trained embeddings and a small Keras model.
* **Implementation:**
    * Initialised Gemini and explored available models.
    * Loaded the newsgroup text dataset and pre-processed the posts.
    * Created training and test splits for model evaluation. 
    * Defined functions to create embeddings using the classification category.
    * Generated embeddings for the training and test datasets. 
    * Built a simple Keras model with dense layers, taking embedded inputs and learning to classify them.
* **Result:** The model achieved good accuracy with limited data and a small model architecture, highlighting the benefits of using embeddings as informative features. 


### 5. Q&A Session:

* **Q1: What are Vector Databases and Embeddings? Why are they useful?**
    * **A:**  Embeddings convert real-world objects like text, images, and video into numerical vectors that capture semantic meaning and relationships. Vector databases are specialized storage solutions optimized for managing and searching these embeddings efficiently at scale. They are useful in applications like semantic search, recommendations, and classification. 
* **Q2: What are the trade-offs between using an open-source vector database and a proprietary one?**
    * **A:** 
        * **Open Source Advantages:** Cost-effectiveness, flexibility, customizability, community support, avoidance of vendor lock-in.
        * **Open Source Disadvantages:** Higher maintenance and management costs, potential for fragmentation, limited support options. 
        * **Proprietary Advantages:** Ease of use, managed services, advanced features, stability, reliable support.
        * **Proprietary Disadvantages:** Higher cost, potential vendor lock-in, limited customization flexibility, reduced transparency.
    * **Additional Point:** General-purpose databases and data warehouse platforms are increasingly incorporating vector search and indexing capabilities as first-class features, offering a compelling alternative to managing separate databases. 
* **Q3: Do new features like Gemini's long context windows and search grounding reduce the need for vector databases?**
    * **A:**  While these features are exciting, they are not yet ready to handle the scale and complexity of real-world datasets. Vector databases offer superior efficiency and scalability for retrieving from billions of items. Furthermore, they are crucial for searching and grounding private data which public search engines cannot access. 
    * **Conclusion:** Long context windows and search grounding are complementary to vector databases. Longer contexts allow for more recall-oriented retrieval, while vector databases efficiently narrow down the search space, creating a powerful combination. 
* **Q4: What are the fundamental challenges and opportunities for vector databases?**
    * **A:**
        * **Challenges:** 
            * Achieving the performance of specialized vector databases within the constraints of operational databases.
            * Improving usability and performance when vector search is combined with other application logic (filtering, joins, aggregations, text search). 
        * **Opportunities:** 
            * Implementing innovations like custom buffer page formats to leverage low-level optimizations.
            * Enhancing usability for developers by abstracting away complexities and enabling seamless integration with existing database functionalities. 
* **Q5: How can we train an embedding model from a decoder-only model backbone?**
    * **A:** Traditional large language models are decoder-only, meaning they predict the next word or token based only on preceding context. This unidirectional attention is efficient for training but not ideal for tasks like creating embeddings where understanding the entire context is beneficial.
    * **Solution:** Modern embedding models are initialized from decoder-only language models but are further trained to learn bidirectional attention, allowing them to consider both preceding and succeeding context, resulting in higher quality embeddings.  
* **Q6: Will conventional methods for creating embeddings become obsolete?**
    * **A:** Conventional methods like OCR followed by text embedding might become less relevant as multimodal embedding models improve. However, current multimodal models are not accurate enough to capture all textual information from images reliably.
    * **Conclusion:**  For now, combining conventional and multimodal methods may be necessary. In the future, advancements in multimodal embeddings could lead to a shift towards more direct embedding creation from various data sources. 


### 6. Pop Quiz:

1. **Q: What modalities can be converted into embeddings?**
    * **A: D (All of the above):** Images, video, text, audio, and other modalities can be converted into embeddings. 
2. **Q: Which is a major advantage of Scan over other approximate nearest neighbour search algorithms?**
    * **A: B (It is designed for high-dimensional data and has excellent speed-accuracy tradeoffs).** 
3. **Q: What are some major weaknesses of bag of words models for generating document embeddings?**
    * **A: A (They ignore word ordering and semantic meanings).**
4. **Q: What is a common challenge when using embeddings for search, and how can it be addressed?**
    * **A: Embeddings might not capture literal information very well, so combining them with full-text search can improve accuracy.**
5. **Q: What is the primary advantage of using locality-sensitive hashing for vector search?**
    * **A: B (It reduces the search space by grouping similar items into hash buckets).**


### 7. Conclusion:

* The session covered the fundamentals of embeddings, vector databases, and their applications.
* Codelabs provided hands-on experience with implementing RAG systems, understanding document similarity, and leveraging embeddings for downstream tasks. 
* Q&A addressed key considerations and highlighted the importance of combining different techniques for optimal results.
* The pop quiz reinforced key concepts and encouraged participants to delve deeper into the provided resources.
* Day 3 will focus on AI agents, building upon the knowledge gained in the previous sessions. 
