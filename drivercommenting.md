# Real-time Data Integration with Power Apps and Revenue Analytics Power BI

## Overview
This project, developed in Power Apps, is a crucial component of the Revenue Analytics project. Its primary function is to automate real-time commenting on the top and bottom drivers, dramatically reducing processing time from 4 hours to just seconds. By leveraging API, Power BI Streaming datasets, and Power Apps, this solution ensures swift and efficient analysis and commentary, providing immediate insights and enhancing decision-making capabilities.

## Tools Used
- **Power Apps:** For creating the user interface and data input mechanism.
- **Power BI:** For real-time data visualization.
- **Streaming/Push Dataset**: For handling real-time data updates.

## Step-by-Step Implementation:
### Step 1: Create the Power BI Streaming/Push Dataset:
In Power BI Workspace, click New button and choose Streaming dataset option. A window called "Streaming dataset" will appear that allows to choose the source of the data. In this project, I choosed API. Click next.
![image](https://github.com/user-attachments/assets/94fddd27-c900-4b10-a971-301a37a7f28c)

Next step is giving a name for my dataset and setting the column fields. Click create once finalized. 
![image](https://github.com/user-attachments/assets/90dbb974-9caf-4b92-87ac-76829b9b8705)


## How to use the App

### Step 1
Switch on the toogle button to show the commenting app.
![image](https://github.com/greatcyan/cyrus-baruc-data-analytics-portfolio/assets/95137493/ad4d3fba-c7b3-4cda-aec8-b49afe2521e2)
### Step 2
Select appropriate revenue bucket and geography.
![image](https://github.com/greatcyan/cyrus-baruc-data-analytics-portfolio/assets/95137493/04d9f308-8d46-4a9d-881d-b73de999b850)
### Step 3
Input driver commentaries and analysis.
![image](https://github.com/greatcyan/cyrus-baruc-data-analytics-portfolio/assets/95137493/f658ab10-6492-4e3a-85fb-faccd78f8f96)
### Step 4
Click submit.
![image](https://github.com/greatcyan/cyrus-baruc-data-analytics-portfolio/assets/95137493/e5844bbc-a31b-4f4f-9d6e-25a528c6fd13)
### Step 5
Hover on the summary table to view the driver comments in a tooltip.
![image](https://github.com/greatcyan/cyrus-baruc-data-analytics-portfolio/assets/95137493/965a02d1-dd90-4622-a3fc-bfe2961b93d2)

## Impact
Previously, commenting was conducted through Analyze in Excel, a process that lacked real-time capabilities and delayed decision-making. With the new Power Apps automation integrated into the Revenue Analytics project, stakeholders can now provide immediate, real-time insights on top and bottom revenue drivers directly within the Power BI environment. This enhancement has significantly accelerated data analysis processes, enabling quicker responses to business trends and opportunities.
