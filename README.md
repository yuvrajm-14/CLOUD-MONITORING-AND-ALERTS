# CLOUD-MONITORING-AND-ALERTS

**COMPANY**: CODTECH IT SOLUTIONS

**NAME**: YUVRAJ VISHVANATH MUDLIYAR

**INTERN ID**: CODHC203

**DOMAIN**: CLOUD COMPUTING

**DURATION**: 12 WEEKS

**MENTOR**: NEELA SANTOSH

#DESCRIPTION

Step 1: Launch an EC2 Instance

•	Go to the AWS EC2 Console → Click on Launch Instance.

•	Choose Amazon Linux 2023 or Ubuntu as the OS.

•	Choose an instance type (e.g., t2.micro for free-tier or t2.medium for better testing).

•	Configure security group:
o	Allow SSH (Port 22) from your IP.

o	Allow HTTP (Port 80) if using a web server.

•	Launch the instance.


Step 2: Create Amazon SNS Topic & Subscription

•	Go to AWS SNS Console.

•	Click Create Topic → Choose Standard.

•	Enter a name (e.g., HighCPUAlert).

•	Click Create Subscription:

o	Choose Email.

o	Enter your email and confirm the subscription from your inbox.


Step 3: Configure CloudWatch Metrics & Alarms
1.	Go to AWS CloudWatch Console.
2.	Click on Alarms → Create Alarm.
3.	Select EC2 Metrics → Choose CPUUtilization.
4.	Set conditions:
o	Threshold: CPUUtilization >= 80%
o	Period: 5 minutes
o	Evaluation Periods: 1
5.	Click on next 
6.	Click on add notification
7.	Click on Inalarm
8.	Click Select an existing SNS topic
9.	Under Send a notification to… 
•	Select the sns topic which is created on Step 2
10.	Click on Next
11.	Give a Alarm name as Cpu Utilization
12.	It shows Preview and create
13.	Click on Create alarm
14.	Go to your gmail
15.	You will see the aws notification mail open it & Click on confirm subscription

    
Step 5: Perform Stress Testing (To Trigger Alarm)
•	Click on the Cloud Shell

•	Upload the Key Pem File

•	Enter this command chmod 0400 keyfile.pem

•	Connect to the EC2 instance via SSH:
ssh -i your-key.pem ec2-user@your-ec2-public-ip

•	Install the stress tool:
sudo yum install -y epel-release && sudo yum install -y stress

•	Run CPU stress test for 10 minutes:
stress --cpu 4 --timeout 600
This will increase CPU usage and trigger the CloudWatch alarm.

Step 7: Verify Monitoring & Alerts
•	Go to CloudWatch Console → Metrics → All Metrics->Click on Graphed metrics ->Check if CPUUtilization is high.
•	Check CloudWatch Alarms → It should show In Alarm.
•	Check your email inbox for the SNS notification.

Step 8: (Optional) Create a CloudWatch Dashboard
•	In CloudWatch, go to Dashboards → Create Dashboard -> Give a name -> Click Create.
•	Add Widgets for:
o	Select the Graph like Line, Bar, Number, Pie, etc
o	Click on Ec2->Per Instances Metrics-> Check the CPUUtilization-> Click Create widget
•	Save the dashboard.


#OUTPUT

![Image](https://github.com/user-attachments/assets/da863a45-8506-4b46-ae19-fe6275223817)

![Image](https://github.com/user-attachments/assets/4e2d7897-2b43-453d-bd7f-1820a55f9d78)

![Image](https://github.com/user-attachments/assets/9cbaa3d1-33c6-470e-80e1-cd1b79268957)

![Image](https://github.com/user-attachments/assets/51c55d31-e2bb-4d52-8c42-af02f668332b)

![Image](https://github.com/user-attachments/assets/880cbe31-d015-4deb-9cc5-cfd21974aa77)

![Image](https://github.com/user-attachments/assets/c03d8907-5bd7-4922-bc98-b7198f0517ce)


