Steps to Schedule EC2 Instances for Off-Hours
Launch EC2 Instances

Create 4 EC2 instances in AWS.
Assign a tag key env with:
Value dev for 2 instances.
Value test for the other 2 instances.
Create a Role

Set up an IAM role with permissions that allow Lambda to manage EC2 instances.
Create a Lambda Function

Develop a Lambda function using the provided code.
Assign the previously created IAM role to the function.
Test the function to ensure it can start and stop EC2 instances based on tags.
Schedule the Lambda Function

Use CloudWatch Events Rules to define the execution schedule for the Lambda function.
Specify start and stop times based on operational needs.
Alternatively, use Infrastructure as Code (IaC) tools like Terraform to automate deployment.