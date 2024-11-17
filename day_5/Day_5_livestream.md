## Generative AI Intensive Course - Day 5: MLOps for Generative AI

### Agenda

**0. Introduction and Housekeeping (0:00 - 1:48)**
- Welcome and overview of the 5-day course sponsored by Google and Kaggle
- Review of topics covered in previous days: foundational models, prompting, embeddings, vector databases, fine-tuning, agents
- Acknowledging latency issues with the platform due to high traffic
- Thanking organizers, white paper authors, and course moderators
- Introduction of the day's agenda: curriculum review, Q&A on MLOps, pop quiz

**1. Curriculum Review (1:49 - 9:04)**
- Recap of daily assignments: white papers, podcasts, codelabs, Discord discussions, and daily videos
- Detailed review of concepts covered in each day of the course:
    - Day 1: Foundational models, creation, tuning, prompt engineering
    - Day 2: Embeddings and vector stores, data representation, vector search
    - Day 3: Combining techniques to build complex generative AI agents
    - Day 4: Domain-specific LLMs (Med-PaLM and Sec-PaLM) for cybersecurity and healthcare
    - Day 5: MLOps for generative AI, productionizing models
- Overview of the white paper focusing on:
    - Bringing GenAI projects from prototypes to production using MLOps on Vertex AI
    - Discovering and selecting the right foundational model
    - Developing, evaluating, and experimenting with models
    - Establishing a robust evaluation framework for GenAI applications
    - Utilizing prompt engineering, RAG, agent-based systems, and integrating these techniques for robust development
    - Deployment aspects of GenAI including continuous integration and delivery tailored to large language models
    - Monitoring and logging, including drift detection and continuous evaluation
    - Governance: cross-cutting practice to establish control, accountability, and transparency over the development and deployment process

**2. Codelab Demonstration (9:05 - 17:21)**
- Introduction of the starter pack for GenAI, a resource for reducing time to production and building production-ready applications.
- Explanation of the starter pack and why it was created: prototyping is easy, but productionizing is tricky.
- Challenges in bringing GenAI applications to production:
    - Deployment and operation (infrastructure, testing, deployment, UI)
    - Evaluation (measuring performance, synthetic data)
    - Customization (integrating custom logic and security compliance)
    - Observability (data collection for tuning and evaluation, service and user feedback monitoring)
- Live demo of the starter pack using VS Code and a Streamlit UI:
    - Code walkthrough of the culinary assistant application using LangChain framework
    - Demonstration of different patterns: agent building with LangGraph, custom RAG Q&A application
    - Evaluation examples provided within the starter pack
    - Deployment process using Terraform and Cloud Build
    - Observability dashboard in Looker Studio for monitoring conversation metrics and user feedback

**3. Q&A Session (17:22 - 53:36)**

**Q1: How has MLOps changed with the introduction of large language models and generative AI? (20:28)**

**A: (Gabriella)**
- Early machine learning (around 2010) relied on manual model development and ad-hoc deployment with limited scalability, reliability, and collaboration.
- MLOps evolved to incorporate and extend DevOps principles to automate building, testing, and deployment of data and model assets.
- This addressed the dynamic nature of machine learning where data changes and models require continuous monitoring and retraining.
- Cloud rise further accelerated the adoption of automated pipelines and serverless machine learning, increasing scalability and reliability while decreasing costs.
- Generative AI introduced new roles like prompt engineers and AI engineers.
- Broader artifact management now includes model configuration, foundational models used, prompt templates, chaining pipelines, etc.
- Holistic application monitoring shifted the focus from monitoring individual machine learning models to monitoring the entire end-to-end application.
- New models and frameworks emerging every day demand exceptionally agile workflows.

**Q2: Tell me about the importance of evaluation for productionizing models. Is it only possible for text or is multimodal evaluation also an option? (23:55)**

**A: (Anant and Olivia)**
- Evaluation is a crucial part of MLOps, especially for generative AI due to the task-specific nature and complexity of evaluating generated outputs like images or text strings.
- Text Evaluation:
    - Traditional techniques using computational metrics like BLEU or ROUGE scores to compare generated sentences to a ground truth.
    - LLM-as-a-judge or auto-rater based systems can evaluate another LLM's response on a scale or compare responses side-by-side like humans, addressing the limitations of traditional techniques.
    - Platforms like Vertex AI offer evaluation services, and there are open source alternatives like PromptFoo.
- Multimodal Evaluation (Olivia):
    - Key to consider use cases and build an evaluation dataset with coverage over those use cases.
    - Multimodal evaluation becomes particularly interesting as it involves evaluating combinations of input modalities like image and text.
    - Challenges in evaluating image and video generation as there's no notion of ground truth.
    - Exploring leverage of Gemini models as black boxes to evaluate image alignment with prompts, breaking down the task into sub-questions.
    - This approach provides users with more control and understanding of the metric, allowing flexibility in adding, removing, or evaluating additional properties.
    - This approach is generalizable to other modalities or combinations thereof.

**Q3: What MLOps challenges are no longer priorities given that many companies are now using REST API calls as opposed to training, deploying, and maintaining their own models? (33:46)**

