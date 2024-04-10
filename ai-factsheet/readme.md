# Workshop on AI-Factsheet

## Pre-requisite

You will be required to possess an [IBM Cloud Account](https://cloud.ibm.com/). 

## Table of contents

- [Step 1. Provision watsonx governance](#step_1)
- [Step 2. Create a deployment space](#step_2)
- [Step 3. Train a Model and add AI-Factsheet](#step_3)
- [Step 4. Explore AI-Factsheet](#step_4)
- [Step 5. Model Deployment & Inference](#step_5)

<a id="step_1"></a>
## Step 1. Provision watsonx governance

Login to IBM Cloud Console https://cloud.ibm.com/

Go to watsonx.governance service catalog https://cloud.ibm.com/catalog/services/watsonxgovernance
- Select a location
- Pick the lite plan (Free plan is good for this workshop)
- Give it a name and create the instance

![image](https://github.com/hitalukder/workshop-watsonx.ai/assets/111310676/34ef1805-43ae-4b56-974e-6a55b66cce62)

After provisioning the instance navigate to the created instance. If you don’t find the created instance go to the resource list from the left top corner of the hamburger menu.

![image](https://github.com/hitalukder/workshop-watsonx.ai/assets/111310676/8b4fa46c-0627-4dac-bdec-613e3d1501dc)

Expand the AI/Machine Learning accordion and you should find your created instance. Click on the watsonx governance instance.

![image](https://github.com/hitalukder/workshop-watsonx.ai/assets/111310676/e6289301-2380-4a3b-bdab-52edd92163f5)

You will be presented to watsonx.governance landing page. Then Click on the Launch watsonx.governance.

![image](https://github.com/hitalukder/workshop-watsonx.ai/assets/111310676/2172e196-708a-4904-997a-3a62e436b6b0)

<a id="step_2"></a>
## Step 2. Create a deployment space

Deployment spaces contain deployable assets, deployments, deployment jobs, associated input and output data, and the associated environments. You can use spaces to deploy various assets and manage your deployments.

Navigate to the deployment menu and create a deployment space for our workshop

![image](https://github.com/hitalukder/workshop-watsonx.ai/assets/111310676/541ebfa3-d7aa-4889-93db-af0a34467c2f)

Click on **New Deployment Space** Give it a name and hit Create button.

![image](https://github.com/hitalukder/workshop-watsonx.ai/assets/111310676/57fe67d0-1493-45f3-a9ad-3350d82fa5dc)

![image](https://github.com/hitalukder/workshop-watsonx.ai/assets/111310676/86a4e0d4-4d0b-492c-9304-c51d51defa1d)

<a id="step_3"></a>
## Step 3. Train a Model and add AI-Factsheet 

Watson Studio provides fully-integrated industry standard tools such as R Studio and Python notebooks for data scientists to work in a collaborative environment. In this section, you explore a notebook that performs data exploration in preparation for an employee promotion usecase and add ai factsheet to the model.

To start with download the notebook from here https://github.com/hitalukder/workshop-watsonx.ai/blob/main/ai-factsheet/employee-promotion-ai-factsheet.ipynb or you can clone the repo with below command.

```sh
git clone git@github.com:hitalukder/workshop-watsonx.ai.git
```

Then please proceed to the project page in the watsonx platform and select the specific project you intend to work with.

![image](https://github.com/hitalukder/workshop-watsonx.ai/assets/111310676/2c43d95d-2326-4083-83c3-caa4954ea40a)

Go to the Project → [Project name] → Assets tab → click on New assets

![image](https://github.com/hitalukder/workshop-watsonx.ai/assets/111310676/5255913a-2495-4092-bfc4-32bcc7c11e73)

Click **Work with models** section from the left pane → Work with data and models in Python or R notebooks

![image](https://github.com/hitalukder/workshop-watsonx.ai/assets/111310676/de81f83e-632d-4516-8133-300c7d012201)

Select **"Local file"**. Then, either drag and drop a file or upload the notebook you previously downloaded from your local file system. Then hit **Create** button.

![image](https://github.com/hitalukder/workshop-watsonx.ai/assets/111310676/270a26b3-8892-4ffc-95d8-a7dd592af1a8)

### Notebook will be opened for development. Please follow the instruction in the notebook.

<a id="step_4"></a>
## Step 4. Explore AI-Factsheet 

In the previous step, we developed a model and saved it in the project. You can now view the saved model in the project you were working on. Now go back to the project you were working, you can see your saved model under **Assets** tab.

![image](https://github.com/hitalukder/workshop-watsonx.ai/assets/111310676/47983fcf-4ef8-4a0b-97a1-1d74cf11b2ba)

Let's promote the saved model to the deployment space. Click on the three dots next to the saved model, then select "Promote to Space" from the context menu. After clicking "Promote to Space," a new window will appear.

![image](https://github.com/hitalukder/workshop-watsonx.ai/assets/111310676/21de14b8-3c82-4ddf-b73c-c17defa75a7b)

Choose the Target space (created in step 2) from the dropdown menu and check the box labeled "Go to the model in the space after promoting it." Finally, click the **Promote** button, which will redirect you to the deployment space window.

Proceed to the **AI Factsheet Tab**, where you will find all the metadata and factsheets that were added during development.

![image](https://github.com/hitalukder/workshop-watsonx.ai/assets/111310676/8cfd4adf-4d8d-43e5-94fb-9ed1b31703ac)

<a id="step_5"></a>
## Step 5. Model Deployment & Inference

We're now ready to deploy our developed model for online inference. To do so, navigate to the deployment space, access the assets tab, and locate the model you wish to deploy. Click on the three dots next to the model, then select the "Deploy" option from the context menu.

![image](https://github.com/hitalukder/workshop-watsonx.ai/assets/111310676/b36d53c7-4c1a-48e9-98ca-a8e270aeb05d)

Give a name to the deployment and hit create button.

![image](https://github.com/hitalukder/workshop-watsonx.ai/assets/111310676/19173e4b-b48f-4891-ac21-592f425db70a)

The deployment process may take some time, and once completed, the status will change to `online`

![image](https://github.com/hitalukder/workshop-watsonx.ai/assets/111310676/d83d1311-310d-4eca-9767-0816697d83ab)

Once the deployment is complete, you can explore and test the model deployment using the API reference or directly from the UI as well.

![image](https://github.com/hitalukder/workshop-watsonx.ai/assets/111310676/80fb326e-b971-4035-ad92-a7d55fe2fb9a)

Here is a sample payload.

```json
{
        "input_data": [
                {
                        "fields": [
                                "no_of_trainings",
                                "age",
                                "previous_year_rating",
                                "length_of_service",
                                "kpis_met_above_80_percent",
                                "any_awards_won",
                                "avg_training_score",
                                "department_Finance",
                                "department_HR",
                                "department_Legal",
                                "department_Operations",
                                "department_Procurement",
                                "department_R&D",
                                "department_Sales & Marketing",
                                "department_Technology",
                                "education_Below Secondary",
                                "education_Master's & above",
                                "gender_m"
                        ],
                        "values": [
                                [
                                        1,
                                        35,
                                        5,
                                        8,
                                        1,
                                        0,
                                        49,
                                        0,
                                        0,
                                        0,
                                        0,
                                        0,
                                        0,
                                        1,
                                        0,
                                        0,
                                        1,
                                        0
                                ]
                        ]
                }
        ]
}
```









