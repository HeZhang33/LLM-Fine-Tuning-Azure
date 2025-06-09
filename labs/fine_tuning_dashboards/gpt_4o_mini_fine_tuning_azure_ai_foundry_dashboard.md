
## Fine-Tuning GPT-4o-mini Model - An AI Foundry Dashboard Experience

Learn how to fine-tune a **gpt-4o-mini** model using the Azure AI Foundry UI Dashboard.

---

### Prerequisites
* Learn the [what, why, and when to use fine-tuning.](https://learn.microsoft.com/en-us/azure/ai-services/openai/concepts/fine-tuning-considerations)
* An Azure subscription - [Create one for free.](https://azure.microsoft.com/free/cognitive-services)
* An [Azure AI project](https://learn.microsoft.com/en-us/azure/ai-foundry/how-to/create-projects) in Azure AI Foundry portal.
* An [Azure OpenAI connection](https://learn.microsoft.com/en-us/azure/ai-foundry/how-to/connections-add?tabs=azure-openai#connection-details) to a resource in a [region where fine-tuning is supported.](https://learn.microsoft.com/en-us/azure/ai-services/openai/concepts/models#fine-tuning-models)
* GPT Models that support fine-tuning so far:
  * *gpt-35-turbo-0125*
  * *gpt-4o-0806*
  * *gpt-4o-mini*
  * *gpt-4.1-mini*
  * *gpt-4.1-nano*
  * *o4-mini*
* Prepare Training and Validation datasets:
  * at least 50 high-quality samples (preferably 1,000s) are required.
  * must be formatted in the JSON Lines (JSONL) document with UTF-8 encoding.

You can check the MS Learn document [here](https://learn.microsoft.com/en-us/azure/ai-services/openai/how-to/fine-tuning?tabs=turbo%2Cpython&amp;pivots=programming-language-studio) for more details.

---

### Step 1: Open the *+Fine-tune model* wizard

1. Open Azure AI Foundry at [https://ai.azure.com/](https://ai.azure.com/) and sign in with credentials that have access to your Azure AI Foundry resource. In the **connected resources** tab, make sure that an Azure OpenAI resource is already connected to your AI Foundry Hub.
2. In Azure AI Foundry, choose an existing project or create a new project.  
<ol><img src="../images/screenshot-foundry-create-project.png" alt="Screenshot of the project creation" width="600"/></ol>

3. Once we have our project created, browse to the **Fine-tuning** pane, and select **+Fine-tune model**.  
<ol><img src="../images/screenshot-foundry-create-finetuning.png" alt="Screenshot of the Fine-tuning pane for the Creation for the custom model wizard" width="600"/></ol>

---

### Step 2: Select the *Base model*

1. In the **Base models** pane, choose **gpt-4o-mini** from the dropdown.
2. Click **Next** to proceed.  
> 🧠 *gpt-4o-mini is optimized for low-latency inference and supports supervised fine-tuning.*  
<ol><img src="../images/screenshot-foundry-select-base-model.png" alt="Screenshot that shows how to select the base model in the Create custom model wizard in Azure AI Foundry." width="600"/></ol>

---

### Step 3: Upload your *Training data*

1. Choose your fine-tuning method: **Supervised** or **Direct Preference Optimization** or **Reinforcement**.
2. Upload your training data using one of the following options:
   - **Upload files** from your local machine.
   - **Azure blob or other shared web locations**.
   - **Existing files on this resource** (already registered in Azure AI Foundry).  
> 📌 *Ensure your data is in JSONL format with UTF-8 encoding and that you have the necessary permissions (e.g., Azure Blob Storage Contributor).*  
<ol><img src="../images/screenshot-foundry-upload-data.png" alt="Screenshot of uploading training data" width="600"/></ol>

Assume we want to **Upload files** from our local machine.  
<ol><img src="../images/screenshot-foundry-upload-local.png" alt="Screenshot of displaying uploaded training data" width="600"/></ol>

---

### Step 4 (Optional): Add *Validation data*

Validation data is optional but recommended. Upload it using the same method as training data.  
<ol><img src="../images/screenshot-foundry-upload-validation.png" alt="Screenshot of uploading validation data" width="600"/></ol>

---

### Step 5 (Optional): Configure *Advanced options*

You can customize hyperparameters such as:
- Epochs
- Batch size
- Learning rate
- Warmup steps

Or leave them at default values.  
> 🔧 For tuning the hyperparameters, one can refer to the MS Learn document [here](https://learn.microsoft.com/en-us/azure/ai-services/openai/how-to/fine-tuning?tabs=turbo%2Cpython&amp;pivots=programming-language-studio#configure-advanced-options) for a detailed explanation.  
<ol><img src="../images/screenshot-foundry-advanced-params.png" alt="Screenshot of advanced configuration options" width="600"/></ol>

---

### Step 6: Review and *Submit*

1. Review your configuration.
2. Click **Submit** to start the fine-tuning job.
3. Monitor progress in the **Status** column of the **Fine-tuning** pane.  
> ⏱️ *Training duration depends on dataset size and selected parameters.*  
<ol><img src="../images/screenshot-foundry-status-check.png" alt="Screenshot of reviewing the status of the fine-tuning job" width="600"/></ol>

When the fine-tuning process finishes, you will see the **Status** showing **Completed**.  
<ol><img src="../images/screenshot-foundry-job-completed.png" alt="Screenshot of completed status of the fine-tuning job" width="600"/></ol>

---

### Step 7: *Deploy* your fine-tuned model

1. Once training completes, select your model in the **Fine-tuning** pane.
2. Click **Use this model**.  
<ol><img src="../images/screenshot-foundry-use-model.png" alt="Screenshot of deploying the fine-tuned model" width="600"/></ol>

3. In the **Deploy model** dialog, enter a deployment name and click **Deploy**.  
<ol><img src="../images/screenshot-foundry-deploy-model.png" alt="Screenshot of configuring the deployment of the fine-tuned model" width="600"/></ol>

---

### Step 8: *Test and use* your deployed model

- Use the **Playgrounds** in Azure AI Foundry to test your model interactively.  
<ol><img src="../images/screenshot-foundry-playground.png" alt="Screenshot of completed deployment of the fine-tuned model" width="600"/></ol>

---

### Step 9 (Optional): *Clean up* resources

Delete deployments, models, and datasets when no longer needed to avoid unnecessary costs.

---

### Step 10 (Optional): *Continuous fine-tuning*

To further refine your model:
1. Start a new fine-tuning job.
2. Select your previously fine-tuned model as the base model (e.g., `gpt-4o-mini-2024-07-18.ft-...`).  
<ol><img src="../images/screenshot-foundry-continous-ft-1.png" alt="Screenshot of continuous fine-tuning setup" width="600"/></ol>

This enables iterative improvement over time.
