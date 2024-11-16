## Kaggle Generative AI Intensive Course - Day 4: Domain Specific Large Language Models

**0. Agenda Extraction:**

* **Course Overview and Introduction:** Recap of the 5-day Generative AI course structure, including assignments, discussions, and resources. Introduction of the day's topic: Domain-Specific Large Language Models (LLMs).
* **White Paper Review:** Summary of the key concepts covered in the day's white paper focusing on domain-specific models in healthcare (Med-PaLM) and cybersecurity (Sec-LLM).
* **Code Lab Walkthrough:** Explanation of two Colab notebooks: one on Google Search grounding for LLMs and another on parameter-efficient fine-tuning of custom models.
* **Q&A with Experts:** Discussion with experts from the Med-PaLM and Sec-LLM teams about the development, applications, and ethical considerations of these models.
* **Pop Quiz:** A short quiz to assess understanding of the day's material on domain-specific LLMs.

---

**1. Course Overview and Introduction:**

Paige, the instructor, welcomes everyone to day 4 of the Kaggle Generative AI Intensive course, sponsored by Google and the Gemini team. This day focuses on Domain Specific Large Language Models. The 5-day course includes daily assignments (podcasts, white papers), Discord discussions, and additional resources.  Day 4's topic is fine-tuning and customizing LLMs for specific use cases.  Paige introduces Anant, who proceeds to review the curriculum and Colab notebooks.


**2. White Paper Review:**

Anant recaps the first three days: Day 1 covered foundational models, Day 2 focused on embeddings, and Day 3 explored dynamic agents. Day 4 connects these concepts in the context of domain-specific models.

The white paper examines the challenges of healthcare, where accurate diagnosis requires a deep understanding of medical concepts, information retrieval, and reasoning skills.  Med-PaLM addresses this by passing the US Medical Licensing Exam and assisting doctors with tasks like diagnosis and treatment planning. The need for long-form answers, understanding medical records, and engaging in natural dialogues with patients is also highlighted.

Next, the paper shifts to cybersecurity, addressing the "three Ts": threats, toil, and talent. Sec-LLM helps analyze malicious code, automate alert triage, and generate reports, freeing human analysts for strategic tasks.  The paper also explores the unique features of Med-PaLM, Sec-LLM, and Med-Palm 2, emphasizing their training on vast datasets and leveraging planning and reasoning frameworks. Finally, responsible deployment, evaluation for biases, and ethical usage are discussed.

**3. Code Lab Walkthrough:**

**3.1. Colab 1: Google Search Grounding:**

The first Colab demonstrates Google Search grounding to improve accuracy and reduce hallucinations in LLMs. The Colab shows AI Studio UI functionality and then focuses on the API approach.  After initializing the API key and libraries, it demonstrates grounding using standard models augmented with Google Search grounding. This provides sources and citations, enhancing answer quality and attribute segments of answers to specific search results. An example query about Taylor Swift's next concert highlights how grounding provides real-time information that LLMs typically lack.  Adding a "Google Search Retrieval" tool allows the model to find the concert information. The Colab also covers accessing metadata (links, sources) related to generated answers. Static and dynamic grounding are also demonstrated, the latter involving using a threshold to trigger grounding only when needed.

**3.2. Colab 2: Fine-Tuning a Custom Model:**

The second Colab focuses on parameter-efficient fine-tuning using the Gemini model. This involves fine-tuning on a custom corpus to improve performance on unseen tasks. After initialization, the newsgroups text dataset (18,000+ posts on 20 topics) is used for classification. The dataset is cleaned (similar to Day 2), and a small sample (50 rows) is used for training and testing due to the data efficiency of parameter-efficient fine-tuning. A zero-shot classification baseline (without fine-tuning) is established, achieving ~18.75% accuracy.  Fine-tuning the model with 50 examples (input-output pairs) shows significant improvement in classification performance.  Prompt engineering is also recommended for performance improvement.  Finally, fine-tuning reduces the number of generated tokens, resulting in cost savings when using the paid API.

**4. Q&A with Experts:**

Paige introduces experts: Scott and Umesh from Sec-LLM team, Chris from the Med-PaLM team, and Antonio from Google Cloud's Office of the CTO.

**4.1. LLMs for Security:**

*Scott and Umesh*
Scott, who leads the data science research team for Google Cloud Security, discusses the unique challenges of applying LLMs to cybersecurity. He notes the diversity of security tasks, limited publicly available data due to sensitivity, and the potential for LLM activities to trigger safety mechanisms. Specialized models are necessary because generalist models lack expert-level understanding of diverse security data and specialized languages used to pull data.  Scott emphasizes task performance rather than memorization, given the rapidly evolving threat landscape. He explains Sec-LLM development, starting with foundational models, continued pre-training with specialized cybersecurity content, and fine-tuning for specific tasks like analyzing security alerts.  Human alignment is important given the diverse interests of security professionals (threat analysts vs. security operations analysts).  Finally, Lora-based fine-tuning allows specialization for specific customer environments or out-of-distribution tasks.  Specialized models improve accuracy and reduce hallucinations compared to generalist models.

**4.2. Benchmarks like MedQA:**

