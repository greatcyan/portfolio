## [⬅️Back](./)

## Occupancy Cost Center Report

This is a single page Power BI report aim to provide analysis of the monthly costs and expenses to occupancy-related [cost centers](https://www.investopedia.com/terms/c/cost-center.asp){:target="_blank"}. The report design is aligned to the the stakeholder's requirements to show costs and expenses by general ledger, prior year and current year comparison, and capability to drill down the details, allowing stakeholders a better understanding of costs.

### The Process

The data is sourced from SAP Business Warehouse, where it undergoes extraction and normalization into various tables grouped by geographical categories. Subsequently, the data is saved into Power BI dataflows. Measures and calculations are created using Data Analysis Expressions (DAX) and data modeling techniques. Following data cleaning and finalization, the dashboard is designed to align with stakeholders' requirements. Upon validation of values, acess and visual presentation, the report is deployed and made available for end-users to fulfill their reporting needs. Scheduled refresh is then set in the Power BI Service (the Software as a Service (SaaS) part of Power BI) to ensure that the displayed data is updated.
![image](https://github.com/greatcyan/cyrus-baruc-data-analytics-portfolio/assets/95137493/182f57a4-6fe6-4aab-a8ef-b3cd32206dfc)

### The Final Output
The report empowers end-users to explore insights based on their chosen parameters and slicers. It is designed and organized with a [visual hierarchy](https://www.interaction-design.org/literature/topics/visual-hierarchy){:target="_blank"} for better data comprehension. Additionally, users can extract data from the report using the export data option, enabling further analysis based on their reporting needs.
![image](https://github.com/greatcyan/cyrus-baruc-data-analytics-portfolio/assets/95137493/8cd98ece-bc3a-4629-995c-999198e475d6)

### More About the Report
#### The Slicers
On the left side of the dashboard, users can find the slicers. These slicers allow users to filter and drill down into details based on various categories such as month, geography, functional area, account group (GL), and cost center. The data across other visuals will automatically update based on the specified slicers. Users can specify their desired categories by selecting the slicers, eliminating the need to create multiple reports for different users.
![image](https://github.com/greatcyan/cyrus-baruc-data-analytics-portfolio/assets/95137493/043430c1-20ab-4066-8905-735aaacb6119)

At the upper right of the report, users can find a currency type slicer displayed as a button. This slicer allows users to view actual costs and expenses based on their currency preference. The numbers displayed in other visuals will also automatically adjust accordingly. 
![image](https://github.com/greatcyan/cyrus-baruc-data-analytics-portfolio/assets/95137493/29c5c61f-0d1d-4d78-9071-8111546cd7e7)

#### Last Refresh Time
Every time the scheduled refresh of the data source (dataflows and the semantic model) is complete, this dynamic label for the last refresh time is also updated. It is an essential part of the report to ensure that the data being analyzed or reported is updated and accurate.
![image](https://github.com/greatcyan/cyrus-baruc-data-analytics-portfolio/assets/95137493/75643cbf-33be-4ddd-bc89-f7b9577be9ab)

#### Dynamic Heading Label
The dynamic heading label changes based on user interaction or slicers being selected. Its purpose is to provide context and clarity to the user about the content or context of the information they are viewing. 
![image](https://github.com/greatcyan/cyrus-baruc-data-analytics-portfolio/assets/95137493/a5ea567b-c699-4499-bae8-e89c2740f6a8)


#### The General Ledger Summary Table
The table presents a comparison of actual costs and expenses between the prior year and the current year, categorized by [general ledger (GL Accounts)](https://www.investopedia.com/terms/g/generalledger.asp){:target="_blank"}. Users can efficiently identify the top and bottom GL by actual expenses by sorting the table based on prior-year actuals, current-year actuals, or the difference (delta) between them.
![image](https://github.com/greatcyan/cyrus-baruc-data-analytics-portfolio/assets/95137493/a9ca948f-9474-4298-856b-8c6d2385c9d4)



