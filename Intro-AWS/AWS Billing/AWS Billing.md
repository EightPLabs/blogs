# **AWS Billing**


# Understanding AWS Billing


### Overview of AWS Pricing Models



* Charges are based on actual usage of AWS services with no long-term commitments or upfront payments.
* It offers discounted pricing for EC2 instances with a one or three-year term commitment.
* It allows users to bid on unused EC2 capacity by offering potential cost savings for workloads with flexible start and end times.


### Billing Metrics and Terminology



* **Usage:** The amount of AWS resources consumed, typically measured in hours, GB, requests, etc.
* **Rate:** The cost per usage unit for a specific AWS service or resource.
* **Billable Events:** Actions or operations that incur charges such as running an EC2 instance, storing data in S3, or transferring data between AWS regions.
* **Billing Period:** The period for which AWS usage is calculated and billed, typically monthly.
* **Cost Allocation Tags:** Tags assigned to AWS resources for cost tracking and allocation purposes, enabling organizations to attribute costs to specific projects, departments, or teams.


## AWS Free Tier
![alt_text](https://github.com/EightPLabs/blogs/blob/main/Intro-AWS/AWS%20Billing/AWS-Billing-Images/0.png?raw=true)



### Explanation of Free Services and Usage Limits:


* AWS Free Tier offers a limited amount of free usage for a selection of services for 12 months.
* Free Tier usage limits vary by service and It is designed to allow customers to explore the AWS services at no cost.
* Standard AWS pricing applies once the usage limits are exceeded or the 12-month period expires.


### Identifying Free-Tier Eligible Services


AWS provides a list of services eligible for the Free Tier along with their respective usage limits and durations on the AWS Free Tier webpage.


Common free-tier eligible services include:

* Amazon EC2 
* Amazon S3 (5GB storage)
* Amazon RDS (limited database instance hours)
* AWS Lambda (1 million free requests per month) and more.


Eligible services may vary by region and certain services may offer extended free usage beyond the initial 12-month period.


## AWS Billing Dashboard


### Overview of the AWS Billing and Cost Management Console



* The AWS Billing and Cost Management Console provides a dashboard for monitoring and managing your spending and usage of services.
![alt_text](https://github.com/EightPLabs/blogs/blob/main/Intro-AWS/AWS%20Billing/AWS-Billing-Images/1.png?raw=true)

It offers an overview of your current month's spending such as: 

* Total costs
* Forecasted costs
* Spending trends.
* The dashboard displays summary charts and graphs that allow users to visualize costs by service, linked accounts, and usage patterns.


### Navigating billing reports and cost explorer


#### Accessing the Billing & Cost Management Console



* Log in to the AWS Management Console.
* Navigate to the **_Billing & Cost Management _** service 
* In the Billing & Cost Management Console, select **_Reports._** 
* Click on **_Reports_** to expand the options, then choose **_Billing Reports_**.


It contains various billing reports, such as 

* Cost and Usage Report
* AWS Budgets
* Click on the desired billing report to view its details.

For example: 

(i)  Select the **_Cost and Usage Report_** to view detailed usage and spending data.


            
![alt_text](https://github.com/EightPLabs/blogs/blob/main/Intro-AWS/AWS%20Billing/AWS-Billing-Images/2.png?raw=true)



(ii) Customize the report settings to specify the period and data filters as needed.



#### Navigating to Cost Explorer



* To access Cost Explorer, go to the Billing & Cost Management Console.
* Click on **_Cost Explorer_** to access the tool for visualizing and analyzing your AWS spending
* In the Cost Explorer dashboard, you can visualize your AWS spending over time using various charts and graphs.



![alt_text](https://github.com/EightPLabs/blogs/blob/main/Intro-AWS/AWS%20Billing/AWS-Billing-Images/3.png?raw=true)


* Customize the view by selecting different periods, services, regions, instance types, etc.
* Utilize filtering options to analyze specific cost dimensions and identify spending trends or anomalies.


## Cost Allocation Tags


### Importance of cost allocation tags



* **Granular Cost Attribution:** Enables attribution of costs to specific projects, teams, or departments.
* **Cost Reporting and Analysis:** Provides detailed cost reporting and analysis based on tag values.
* **Resource Optimization:** Helps identify and optimize unused resources or cost outliers.


### Tagging strategies for cost management



* **Standardized Tagging Schema:** Establishes consistent tagging practices across resources.
* **Automated Tagging Policies:** Enforces tagging compliance and consistency through automation.
* **Hierarchical Tagging Hierarchy:** Represents relationships between organizational structures.
* **Cost-Aware Resource Provisioning:** Tags resources at creation to ensure accurate cost attribution.
* **Regular Review and Optimization:** Ensures tagging accuracy and relevance over time.


## Monitoring Cost and Usage Reports


    
![alt_text](https://github.com/EightPLabs/blogs/blob/main/Intro-AWS/AWS%20Billing/AWS-Billing-Images/4.png?raw=true)




### Generating and interpreting cost and usage reports



* Navigate to **_Reports _**and select**_ Cost and Usage Reports_**.



![alt_text](https://github.com/EightPLabs/blogs/blob/main/Intro-AWS/AWS%20Billing/AWS-Billing-Images/5.png?raw=true)




* Customize the report settings including time period, granularity, and data filters.
* Generate the report to retrieve detailed cost and usage data for analysis.


### Analyzing cost trends and patterns



* Review the summary section to understand total costs and usage for the selected period.
* Analyze cost breakdowns by service, linked accounts, and usage types to identify cost drivers.
* Explore detailed line items to understand individual resource costs and usage patterns.
* Identify cost trends over time by comparing data across different reporting periods.
* Look for patterns in resource utilization, such as spikes or anomalies, that may impact costs.
* Analyze cost allocation tags to understand how costs are distributed across projects, teams, or departments.


## Setting Budgets


![alt_text](https://github.com/EightPLabs/blogs/blob/main/Intro-AWS/AWS%20Billing/AWS-Billing-Images/6.png?raw=true)



### Creating AWS Budgets to Monitor Spending


![alt_text](https://github.com/EightPLabs/blogs/blob/main/Intro-AWS/AWS%20Billing/AWS-Billing-Images/7.png?raw=true)




* Click on **_Create Budget_** to begin creating a new budget.
* Specify budget details like budget name, budget period, budget amount, and optional filters (e.g., service, tag).
* Choose the desired budget type (e.g., usage, cost, RI utilization).
* Review and confirm the budget settings before creating the budget.


### Configuring Budget Notifications



* After creating a budget, configure notifications to receive alerts when budget thresholds are reached or exceeded.
* Select the desired notification options like email, SNS (Simple Notification Service) topic, or AWS Chatbot integration.
* Specify the notification thresholds (e.g., percentage of budget) and frequency (e.g., daily, weekly).
* Review and confirm the notification settings before saving the budget.


## Setting Up Billing Alarms



![alt_text](https://github.com/EightPLabs/blogs/blob/main/Intro-AWS/AWS%20Billing/AWS-Billing-Images/8.png?raw=true)



### Configuring CloudWatch Billing Alarms



* Access the AWS Management Console and navigate to the CloudWatch service.
* In the CloudWatch dashboard, select **_Alarms_** from the left-hand menu.
* Click on **_Create Alarm _** to begin configuring a new alarm.
* Choose the "Billing" metric namespace and select the **_Total Estimated Charge_** metric.
* Specify the metric's period, statistic, and threshold conditions for triggering the alarm.


### Defining Billing Thresholds for Alerts


![alt_text](https://github.com/EightPLabs/blogs/blob/main/Intro-AWS/AWS%20Billing/AWS-Billing-Images/9.png?raw=true)




* Set the threshold values for the billing alarm based on your budget or cost tolerance.
* Define threshold conditions such as **_Threshold is greater than_** or **_Threshold is greater than or equal to_** and enter the threshold value.
* Choose the appropriate actions to take when the alarm state changes (e.g., notify via SNS, trigger an AWS Lambda function).
* Provide a name and description for the alarm to distinguish it from others.
* Review the alarm configuration settings to ensure accuracy.
* Confirm the creation of the billing alarm to activate monitoring for AWS billing metrics.


## Implementing Service Limits


### Understanding AWS Service Limits



* AWS imposes service limits on various resources and services to ensure fair usage and prevent abuse.
* Service limits define the maximum number of resources or operations allowed within a specific AWS account, region, or service.
* Limits vary by service and resource type and may be based on factors such as account type, usage history, and performance considerations.


### Managing Service Limits and Quotas



* Access the AWS Service Quotas console to view and manage service limits for your AWS account.
* Identify the service limits relevant to your workload and usage patterns.
* Request limit increases for specific services or resources if your workload requires additional capacity beyond the default limits.
* Monitor service limits regularly and adjust resource usage or request limit increases as needed to avoid service disruptions.


## Practical Exercises


### Creating and Configuring Billing Alerts using CloudWatch



* Access the AWS Management Console and navigate to the CloudWatch service.
* Create a new billing alarm by selecting **_Alarms_** and clicking on **_Create Alarm._**
* Configure the alarm to monitor the **_Total Estimated Charge_** metric and set threshold conditions for triggering alerts.
* Define actions to take when the alarm state changes (e.g., notify via SNS, trigger an AWS Lambda function).
* Test the billing alarm by intentionally exceeding the threshold to ensure alerts are triggered correctly.


### Setting Up Budgets and Cost Allocation Tags


![alt_text](https://github.com/EightPLabs/blogs/blob/main/Intro-AWS/AWS%20Billing/AWS-Billing-Images/10.png?raw=true)




* Create a new budget by specifying budget details such as name, period, amount, and optional filters.
* Configure budget notifications to receive alerts when spending exceeds defined thresholds.
* Explore cost allocation tags and apply them to AWS resources to track spending by project, team, or department.
* Review and analyze budget reports to monitor spending trends and identify cost-saving opportunities.


### Exploring AWS Free Tier-Eligible Services



* Visit the AWS Free Tier webpage to review the list of services eligible for the Free Tier.
* Explore the usage limits and duration of free usage for each eligible service.
* Create a new AWS account or use an existing account to experiment with Free Tier-eligible services.
* Deploy and configure resources within the Free Tier limits to gain hands-on experience with AWS services at no cost.
* Monitor usage and spending to ensure usage remains within the Free Tier limits to avoid unexpected charges.
