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

### Step 1: Open the *Create a custom model* wizard
1. Open Azure OpenAI Studio at [https://oai.azure.com/](https://oai.azure.com/) and sign in with credentials that have access to your Azure OpenAI resource. During the sign-in workflow, select the appropriate directory, Azure subscription, and Azure OpenAI resource.
2. In Azure OpenAI Studio, browse to the **Management > Models** pane, and select **Create a custom model**.
<ol><img src="https://learn.microsoft.com/en-us/azure/ai-services/openai/media/fine-tuning/studio-create-custom-model.png" alt="Screenshot of the Training data pane for the Create custom model wizard, with local file options." width="600"/></ol>

### Step 2: Select the *Base model*
The first step in creating a custom model is to choose a base model. 

The **Base model** pane lets you choose a base model to use for your custom model. Select the base model from the **Base model type** dropdown, and then select **Next** to continue.
<ol><img src="https://learn.microsoft.com/en-us/azure/ai-services/openai/media/fine-tuning/base-model.png" alt="Screenshot that shows how to select the base model in the Create custom model wizard in Azure OpenAI Studio." width="600"/></ol>

### Step 3: Choose your *Training data*
The next step is to choose your training data either from the previously uploaded one or by uploading a new one.
<ol><img src="https://learn.microsoft.com/en-us/azure/ai-services/openai/media/fine-tuning/studio-training-data.png" alt="Screenshot of the Training data pane for the Create custom model wizard in Azure OpenAI Studio." width="600"/></ol>

To upload a new training data, you can use one of the following options:
* Select **Local file** to upload training data from a local file.
  <ol><img src="https://learn.microsoft.com/en-us/azure/ai-services/openai/media/fine-tuning/studio-training-data-local.png" alt="Screenshot of the Training data pane for the Create custom model wizard, with local file options." width="600"/></ol>
* Select **Azure blob or other shared web locations** to import training data from Azure Blob or another shared web location.
  <ol><img src="https://learn.microsoft.com/en-us/azure/ai-services/openai/media/fine-tuning/studio-training-data-blob.png" alt="Screenshot of the Training data pane for the Create custom model wizard, with Azure Blob and shared web location options." width="600"/></ol>

### Step 4 (Optional): Choose your *Validation data*
You can choose your validation data by following the similar pattern as you upload your training data.
<ol><img src="https://learn.microsoft.com/en-us/azure/ai-services/openai/media/fine-tuning/studio-validation-data.png" alt="Screenshot of the Validation data pane for the Create custom model wizard in Azure OpenAI Studio." width="600"/></ol>


  
  
