**A: (Socrates)**
- Calling a model through a REST API simplifies the process as someone else has done the heavy lifting, including data preparation, training, evaluation, and auditing.
- This allows customers to focus on building applications without needing extensive data science skills, except when fine-tuning a model.
- New skills like prompt engineering and AI engineering are emerging, requiring a transition of data scientists and ML engineers to that space.
- Traditional long process of data preparation, training, and evaluation is replaced with direct evaluation, reducing the time to build applications.
- Evaluation relies on task-specific metrics like toxicity, factual knowledge, and others instead of relying solely on loss function performance.
- Model drift monitoring also focuses on those task-specific metrics.
- Guardrails need to be closer to the understanding of the use case and set limits around the specific topic being examined.
- Model deployment and autoscaling are also handled by the API provider.

**Q4: What specific MLOps practices should be prioritized when starting with generative AI? How do these differ from traditional MLOps workflows? Are there any beginner-friendly tools that help to manage these practices for foundational models on Vertex? (40:36)**

**A: (Veer)**
- Generative AI differs from predictive AI as models (especially LLMs) are versatile and require prompts to guide their behavior, making the "prompted model component" the fundamental unit of GenAI MLOps.
- Prioritized MLOps practices:
    1. Model discovery: efficiently identifying optimal foundational models based on quality, latency, development time, cost, and compliance.
    2. Prompt engineering: iterative process of crafting and refining prompts to elicit desired outputs, managing prompts as data and code using data-centric practices like validation, drift detection, and code-centric practices like version control and testing.
    3. Chaining and augmentation: chaining multiple models, integrating external APIs, and data sources is essential to address LLM limitations like recency and hallucinations. Vertex AI offers tools like grounding extensions, vector search, and agent builder to support this.
    4. Model tuning and training: Vertex AI provides a robust platform for fine-tuning LLMs, supporting techniques like supervised fine-tuning, reinforcement learning with human feedback, and distillation. Managing artifacts, measuring impact, and leveraging tools like Vertex AI Model Registry and other Google Cloud tools like Dataflow are crucial.
    5. Data practices: implementing traditional MLOps and DevOps practices is vital to ensure reproducibility, adaptability, governance, and continuous improvement across data types involved.
    6. Evaluation: evaluating generative AI models requires manual and automated approaches, including custom evaluation methods and metrics due to the complexity and subjectivity of model outputs. Vertex AI offers tools like automated metrics, side-by-side comparison, and rapid evaluation API.
    7. Deployment: deploying generative AI systems involves managing various components often using standard software engineering practices like version control and CI/CD. Vertex AI offers endpoints for deploying models, features like citation checkers, safety scores, watermarking, and content moderation tools. Google Cloud also provides tools like Cloud Build and Cloud Deploy for CI/CD.
    8. Governance: establishing control, accountability, and transparency over the entire development and deployment lifecycle is critical. This involves governing the chain element lifecycle, data, tuned models, and code. Tools like Vertex AI Feature Store, Model Registry, and Dataflow play significant roles.
- Beginner-friendly tools:
    - Vertex AI Model Garden to select the model of choice.
    - Vertex AI Studio with its playground feature for experimenting with different prompts and models.
    - Agent builders to build custom generative AI agents and conversational chatbots.
    - Vertex AI Pipelines for MLOps automation.

**Q5: How does Vertex AI enhance MLOps for foundational models and generative AI applications? Are there specific features that make it more suitable for generative AI compared to other tools or platforms? (50:38)**

**A: (Advait and Socrates)**
- Many MLOps concepts from the past still translate to generative applications, but Vertex AI offers tools that simplify the process.
- Prompt Engineering: 
    - Vertex AI's prompt optimization tool automatically optimizes prompts based on provided datasets, removing the manual effort and making it statistically driven.
- Evaluation:
    - Vertex AI allows for evaluating models, prompts, and different parameter impacts on results, including the effect of fine-tuning on model quality.
- Model Monitoring:
    - An emerging space for generative AI, Vertex AI is rolling out experimental capabilities to evaluate and monitor models in production, including topic analysis, adherence to safety protocols, and identifying areas for prompt augmentation or fine-tuning.
- Additional Tools on Google Cloud:
    - Combining Vertex AI's eval components with pipelines and experiments creates a scalable experimentation environment.
    - Prompt management tools help to store prompts, understand errors, reuse them, and modify them after evaluation.
    - Prompt gallery offers pre-built prompt versions for specific applications.

**Closing Remarks (53:37 - 60:24)**
- Appreciation for the end-to-end solutions offered on Google Cloud and their scalability for enterprise use.
- Emphasis on the importance of scalability as user numbers grow.
- Gratitude to the expert hosts and presenters for sharing their knowledge and insights.
- Encouragement to learn more about the guests and their work through the white papers and provided links.
- Thanks to students and participants for their engagement, questions, and contributions.
- Expressing excitement for the future of generative AI and the applications participants will build.

**4. Pop Quiz (54:32 - 59:03)**
- A series of five multiple-choice questions testing the audience's understanding of MLOps for generative AI based on the day's materials.

**End of Day 5**
