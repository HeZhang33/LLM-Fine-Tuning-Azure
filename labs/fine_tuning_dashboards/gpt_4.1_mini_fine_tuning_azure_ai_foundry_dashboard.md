
## Fine-Tuning GPT-4.1-mini Model - A Dashboard Experience

Learn how to fine-tune a **gpt-4.1-mini** model using the Azure AI Foundry UI Dashboard.

---

### Step 1: Create a Project in Azure AI Foundry

1. Navigate to https://ai.azure.com/ and sign in with your Azure credentials.
2. On the landing page, click the **+ Create new** button in the top-right corner to create a new project.
<ol><img src="../images/screenshot-create-project.png" alt="Screenshot of creating a new project in Azure AI Foundry" width="600"/></ol>

4. Provide a name for your project, configure other settings such as region, resource group etc., and then select **Create**.  
<ol><img src="../images/screenshot-create-project-config.png" alt="Screenshot of configuring the project settings" width="600"/></ol>

---

### Step 2: Launch the *Fine-tune with your own data* Wizard

1. Inside your project, go to the **Fine-tuning** pane.
2. Click **Fine-tune model** to open the wizard.

<ol><img src="../images/screenshot-launch-finetune-wizard.png" alt="Screenshot of launching the fine-tune wizard" width="600"/></ol>

---

### Step 3: Select the *Base model*

1. In the **Base model** pane, choose **gpt-4.1-mini** from the dropdown.
2. Click **Next** to proceed.

> 🧠 *gpt-4.1-mini is optimized for low-latency inference and supports supervised fine-tuning.*

<ol><img src="../images/screenshot-select-base-model.png" alt="Screenshot of selecting the base model" width="600"/></ol>

---

### Step 4: Upload your *Training data*

1. Choose your fine-tuning method: **Supervised** or **Direct Preference Optimization** or **Reinforcement**.
2. Upload your training data using one of the following options:
   - **Upload files** from your local machine.
   - **Azure blob or other shared web locations**.
   - **Existing files on this resource** (already registered in Azure AI Foundry).

> 📌 *Ensure your data is in JSONL format with UTF-8 encoding and that you have the necessary permissions (e.g., Azure Blob Storage Contributor).*

<ol><img src="../images/screenshot-upload-training-data.png" alt="Screenshot of uploading training data" width="600"/></ol>

<ol><img src="../images/screenshot-upload-training-data-display.png" alt="Screenshot of displaying uploaded training data" width="600"/></ol>

---

### Step 5 (Optional): Add *Validation data*

Validation data is optional but recommended. Upload it using the same method as training data.

<ol><img src="../images/screenshot-upload-validation-data.png" alt="Screenshot of uploading validation data" width="600"/></ol>

---

### Step 6 (Optional): Configure *Advanced options*

You can customize hyperparameters such as:
- Epochs
- Batch size
- Learning rate
- Warmup steps

Or leave them at default values.

> 🔧 For tuning guidance, refer to https://learn.microsoft.com/en-us/azure/ai-services/openai/how-to/fine-tuning?tabs=turbo%2Cpython&pivots=programming-language-studio#configure-advanced-options.

<ol><img src="../images/screenshot-advanced-options.png" alt="Screenshot of advanced configuration options" width="600"/></ol>

---

### Step 7: Review and *Submit*

1. Review your configuration.
2. Click **Submit** to start the fine-tuning job.
3. Monitor progress in the **Status** column of the **Fine-tuning** pane.

> ⏱️ *Training duration depends on dataset size and selected parameters.*

<ol><img src="../images/screenshot-review-submit.png" alt="Screenshot of reviewing and submitting the fine-tuning job" width="600"/></ol>

<ol><img src="../images/screenshot-review-status.png" alt="Screenshot of reviewing the status of the fine-tuning job" width="600"/></ol>

<ol><img src="../images/screenshot-review-status-completed.png" alt="Screenshot of completed status of the fine-tuning job" width="600"/></ol>

<ol><img src="../images/screenshot-review-metrics.png" alt="Screenshot of reviewing metrics of the fine-tuning job" width="600"/></ol>

---

### Step 8: *Deploy* your fine-tuned model

1. Once training completes, select your model in the **Fine-tuning** pane.
2. Click **Use this model**.
3. In the **Deploy model** dialog, enter a deployment name and click **Deploy**.

<ol><img src="../images/screenshot-deploy-model.png" alt="Screenshot of deploying the fine-tuned model" width="600"/></ol>

<ol><img src="../images/screenshot-deploy-model-config.png" alt="Screenshot of configuring the deployment of the fine-tuned model" width="600"/></ol>

<ol><img src="../images/screenshot-deploy-model-completed.png" alt="Screenshot of completed deployment of the fine-tuned model" width="600"/></ol>

---

### Step 9: *Test and use* your deployed model

- Use the **Playgrounds** in Azure AI Foundry to test your model interactively.
- Or integrate it via the Completion API.

<ol><img src="../images/screenshot-test-model.png" alt="Screenshot of testing the deployed model" width="600"/></ol>

---

### Step 10 (Optional): *Clean up* resources

Delete deployments, models, and datasets when no longer needed to avoid unnecessary costs.

<ol><img src="../images/screenshot-cleanup-resources.png" alt="Screenshot of cleaning up resources" width="600"/></ol>

---

### Step 11 (Optional): *Continuous fine-tuning*

To further refine your model:
1. Start a new fine-tuning job.
2. Select your previously fine-tuned model as the base model (e.g., `gpt-4.1-mini-2025-06-08ft-abc123...`).

This enables iterative improvement over time.

<ol><img src="../images/screenshot-continuous-finetuning.png" alt="Screenshot of continuous fine-tuning setup" width="600"/></ol>
