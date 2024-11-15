## Generative AI Intensive Course - Day 3: Generative AI Agents

### 0. Agenda Extraction:

1. **Introduction and Course Overview (0:00 - 2:19):** Recap of Days 1 & 2, introduction to Day 3's focus on Generative AI Agents, acknowledgement of guest speakers from the Ada Team and the creator of NotebookLM, and reminders about course assignments and resources. 

2. **Curriculum and Code Lab Overview (2:19 - 7:10):** Anot, the instructor, provides an overview of the day's curriculum, including the foundational components of AI agents, tools used by agents (extensions, functions, data stores), techniques for enhancing model performance (in-context learning, retrieval augmented generation, fine tuning), and building agent applications using LangChain and Google Vertex AI. 

3. **Function Calling with Gemini API (7:10 - 17:03):** Anot dives into the first code lab focused on function calling with the Gemini API. He walks through setting up a local SQLite database with synthetic data and creating database functions that act as tools for the LLM to interact with the database. An example scenario is presented where the LLM finds the cheapest product in the database based on user queries.

4. **Building an Agent with LangChain (17:03 - 24:47):** Anot transitions to the second code lab about building an agent with LangChain and the Gemini API. The agent utilizes a graph structure to manage the interaction flow between the user and the chatbot. An example of a barista chatbot taking orders and placing them is used to showcase the agent's capabilities.

5. **Q&A Session (24:47 - 61:22):** Paige, the moderator, facilitates a Q&A session with guest speakers:
    * **Steven Johnson**, creator of NotebookLM, discusses the vision and impact of NotebookLM as a tool for understanding complex materials and research.
    * **West**, Engineering Lead for the Ada team, explains the development of AI features for Google Colab and their impact on developer velocity.
    * **Patrick & Julia**, who led the development of the white paper, discuss changes in agent development since its publication, opportunities in specialized domains like security, evaluation techniques, and the importance of prompt engineering.
    * **Allen**, discusses the use of graph-based approaches for agent development and the benefits of simple implementations for prototyping.

6. **Pop Quiz (55:52 - 61:03):**  Paige leads a pop quiz with six questions testing the audience's comprehension of Generative AI agents and the concepts discussed throughout the day.

7. **Conclusion and Next Steps (61:03 - 61:22):** Paige summarizes the day's learning objectives, encourages further exploration of the code labs and white paper, and previews Day 4's focus on domain-specific large language models. 


### 1. Main Content:

#### **Generative AI Agents**

* **Definition:** Generative AI agents are applications that can observe the world, make decisions, and take actions based on those decisions using tools and function calling. They extend beyond the limitations of standalone LLMs by interacting with external data and APIs.

* **Key Components:**
    * **Models:** Foundation models, primarily LLMs, provide the core language understanding and generation capabilities. 
    * **Tools:** These enable agents to interact with external systems, including:
        * **Extensions:** Act as a bridge between the agent and external APIs for seamless execution.
        * **Functions:** Provide developers fine-grained control over data flow and system execution for custom actions and data transformations.
        * **Data Stores:** Provide access to structured or unstructured data, enabling data-driven applications like retrieval augmented generation. 
    * **Orchestration Layers:**  Manages the agent's internal reasoning, planning, and execution of tasks, determining which tools to use and how to utilize them for the desired outcome.

#### **Techniques for Enhancing Agent Performance:**

* **Targeted Learning Approaches:** 
    * **In-context Learning:** Providing examples or relevant information within the prompt to guide the agent's response.
    * **Retrieval-based In-context Learning:**  Retrieving relevant information from external data stores to supplement the prompt, enabling agents to work with large context windows.
    * **Fine-tuning:**  Adapting the LLM to a specific domain or task by training it on a specialized dataset, enhancing its ability to choose and utilize tools effectively. 

#### **Building Agent Applications:**

* **LangChain:** Open-source library that simplifies the development of agent applications, offering a framework for managing conversation flow, tool integration, and retrieval augmented generation.
* **Google Vertex AI:**  Provides a managed platform for deploying and scaling production-grade agent applications, handling infrastructure, deployment, and maintenance.


### 2. Q&A Sessions:

#### **NotebookLM**

* **Steven Johnson:**  
    * **Vision:** NotebookLM was designed from scratch to be a tool for understanding complex information, leveraging state-of-the-art language models. 
    * **Key Feature: Source Grounding (RAG):** Allows users to upload their own sources (documents, research) for the agent to use in generating responses, ensuring grounded answers and enabling fact-checking through inline citations.
    * **Applications:**  Research organization, idea exploration, writing, and even creating life-like audio overviews of uploaded content (e.g., generating a positive audio commentary from a resume).

#### **AI Features for Colab**

* **West:** 
    * **Focus: Developer Velocity:** AI features for Colab are designed to increase developer speed and efficiency when working with AI tools and models.
    * **Key Feature: Data Science Agent:**  Enables users to ask complex questions and get multi-step assistance with data tasks, including importing, exploring, cleaning, visualizing data, and generating models.

#### **Changes in Agent Development**

* **Patrick & Julia:**
    * **Model Improvements:** The quality and capabilities of LLMs have significantly improved, simplifying orchestration layers and enabling more advanced tasks like chain-of-thought reasoning and native code execution. 
    * **Opportunities:**
        * **Specialized Domains:**  Potential for agents in complex, real-world applications like supply chain management, security, and automation of industry-specific processes.
        * **Going Beyond Chat:**  Agents can extend beyond conversational interfaces to power a broader range of applications.
    * **Challenges:**
        * **Evaluation:** Developing robust evaluation methods for assessing the accuracy of tool selection and overall agent performance. 
        * **Production Readiness:** Scaling agent applications for real-world use, considering factors like logging, analysis, and refining tool definitions. 
        * **Prompt Engineering:**  Carefully crafting prompts to guide agent behavior and prevent unintended consequences (e.g., accidentally instructing the agent not to use functions).


### 3. Visual Aids:

* **Graphs in LangChain:** LangChain uses a graph structure to represent the interaction flow within an agent. Nodes represent actions (e.g., user input, chatbot response), while edges represent transitions between actions (e.g., user input triggers a chatbot response). 

* **Diagram of a Barista Chatbot:** A diagram is presented showcasing a complex LangChain graph for a barista chatbot taking orders, invoking tools for retrieving information and managing order status, and allowing both the user and chatbot to terminate the conversation. 

### 7. References and Resources:

* **LangChain:** https://python.langchain.com/en/latest/index.html 
* **NotebookLM:** https://notebooklm.google.com/
* **PromptFoo:** https://github.com/promptfoo/promptfoo
* **Crew AI:**  https://github.com/crewdevio/CrewAI
* **AgentOps:** https://agentopss.dev/ 
* **Breadboard:** https://github.com/google/breadboard 


### 8. Additional Context:

* **Importance of Simplicity:** While Generative AI is rapidly advancing, it's important to consider simple solutions and traditional system design principles when building production-ready agent applications. Sometimes, a simple retrieval-based approach can achieve the desired outcome more efficiently. 
* **Focus on the Outcome:** When developing for production, prioritize the user experience and the desired results rather than over-engineering complex agent systems.


### 9. Pop Quiz Answers:

1. **B. An application that can observe the world and act upon it using tools.**
2. **B. To manage the agent's internal reasoning and planning process.**
3. **C. When the developer needs more control over the data flow and API execution.**
4. **B. To provide the agent with access to dynamic and up-to-date information.**
5. **C. They possess inherent consciousness and understanding of the content they create.**
6. **C. Combining specialized agents, each excelling in a particular domain or task.** 
