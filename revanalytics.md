# Revenue Analytics

## Overview
This report will support the P&L Review, enabling the Revenue Accounting team to investigate revenue buckets/streams with significant deviations from expected amounts. Expected amounts are based on the Average Unit Revenue (AUR) from the last 12 months rather than validating top customers as done previously using SAP Analysis for Office. Due to its limitations with large data volumes, automating data preparation and utilizing Power BI's features for user interactivity and data visualizations, this project has been successfully deployed to users, resulting in significant time savings and a more efficient decision-making process.

## Visualization
### Summary
This Power BI report comprises multiple views, each dedicated to different revenue buckets, complemented by a summary page that compares each revenue stream, emphasizing those with significant impact. The summary page is structured with a clear visual hierarchy to facilitate rapid data analysis. Interactive slicers on the left side allow users to select specific criteria for customized analysis. Metric cards for each revenue bucket display actual revenue, expected revenue, and variance, helping users pinpoint the highest and lowest revenue streams of the month. Additionally, a summary table on the left provides these metrics alongside real-time driver commentaries inputted via a Power Apps application. Below, a variance distribution by geography and revenue buckets enhances comparability.
![image](https://github.com/user-attachments/assets/9400d79e-5b22-4f62-93a8-20e175302c66)

### Details
All revenue buckets can be navigated through separate navigation buttons, each offering detailed information on revenue, units, calculation specifics, and the analytics page accessible via *radio buttons*. This functionality is achieved using bookmarking capabilities within Power BI.

The **Revenue Details** section features a matrix table visualization displaying actual revenue by month. Users can drill down into details starting from company code and product family, all the way up to customer level.
![image](https://github.com/user-attachments/assets/5366156f-3019-4722-a179-39590f1677c0)

The **Units Details or the "Sellin Pages"**, the same with Revenue details, also features a matrix table visualization displaying actual units/volume by month. Users can drill down into details starting from company code and product family, all the way up to customer level.
![image](https://github.com/user-attachments/assets/b2e9a3ba-3c8d-4462-9440-1d62838d5ecb)

The **Calculation Details** section displays metrics and calculations using a matrix table, designed for in-depth analysis and data validation.
![image](https://github.com/user-attachments/assets/789360a5-aac1-475a-a62b-e5429ebf0d55)


The **Analytics View** is a dashboard providing a quick snapshot of revenue metrics for swift insights and data comprehension. At the top, main metric cards display key figures. The middle left section shows variance by geography, while the middle right section illustrates revenue and volume trends over the past 12 months. At the bottom, the top and bottom three variances are detailed by geography, product family, and customer. Slicers are synchronized across other pages, ensuring consistent filtering and analysis throughout the report.
![image](https://github.com/user-attachments/assets/5a64db42-b494-424a-9348-fd7fc4f84394)

## Data Source
- The actual revenue and volume figures are sourced from the P&L Performance Table in SAP.
- The mapping file for converting volume to Sellin Pages is sourced from the Product Details Table in SAP.

## Data Model Structure
After the ETL process, the model applied in this Power BI project is a star schema. Summarized and aggregated revenue bucket tables into a single table to reduce complexity. Created dimension tables for calendar, geography, product family, and customer to lessen ambiguity and optimize query performance at the front end, preventing loading delays in rendering visuals.
![image](https://github.com/user-attachments/assets/d1fabfba-bb28-48f1-8501-a78ad87070fb)

## Calculations
Calculated measures are developed using DAX to support the objectives of this report. The primary aim is to conduct a comparative analysis between actual revenue and expected revenue. To facilitate this comparison, we calculate the Average Units Revenue (AUR), offering a precise and detailed measure of revenue performance. We begin by calculating the actual revenue and volume, followed by their respective averages, and then derive the AUR. With the AUR established, we can calculate the expected revenue. 
Below are the process in deriving the AUR and the DAX Queries.

- Total Revenue and Volume
  ![image](https://github.com/user-attachments/assets/6d52fb96-1abd-4647-b4ad-869680676044)
<!--![image](https://github.com/user-attachments/assets/fbb37aae-5c1b-4ce6-ad61-68d4f74507ed)-->

- Current Month Revenue
  ![image](https://github.com/user-attachments/assets/db020302-7c19-4f20-a594-1f9f0a070580)
<!--![image](https://github.com/user-attachments/assets/6cedcd09-a88d-4666-a6d1-c3c5e63c3192)-->

- Current Month Volume
  ![image](https://github.com/user-attachments/assets/528c3298-4dd2-4618-8c86-00a206af23c9)
<!--![image](https://github.com/user-attachments/assets/43a78393-93be-4572-a68e-1b4347545a59)-->

- Current Month Average Revenue
  ![image](https://github.com/user-attachments/assets/1a5fae46-f054-420c-a128-e98ffa5872b8)
<!--![image](https://github.com/user-attachments/assets/63518639-38cf-41db-a54e-b8a84f329b8f)-->

- Current Month Average Volume
  ![image](https://github.com/user-attachments/assets/6729b790-e04a-425e-a240-081929e986a0)
<!--![image](https://github.com/user-attachments/assets/77ef78de-8886-450f-8da4-733d6bf8f706)-->

- AUR
  ![image](https://github.com/user-attachments/assets/9f72b2dc-1597-4095-b67d-e92bcbfa0c7c)
<!--![image](https://github.com/user-attachments/assets/4fdee12b-3812-4e82-a6ea-c8fb43c0c733)-->

- AUR based on average
  ![image](https://github.com/user-attachments/assets/fdbb6184-f5f8-414d-8c23-6b222d9c85e3)
<!--![image](https://github.com/user-attachments/assets/ee8d444b-9b6c-4931-a206-6ba492adf6ea)-->

- Expected Revenue
  ![image](https://github.com/user-attachments/assets/34f629a5-4b77-413d-a9d9-3b36d4d8a481)
<!--![image](https://github.com/user-attachments/assets/5253ac3a-1dd7-48fc-b0bb-fe698550d9cd)-->

We can then perform a comparative analysis between the current month actual revenue vs the expected revenue. These calculations provide insights into whether the supply volume justifies the revenue. Decision-makers can use these insights to strategize and optimize revenue effectively.

## Design Approach
The design of the Revenue Analytics Dashboard was guided by principles of visual hierarchy, brand consistency, and user accessibility. The goal was to create an intuitive and engaging user experience that allows stakeholders to easily navigate through the data and derive meaningful insights.

### Layout and Visual Hierarchy
-  Structured Layout: The dashboard was organized into clear sections to guide the user’s focus and ensure logical flow. Key metrics and KPIs were placed prominently at the top, while detailed visualizations and trend analyses were positioned below.
-  Consistent Grid System: Used a consistent grid system to align visual elements, ensuring a clean and professional appearance.
-  Emphasis on Key Data: Highlighted critical data points and trends using larger font sizes and distinct colors to draw immediate attention.

### Color Scheme and Branding
- Brand Colors: Applied the company's brand colors throughout the dashboard to maintain consistency with the corporate identity. This included primary colors for main elements and secondary colors for accents and highlights.
- Color Contrast: Ensured high contrast between text and background to enhance readability and cater to users with visual impairments.
- Conditional Formatting: Used conditional formatting to dynamically change colors based on data values, helping users quickly identify positive and negative trends.

### Interactivity and Navigation
- Bookmarking: Utilized Power BI’s bookmarking feature to create snapshots of different views within the dashboard. This allowed users to easily switch between various analyses and maintain their context.
- Navigation Buttons: Implemented navigation buttons to enable seamless movement between different sections and pages of the dashboard. Buttons were clearly labeled and styled consistently to align with the overall design.
- Tooltips and Drill-Throughs: Added tooltips and drill-through actions to provide additional context and enable deeper exploration of data without cluttering the main view.

### Stakeholder's Feedback
![image](https://github.com/user-attachments/assets/387795b0-0ad9-449b-b7b0-325dc2e02a7f)













