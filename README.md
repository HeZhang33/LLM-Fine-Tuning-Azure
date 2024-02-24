# LLM Fine-Tuning using Azure 
A fine-tuning guide for both OpenAI and Open-Source Large Lauguage Models on Azure.

## What
Fine-Tuning, or *Supervised Fine-Tuning*, retrains an existing pre-trained LLM using example data, resulting in a new "custom" fine-tuned LLM that has been optimized for the provided task-specific examples. 
<ol><img src="labs/images/screenshot-fine-tuning-illustration-diagram.png" alt="Screenshot of What is Fine-Tuning illustration diagram." width="600"/></ol>

## Why
Typically, we use Fine-Tuning to:
- improve LLM performance on specific tasks.
- introduce information that wasn't well represented by the base LLM model.

Good use cases include: 
- steering the LLM outputs in a specific style or tone.
- too long or complex prompts to fit into the LLM prompt window.

## When
You may consider Fine-Tuning when:
- you have tried Prompt Engineering and RAG approaches.
- latency is critically important to the use case.
- high accuracy is required to meet the customer requirement.
- you have thousands of high-quality samples with ground-truth data.
- you have clear evaluation metrics to benchmark fine-tuned models.

## Learning Path

**Lab 1: LLM Fine-Tuning via *Dashboards***
- [Lab 1.1](labs/fine_tuning_dashboards/gpt_fine_tuning_aoai_dashboard.md): Fine-Tuning GPT Models (*1h duration*)
- [Lab 1.2](labs/fine_tuning_dashboards/llama2_fine_tuning_aml_dashboard.md): Fine-Tuning Llama2 Models (*1h duration*)

**Lab 2: LLM Fine-Tuning via *Python SDK***
- [Lab 2.1](labs/fine_tuning_notebooks/gpt_fine_tuning/gpt_35_turbo_fine_tuning.ipynb): Fine-Tuning GPT Models (*2h duration*)
- [Lab 2.2](labs/fine_tuning_notebooks/llama2_fine_tuning/llama_2_7b_fine_tuning.ipynb): Fine-Tuning Llama2 Models (*2h duration*) 