*Chris*
Chris, working in Google Research on Health AI, discusses the MedQA benchmark and its limitations. MedQA is a multiple-choice test similar to the US Medical Licensing Exam, providing compressed patient information and multiple-choice answers, which simplifies automatic evaluation but lacks real-world complexity.  While achieving 100% on MedQA is possible, it might indicate memorization rather than true medical reasoning. He hopes for more sophisticated benchmarks closer to reality, like medical imaging tasks and "hard case" challenges requiring diagnosis or treatment recommendations based on full patient scenarios.

**4.3. Trade-offs Between General-Purpose and Fine-Tuned Models:**

*Antonio*
Antonio, from Google Cloud's Office of the CTO, addresses trade-offs between general-purpose and fine-tuned models.  He points out the increasing size and complexity-handling capabilities of models like Gemini Pro, as well as the efficiency of smaller, domain-specific models. Trade-offs involve balancing answer quality, cost, and latency.  Fine-tuning adapts pre-trained models to specific domains, offering semi-static adaptation.  Dynamic approaches like retrieval augmentation, search-based methods, and in-context learning with caching provide more real-time information.  The optimal approach depends on the specific use case.

**4.4. A Single Superior Model for Health Problems:**

*Chris*
Chris argues against a single model solving all health problems, highlighting historical healthcare advancements. He emphasizes that current LLM use cases in healthcare often focus on efficiency improvements, like assisting doctors with replies or patient education.  He anticipates significant scientific discoveries and new care pathways enabled by LLMs.  Incremental improvements are important, but he emphasizes the need to explore new possibilities enabled by models like Gemini and Med-PaLM.

**4.5. Adversarial Field and LLM Deployment Strategies:**

*Scott and Umesh*
Scott and Umesh discuss the adversarial nature of security and its impact on LLM deployment.  Evasion papers highlighted ML vulnerabilities over a decade ago, and LLMs represent a new attack surface.  Umesh emphasizes the need to consider the security implications of dependencies on external sources (open-source libraries, user input, training data).  Prompt injection is a significant challenge due to the use of natural language for both user input and LLM programming. Techniques like training for resistance, heuristic input scanning, and decomposing problems into smaller parts are being explored.

**4.6. Most Effective Use of LLMs in Security:**

*Umesh and Scott*
Umesh and Scott discuss effective LLM applications in security.  Umesh highlights the power of procedural knowledge over factual knowledge, emphasizing a grounding approach for factual information. LLMs improve workflows by automating tasks up to 70%, leaving complex judgments, tool usage, and iterative analysis to humans.  Code analysis and code generation are other effective areas, particularly addressing cloud misconfigurations.  Scott emphasizes the LLM's role as connective tissue among diverse security systems and data silos, enabling coherent combination of heterogeneous data.  LLMs offer flexibility at the company level, eliminating the need for company-specific rules.

**4.7. Major Gap in LLM Capabilities for Security:**

*Scott and Umesh*
Scott notes the inherent skepticism of cybersecurity professionals and the challenge of explainability and trust in ML.  LLMs introduce a new dimension to this, and while grounding through citations offers some solution, verifying this information requires significant human effort, particularly in technical fields.  He identifies a gap in shortening verification time and providing a deeper understanding of model confidence, potentially incorporating confidence in underlying data and reasoning. Umesh adds that the ability to effectively use existing tools and APIs is critical for security problem-solving. Current tool use by LLMs is rudimentary, requiring significant hand-tuning, especially for APIs with complex schemas. Cracking this nut and enabling scalable tool handling would be transformative.


**4.8. Ethical Considerations in Healthcare LLMs:**

*Chris*
Chris addresses ethical considerations in developing specialized healthcare LLMs.  For deployment, local regulations like HIPAA compliance ensure patient data privacy during serving time. For training, de-identified or synthetic data are used, adhering to standards for patient privacy and improving data hygiene by reducing noise from individual details.  He stresses the importance of abstraction through de-identification and aggregation for model performance and data privacy.

**4.9. Med-PaLM Evolution:**

*Chris*
Chris discusses the evolution of Med-PaLM, referencing the white paper on diagnosing depression and PTSD from patient interview transcripts. While performance was decent and has improved, the ultimate goal is to improve patient outcomes by helping them take the best next steps, beyond just diagnosis. Research focuses on LLMs participating in conversations, but clinical studies are needed to demonstrate real-life impact.


**5. Pop Quiz:**

The pop quiz covers domain-specific LLMs.

1. **Med-PaLM's Primary Goal:** The answer is C, to improve health outcomes by making advanced AI technology available to healthcare professionals.
2. **Significance of Ensemble Refinement (ER) in Med-PaLM V2:** The answer is D, to enhance reasoning and answer refinement by conditioning on multiple generated reason pathways.
3. **Sec-LLM's Innovative Approach:** The answer is C, to combine LLMs, authoritative data sources, and a flexible planning framework.
4. **Sec-LLM's Approach to Limited Security Data:** The answer is B, developing specialized LLMs trained on cybersecurity-specific content and tasks.


**6. Conclusion:**

Paige concludes the session, highlighting topics covered during the week (prompting, LLMs for specific tasks, function calling, retrieval, vector databases, fine-tuning, domain-specific models) and looking ahead to the final day's focus on evaluations and MLOps.

---


