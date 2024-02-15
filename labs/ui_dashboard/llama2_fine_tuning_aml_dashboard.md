## Fine-Tuning Llama-2 Models - A Dashboard Experience
Learn how to fine-tune an Llama-2 model using Azure Machine Learning (AML) Studio - UI Dashboard.  

### Prerequisites
* Learn the [what, why, and when to use fine-tuning.](https://learn.microsoft.com/en-us/azure/ai-services/openai/concepts/fine-tuning-considerations)
* An Azure subscription.
* Access to AML Service.
* An AML resource created.
* Prepare Training and Validation datasets:
  * at least 50 high-quality samples (preferably 1,000s) are required.
  * must be formatted in the JSON Lines (JSONL) document with UTF-8 encoding.

### Step 1: Open the *Model catalog* wizard
1. Open Azure Machine Learning Studio at [https://ml.azure.com/](https://ml.azure.com/) and sign in with credentials that have access to AML resource. During the sign-in workflow, select the appropriate directory, Azure subscription, and AML resource.

2. In AML Studio, browse to the **Model catalog** pane.
<ol><img src="../images/screenshot-aml-model-catalog.png" alt="Screenshot of AML Model Catalog pane." width="600"/></ol>

3. In the search box, type <code>llama2</code>.
<ol><img src="../images/screenshot-aml-search-llama2.png" alt="Screenshot of AML Model Catalog pane, searching for llama2 in the search box." width="600"/></ol>

### Step 2: Start the fine-tuning process
Assume that you want to fine-tune the <code>llama-2-7b</code> model for a text generation task (similar process for chat-completion tasks). 

1. The first step is to press the **Fine-tune** button to start the fine-tuning process.
<ol><img src="../images/screenshot-aml-ft-llama2-7b.png" alt="Screenshot of AML Model Catalog, with llama2-7b model description page." width="600"/></ol>

2. The **Fine-tune Llama-2-7b** blade lets you specify task type (choose <code>Text generation</code> for our case), training data, validation data (optional), test data (optional), and an Azure ML compute cluster.
<ol><img src="../images/screenshot-aml-ft-llama2-7b-wizard.png" alt="Screenshot of AML Model Catalog pane, for llama2-7b model, opening the Fine-Tune blade." width="600"/></ol>

### Step 3: Create an Azure ML compute cluster
To run the fine-tuning job, an AML compute cluster machine needs to be created (if you haven't done it before). 

1. The **\+ New** button at the bottom of the blade opens the **Create compute cluster** pane, where you need to specify the **Location** (<code>e.g. West Europe</code>), **Virtual machine tier** (<code>Dedicated</code>), **Virtual machine type** (<code>GPU</code>) and **Virtual machine size**. 
<ol><img src="../images/screenshot-aml-ft-create-compute-cluster.png " alt="Screenshot of AML create compute cluster pane, with location on west europe and the gpu type of nvidia ND40 series machine." width="600"/></ol>

<ol>Note that only nvidia ND40 and ND96 VMs are supported for fine-tuning at the moment. If you can't find it in list, you can try choosing other <strong>Location</strong> or to request quota accordingly.</ol>

2. Give a name to the compute, and specify the minimum (usually <code>0</code>) and maximum (<code>1</code> for testing purpose) number of nodes.
<ol><img src="../images/screenshot-aml-ft-create-compute-cluster-advanced-config.png " alt="Screenshot of AML create compute cluster pane, with gpu advanced config pane." width="600"/></ol>

<ol>Click <strong>Next</strong> to start the creation process. This may take a couple of minutes.</ol>

### Step 4: Choose your **Training data**
The next step is to select your training data either from the previously uploaded one or by uploading a new one.
<ol><img src="../images/screenshot-aml-ft-select-training-data.png " alt="Screenshot of AML fine tuning - choose training / validation / test data." width="600"/></ol>

You also need to specify the 'prompt' (i.e. input) and the 'completion' (i.e. output) columns to guide the fine-tuning process.  
<ol><img src="../images/screenshot-aml-ft-select-training-data-map-columns.png " alt="Screenshot of AML fine tuning - choose training / validation / test data, and map the prompt and completion columns." width="600"/></ol>

### Step 5 (Optional): Choose your **Validation data**
You can select your validation data by following the similar procedure as you do for the training data. Or, you can leave it as the default setting (i.e. an automtic split of the training data will be used for validation).

### Step 6 (Optional): Choose your **Test data**
You can select your test data by following the similar procedure as you do for the training data. Or, you can leave it as the default setting (i.e. an automtic split of the training data will be used for testing).
