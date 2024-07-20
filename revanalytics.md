# Revenue Analytics

## Overview
This report will support the P&L Review, enabling the Revenue Accounting team to investigate revenue buckets/streams with significant deviations from expected amounts. Expected amounts are based on the Average Unit Revenue (AUR) from the last 12 months rather than validating top customers as done previously using SAP Analysis for Office. Due to its limitations with large data volumes, automating data preparation and utilizing Power BI's features for user interactivity and data visualizations, this project has been successfully deployed to users, resulting in significant time savings and a more efficient decision-making process.

## Visualization
#### Summary
This Power BI report comprises multiple views, each dedicated to different revenue buckets, complemented by a summary page that compares each revenue stream, emphasizing those with significant impact. The summary page is structured with a clear visual hierarchy to facilitate rapid data analysis. Interactive slicers on the left side allow users to select specific criteria for customized analysis. Metric cards for each revenue bucket display actual revenue, expected revenue, and variance, helping users pinpoint the highest and lowest revenue streams of the month. Additionally, a summary table on the left provides these metrics alongside real-time driver commentaries inputted via a Power Apps application. Below, a variance distribution by geography and revenue buckets enhances comparability.
![image](https://github.com/user-attachments/assets/9400d79e-5b22-4f62-93a8-20e175302c66)

#### Details
All revenue buckets can be navigated through separate navigation buttons, each offering detailed information on revenue, units, calculation specifics, and the analytics page accessible via *radio buttons*. This functionality is achieved using bookmarking capabilities within Power BI.
- The **Revenue Details** section features a matrix table visualization displaying actual revenue by month. Users can drill down into details starting from company code and product family, all the way up to customer level.
![image](https://github.com/user-attachments/assets/de7d5f6b-aa16-44fe-97b8-799e37490b1f)



- Units/Volume Details the same with Revenue details, also features a matrix table visualization displaying actual units/volume by month. Users can drill down into details starting from company code and product family, all the way up to customer level.
  ![image](https://github.com/greatcyan/cyrus-baruc-data-analytics-portfolio/assets/95137493/ba398152-efae-4950-a7d0-ec46bdd30f10)
- The Calculation Details section displays metrics and calculations using a matrix table, designed for in-depth analysis and data validation.
  ![image](https://github.com/greatcyan/cyrus-baruc-data-analytics-portfolio/assets/95137493/39108baf-9dd3-4f60-a64f-cb7dea9c7386)
- The Analytics View is a dashboard providing a quick snapshot of revenue metrics for swift insights and data comprehension. At the top, main metric cards display key figures. The middle left section shows variance by geography, while the middle right section illustrates revenue and volume trends over the past 12 months. At the bottom, the top and bottom three variances are detailed by geography, product family, and customer. Slicers are synchronized across other pages, ensuring consistent filtering and analysis throughout the report.
  ![image](https://github.com/greatcyan/cyrus-baruc-data-analytics-portfolio/assets/95137493/f9e68e22-2e80-4b21-bcbf-8d4d9401d61e)

## Data Model Structure
After the ETL process, the model applied in this Power BI project is a snowflake schema. Summarized and aggregated revenue bucket tables into a single table to reduce complexity. Created dimension tables for calendar, geography, product family, and customer to lessen ambiguity and optimize query performance at the front end, preventing loading delays in rendering visuals.

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

### Stakeholder Impact
![image](https://github.com/greatcyan/cyrus-baruc-data-analytics-portfolio/assets/95137493/4a80b8b5-0fca-4782-a4cc-5d271258ee11)












