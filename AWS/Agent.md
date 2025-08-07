# Basics 
Instructions--> Actions ( using Knowldge Bases )

#### Agent Builder 
Name
Description
Instructions 
Model
Action Group
Knowldge base

#### Action group 
defines the action the users needs to perform. 
e.g. action group called "book hotel: that has create, update and cancell bokking actions 

has 3 key elements : Description, API schema and the lambda function 

<img width="931" height="459" alt="image" src="https://github.com/user-attachments/assets/ac2c22c5-c7a3-4786-8e10-c50d6b039a76" />

# Demo : Aoutfit assistant
<img width="810" height="315" alt="image" src="https://github.com/user-attachments/assets/ee416dae-ec7a-44f2-84ff-f08b248e21a3" />

#### Building agents 
AWS Bedrock --> Builder tools --> Agents --> Create 
Name 
Resource role : use existing role as Bedrock 
Select Model: Calude 3
Instruction: write clear and detailed instruction. 
  Agent Actions group
    Descruption
    - getCordinates
    - getCurrentTime
    - getCurrentWeather
    Action group type
      Define with function details
    Action group invocation 
      create or select a lambda function 
      3Lambda functions has 3 clasees or functions getCordinates getCurrentTime getCurrentWeather and aditioanlly an external weather API call. 
    
      












