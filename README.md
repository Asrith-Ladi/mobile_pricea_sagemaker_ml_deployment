# End-to-End Machine Learning with Amazon SageMaker

This project demonstrates a complete machine learning workflow using Amazon SageMaker, from data acquisition and exploration to training, deployment, and creating a real-time inference endpoint. It is built around a mobile price classification dataset sourced from Kaggle.

By following this project, you will get hands-on experience with:

✅ Preparing and uploading data to S3  
✅ Training a scikit-learn Random Forest classifier on SageMaker  
✅ Deploying the trained model as a REST API endpoint  
✅ Testing the endpoint with sample predictions  
✅ Performing proper cleanup to manage AWS costs

---

## Project Overview

- **Dataset**: [Kaggle - Mobile Price Classification](https://www.kaggle.com/datasets/iabhishekofficial/mobile-price-classification?select=train.csv)  
- **Model**: Random Forest Classifier  
- **Framework**: Scikit-learn on Amazon SageMaker  
- **Language**: Python 3.11  
- **Infrastructure**: AWS SageMaker, S3, IAM  
- **Documentation**: [Project Documentation (Word)](https://github.com/Asrith-Ladi/mobile_pricea_sagemaker_ml_deployment/blob/main/Aws%20sagemaker.docx)  
- **Notebook**: [Jupyter Notebook](https://github.com/Asrith-Ladi/mobile_pricea_sagemaker_ml_deployment/blob/main/sagemaker_script.ipynb)

---

## Getting Started

1. **Set up prerequisites**  
   - Install Anaconda or Miniconda  
   - Create and activate a conda environment:  
     ```bash
     conda create --prefix ./env python=3.11
     conda activate ./env
     ```
   - Install AWS CLI and configure it:  
     [AWS CLI install link](https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html)  
     or  
     ```bash
     msiexec.exe /i https://awscli.amazonaws.com/AWSCLIV2.msi
     ```
   - Configure with your AWS credentials:  
     ```bash
     aws configure
     ```
   - Install required Python packages:  
     ```bash
     pip install sagemaker pandas scikit-learn kaggle
     ```

2. **Download the dataset**  
   - Follow the Kaggle API instructions in the notebook or download manually from Kaggle

3. **Run the Jupyter Notebook**  
   - Open `sagemaker_script.ipynb`  
   - Execute cells step by step to:  
     - upload data  
     - train the model  
     - deploy the endpoint  
     - test predictions

---

## Cleanup

⚠️ Remember to delete your SageMaker endpoint and any S3 buckets created during the project to avoid unnecessary AWS costs:  

```python
sm_boto3.delete_endpoint(EndpointName=endpoint_name)
