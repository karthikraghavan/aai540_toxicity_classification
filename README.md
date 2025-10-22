**Project Background: Toxicity Classification**  
  
In today’s data-driven landscape, the integration of machine learning (ML) algorithms into business operations has become increasingly prevalent. In the case of Toxicity classification, which is essential for maintaining safe and trustworthy online platforms, the demand for robust ML systems and automated machine learning (AutoML) pipelines is particularly critical (Ltd, 2024). To address this need, MLOps, a convergence of machine learning and DevOps practices—provides the framework for building, deploying, and managing ML solutions at scale with reliability and efficiency.. The objective of this project is to detect and classify toxic civil comments with the focus on ensuring fairness across different demographic groups. These civil comments can originate from online article discussion platforms, such as the comment sections found in some news articles. Toxicity includes comments that are harmful, abusive, and hateful, while non-toxic comments are respectful, even if they refer to some sensitive identities (Pietrolesci/Civilcomments-Wilds · Datasets at Hugging Face, 2024). 
This is fundamentally a text classification problem in Natural Language Processing. The project is more specifically a binary classification task that identifies whether a comment is either toxic or non-toxic. The dataset has distributional shifts across various demographic groups, ensuring that the model can handle unseen data in the real world.





<img width="1113" height="614" alt="Architecture" src="https://github.com/user-attachments/assets/04f9fb9a-541d-43fb-85ee-99e6f8299cf2" />



The workflow begins with the preparation of both training input data and batch data required for real-time inference. The binary classification pipeline is structured into five major stages:

**Data Preparation**
The input data is split into train, validation. and test, and is made available for preprocessing.

**Preprocessing & Feature Engineering**
The input text is cleaned, tokenized, and lemmatized, and is fed into the CI/CD pipeline 

**CI/CD Pipeline**
The CI/CD pipeline automates the data transformation process, trains the model, performs model evaluation, and registers the model based on the accuracy threshold.

**Model training & Evaluation**
The model training and evaluation step is part of the CI/CD pipeline. The model leverages XGBoost to perform training. The model is evaluated for accuracy, precision, recall,  F1, and AUC scores.

**Model Deployment**
The model is retrieved from the cloud registry and deployed to an endpoint for downstream applications to consume the model for inference

**Model Monitoring**
The model is monitored using AWS Sagemaker’s monitoring job. The job establishes a baseline performance using ground truth labels and raises a CloudWatch alarm if the model performance drifts below the predefined threshold.


