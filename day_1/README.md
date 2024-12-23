## Day 1 - Prompting with Gemini API

## Overview

This notebook introduces learners to Google's Gemini API and fundamental prompting techniques. Part of a comprehensive 5-day Generative AI course, Day 1 establishes the foundation for working with large language models through practical examples and hands-on exercises.

## Main Topics Covered

### 1. Getting Started with Gemini API

- **Library Installation**: Step-by-step guide to installing the Google Generative AI Library
- **API Configuration**: Process of setting up API keys securely in Kaggle notebooks
- **Initial Setup**: Creating your first model instance and sending basic prompts
- **Response Handling**: Understanding and processing model responses

### 2. Model Selection

- **Available Models**: Overview of Gemini model family (Gemini Pro, Gemini Flash, etc.)
- **Model Capabilities**: Understanding different models' strengths and limitations
- **Parameter Exploration**: Investigating model-specific parameters like token limits
- **Selection Criteria**: Guidelines for choosing the right model for specific tasks

### 3. Generation Parameters

- **Output Control**:
  - Managing response length using `max_output_tokens`
  - Understanding token usage and optimization
- **Temperature Settings**:
  - Fine-tuning output randomness and creativity
  - Practical examples of different temperature values
- **Sampling Parameters**:
  - Using Top-K and Top-P for controlling output diversity
  - Real-world examples showing parameter effects

In order to understand these parameters visually, created Claude artifact: https://claude.site/artifacts/eb268c78-b35f-470e-b8f8-eff0dae282cf

![generation params](screenshots/generation_params.png)

### 4. Prompting Techniques

- **Zero-shot Prompting**

  - Direct task instructions without examples
  - Using enum mode for controlled outputs
  - Best practices for zero-shot prompts

- **One-shot and Few-shot Prompting**

  - Learning from examples in prompts
  - Structured outputs using JSON mode
  - Creating effective example sets

- **Chain of Thought (CoT)**

  - Implementing step-by-step reasoning
  - Comparing direct and CoT approaches
  - When to use CoT for better results

To understand visually, check the Claude artifact: https://claude.site/artifacts/87a714ea-9ac6-4edc-902a-fdd1a3eee9aa

![CoT](screenshots/chain_of_thought.png)

- **ReAct Framework**
  - Combining reasoning with actions
  - Interactive search and response cycles
  - Implementing Thought, Action, Observation patterns
  - Real-world application examples

To understand visually, check the Claude artifact: https://claude.site/artifacts/fb48da4c-e71c-4234-8070-eee06f029ed9

![ReAct part 1](screenshots/react_1.png)

![ReAct part 2](screenshots/react_2.png)

### 5. Code-related Features

- **Code Generation**

  - Techniques for generating clean, functional code
  - Best practices for code-focused prompts
  - Error handling and validation

- **Code Execution**

  - Safe execution of generated code
  - Output analysis and interpretation
  - Debugging and troubleshooting

- **Code Explanation**
  - Breaking down complex code snippets
  - Generating comprehensive documentation
  - Understanding code architecture and patterns

## Additional Resources & References

- **Interactive Tools**:

  - [TextFX](https://textfx.withgoogle.com/): AI-powered tools for creative writing
  - [SQL Talk](https://sql-talk-r5gdynozbq-uc.a.run.app/): Natural language interface for databases
  - [NotebookLM](https://notebooklm.google/): AI research assistant
  - Listen to the [summary podcast episode](https://youtu.be/mQDlCZZsOyo) for this unit (created by NotebookLM, https://notebooklm.google.com/).
  - Listen to the [summary podcast episode](https://youtu.be/F_hJ2Ey4BNc) for this unit (created by NotebookLM).

- **Documentation & Learning**:
  - Read the [Foundational Large Language Models & Text Generation whitepaper](https://www.kaggle.com/whitepaper-foundational-llm-and-text-generation). Also included in this folder.
  - Read the [Prompt Engineering whitepaper](https://www.kaggle.com/whitepaper-prompt-engineering). Also included in this folder.
  - Comprehensive Gemini API documentation
  - Interactive prompt gallery
  - Practical examples in Gemini API cookbook

## Best Practices

- Start with simple prompts and gradually increase complexity
- Experiment with different parameter combinations
- Test generated code thoroughly before implementation
- Keep API keys secure and never share them publicly

This notebook serves as a comprehensive introduction to working with the Gemini API, setting the foundation for more advanced topics in the following days of the course.
