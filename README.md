# 5-Day Gen AI Intensive Course with Google

## Prerequisites

- Kaggle Account (phone verified)
- Google API Key from AI Studio
- Basic Python knowledge
- Internet connectivity for API access

## Technical Requirements

- Python 3.10+
- `google-generativeai>=0.8.3`, `tensorflow`, `keras`, `langgraph` libraries
- Kaggle notebook environment.

## Day 1 - Prompt Engineering

Day 1 of Google's Generative AI course focuses on mastering the Gemini API and advanced prompting techniques. The course begins with a comprehensive introduction to the Gemini API setup using Kaggle notebooks, making it accessible for hands-on learning. Participants learn about various prompting techniques, from basic zero-shot prompting to more advanced methods like Chain of Thought (CoT) and the ReAct framework. The course covers essential concepts such as model selection, generation parameters (temperature, top-k, top-p), and output control. A significant portion is dedicated to code-related features, including code generation, execution, and explanation capabilities of the Gemini API. The practical examples and real-world applications, demonstrated through tools like TextFX and SQL Talk, help bridge the gap between theory and implementation. Whether you're new to Gen AI or have experience with other models like ChatGPT, this course provides valuable insights into leveraging Google's Gemini API effectively. The day concludes with comprehensive resources and best practices for continued learning and development.

## Day 2 - Embeddings and Vector Stores/Databases

Day 2 of Google’s Generative AI course dives into embeddings and retrieval-augmented generation (RAG), offering a deep understanding of these foundational components. The day begins with a detailed exploration of embeddings, including text, image, and multimodal embeddings, helping participants understand how these representations capture semantic relationships in vector space. Practical examples walk learners through the classification of embeddings using Keras, highlighting essential techniques for implementing similarity scoring and optimizing vector search. The course also covers Retrieval-Augmented Generation, demonstrating how to use embeddings with RAG for accurate, context-aware document-based Q&A. To bridge theory and application, participants engage with hands-on assignments that reinforce these concepts in real-world scenarios. By the end of the day, participants are well-equipped with tools and techniques to harness embeddings and RAG for enhanced AI solutions.

## Day 3 - Agents

Day 3 of Google's Generative AI course focuses on building intelligent agents and implementing function calling with the Gemini API. The day explores how to create sophisticated AI agents that can interact with external tools and maintain conversational context. Using LangGraph, we learnt how to build stateful graph-based applications, demonstrated through a practical BaristaBot example that handles cafe ordering interactions. The course covers essential concepts like cognitive architectures, tool integration, and orchestration layers, showing how agents can make informed decisions using frameworks like ReAct. Through hands-on assignments, participants implement function calling to create a chat interface over a local database, learning how to bridge AI models with external systems. By the end, participants gain practical experience in building autonomous AI agents capable of complex reasoning and real-world interactions.

## Day 4 - Domain-Specific LLMs

Day 4 of Google's Generative AI course delves into specialized applications of Large Language Models through two key implementations: search grounding and fine-tuning. The day explores how to enhance LLM capabilities by connecting them to verifiable information sources and adapting them for specific tasks. Using the Gemini API, we have learnt to implement search grounding that automatically generates and verifies queries against Google Search results, offering both static and dynamic approaches. The course then covers model fine-tuning techniques, demonstrated through a practical classification task using the 20 Newsgroups dataset. Through hands-on assignments, participants implement both techniques, learning how to evaluate model performance, handle parameter-efficient tuning, and manage token usage effectively. The day's content is grounded in real-world applications, supported by a comprehensive whitepaper that explores how similar techniques are transforming specialized fields like cybersecurity and healthcare. At the end, we all gained practical experience as well as intuition for creating and deploying domain-specific LLM solutions while understanding the broader implications and best practices in specialized AI applications.

## Day 5 - MLOps for Generative AI

Day 5 of Google's Generative AI course focuses on the critical aspects of operationalizing GenAI applications through MLOps best practices and practical implementation strategies. The day centers around a comprehensive whitepaper and demonstration of the GenAI Starter Pack, which serves as a blueprint for bridging the gap between prototyping and production. Using Vertex AI's ecosystem, we explored how to implement sophisticated MLOps practices including continuous evaluation, model monitoring, and governance. The course showcases practical patterns for building production-ready applications through the Starter Pack, which includes a FastAPI server, interactive UI playground, and complete CI/CD infrastructure using Terraform. Through detailed demonstrations, participants learn how to implement RAG patterns, create evaluation pipelines, and establish robust observability frameworks that track user interactions in BigQuery and visualize insights through Looker Studio dashboards. The day's content emphasizes real-world deployment challenges and solutions, supported by comprehensive documentation that explores how Vertex AI's tools and services facilitate enterprise-grade GenAI applications. By the end, participants gain both theoretical understanding and practical experience in deploying GenAI applications at scale while maintaining production-grade reliability, monitoring, and governance standards.
