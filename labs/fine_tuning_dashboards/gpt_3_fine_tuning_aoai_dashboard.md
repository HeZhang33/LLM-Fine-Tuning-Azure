## Fine-Tuning GPT Models - A Dashboard Experience
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

### Step 5 (Optional): Configure *Advanced options*
Select **Default** to use the default values for the fine-tuning job, or select **Advanced** to display and edit the hyperparameter values.
<ol><img src="https://learn.microsoft.com/en-us/azure/ai-services/openai/media/fine-tuning/studio-advanced-options.png" alt="Screenshot of the Advanced options pane for the Create custom model wizard, with default options selected." width="600"/></ol>

One can refer to the MS Learn document [here](https://learn.microsoft.com/en-us/azure/ai-services/openai/how-to/fine-tuning?tabs=turbo%2Cpython&pivots=programming-language-studio#configure-advanced-options) for a detailed explanation on key tun-able hyperparameters.

### Step 6: Review your choices and *Start Training job*
If you're ready to train your model, select **Start Training job** to start the fine-tuning job and return to the **Models** pane.
<ol><img src="https://learn.microsoft.com/en-us/azure/ai-services/openai/media/fine-tuning/studio-review.png" alt="Screenshot of the Review pane for the Create custom model wizard in Azure OpenAI Studio." width="600"/></ol>

You can check the status of the custom model in the **Status** column of the **Custom models** tab.
<ol><img src="https://learn.microsoft.com/en-us/azure/ai-services/openai/media/fine-tuning/studio-models-job-running.png" alt="Screenshot of the Models pane from Azure OpenAI Studio, with a custom model displayed." width="600"/></ol>

After you start a fine-tuning job, it can take some time to complete (from minutes to hours).
<ol><img src="https://learn.microsoft.com/en-us/azure/ai-services/openai/media/fine-tuning/studio-model-details.png" alt="Screenshot of the Models pane in Azure OpenAI Studio, with a custom model displayed." width="600"/></ol>

### Step 7: Deploy a custom model
When the fine-tuning job succeeds, you can deploy the custom model from the **Models** pane to make it available for use with completion calls.

To deploy your custom model, select the custom model to deploy, and then select **Deploy model**.
<ol><img src="https://learn.microsoft.com/en-us/azure/ai-services/openai/media/fine-tuning/studio-models-deploy-model.png#lightbox
" alt="Screenshot that shows how to deploy a custom model in Azure OpenAI Studio." width="600"/></ol>

The **Deploy model** dialog box opens. 

In the dialog box, enter your **Deployment name** and then select **Create** to start the deployment of your custom model.
<ol><img src="https://learn.microsoft.com/en-us/azure/ai-services/openai/media/fine-tuning/studio-models-deploy.png" alt="Screenshot of the Deploy Model dialog in Azure OpenAI Studio." width="600"/></ol>

### Step 8: Test and use a deployed model
After your custom model deploys, you can use it like any other deployed model. 

You can use the **Playgrounds** in [Azure OpenAI Studio]("https://oai.azure.com") to experiment with your new deployment. You can also use the fine-tuned model by calling the completion API.

### Step 9 (Optional): Clean up your deployment resources
When you're done with your custom model, you can delete the deployment and model. You can also delete the training and validation files you uploaded to the service, if needed.

### Step 10 (Optional): Continous fine-tuning
Once you have created a fine-tuned model you may wish to continue to refine the model over time through further fine-tuning. Continuous fine-tuning is the iterative process of selecting an already fine-tuned model as a base model and fine-tuning it further on new sets of training examples.

To perform fine-tuning on a model that you have previously fine-tuned you would use the same process as described in **Step 1**, but instead of specifying the name of a generic base model, you would specify your already fine-tuned model. A custom fine-tuned model would look like <code>gpt-35-turbo-0613.ft-5fd1918ee65d4cd38a5dcf6835066ed7</code>
<ol><img src="https://learn.microsoft.com/en-us/azure/ai-services/openai/media/fine-tuning/studio-continuous.png" alt="Screenshot of the Create a custom model UI with a fine-tuned model highlighted." width="600"/></ol>
