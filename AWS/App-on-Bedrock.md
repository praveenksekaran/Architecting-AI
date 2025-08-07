# Tech stack 
<img width="841" height="449" alt="image" src="https://github.com/user-attachments/assets/18edf75f-cbd8-4647-bf47-a99451dea8ef" />

<img width="857" height="380" alt="image" src="https://github.com/user-attachments/assets/c16aa729-49eb-4953-8995-2d26f3f8e299" />

Nova is AWS own models 
Build agents on Bedrock

# Building the app

#### image Analysis application use case 
<img width="804" height="437" alt="image" src="https://github.com/user-attachments/assets/8750b769-e491-40ec-8818-70418235880c" />

Build using Python and FastAPI. Boto3. 

#### Architecture 
- Route 53 : exposing apps to the external world
- App Runner: fully Managed compute platform for deployment & scaling of  containerized application to bring it into the cloud for use and sharing with others
- Elastic Container Registry - app runner is going to pull the docker image from ECR (Managed container registry service)

<img width="409" height="426" alt="image" src="https://github.com/user-attachments/assets/638130ca-c131-4590-b75e-3e1f0f1a2abb" />

#### on AWS  
Step 1: Go to console home --> Amazon bedrock --> Bedrock configurations (Model access). 
- use the chat /Playground to test the model
- use Image/Video playground

Step 2a: create a App Runner service 
console home --> create service --> Source (Source code repository) 
Github Connection : RPS-Flask
Repository: choose from Git 
Deployment settings : Automatic (if you have apprunner.yaml file in the source) 

Step 2b: Build settings 
Use configuration file (if yaml is present)

step 2c: Configure service 
Service Name, CPU 
Health check: Protocol HTTP, Path /health (its an api in the project)
security: IAM policy to bedrock to allow ECS and choose that name in the security 

step 3: Review and Deploy

#### Get the code 
[Git: genai-image-app-builders-online-25](https://github.com/MattJColes/genai-image-app-builders-online-25)






