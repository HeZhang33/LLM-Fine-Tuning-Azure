## Fine-Tuning GPT Models via Azure OpenAI Studio - Dashboard Experience
Learn how to fine-tune a GPT model using Azure OpenAI Studio - UI Dashboard.  

### Prerequisites
* Learn the [what, why, and when to use fine-tuning.](https://learn.microsoft.com/en-us/azure/ai-services/openai/concepts/fine-tuning-considerations)
* An Azure subscription.
* Access to Azure OpenAI Service.
* An Azure OpenAI resource created in the supported fine-tuning region (e.g. Sweden Central).
* GPT Models that support fine-tuning so far: *gpt-35-turbo-0613* and *gpt-35-turbo-1106*.
* Prepare Training and Validation datasets:
  * at least 50 high-quality samples (preferably 1,000s) are required.
  * must be formatted in the JSON Lines (JSONL) document with UTF-8 encoding.

You can check the MS Learn document [here](https://learn.microsoft.com/en-us/azure/ai-services/openai/how-to/fine-tuning?tabs=turbo%2Cpython&pivots=programming-language-studio) for more details.


<ol>
<li><p>Open Azure OpenAI Studio at <a href="https://oai.azure.com/" target="_blank" data-linktype="external">https://oai.azure.com/</a> and sign in with credentials that have access to your Azure OpenAI resource. During the sign-in workflow, select the appropriate directory, Azure subscription, and Azure OpenAI resource.</p>
</li>  
<img src="https://learn.microsoft.com/en-us/azure/ai-services/openai/media/fine-tuning/studio-create-custom-model.png" alt="Screenshot of the Training data pane for the Create custom model wizard, with local file options." width="800"/>

</ol>
