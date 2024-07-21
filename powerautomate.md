## Power BI to Sharepoint Data Extract Automation
The Power BI to SharePoint Data Extract Automation process is designed to streamline and automate the extraction and transfer of data from Power BI reports to SharePoint. This integration leverages Power Automate (formerly Microsoft Flow) to facilitate the seamless export of data, ensuring that critical insights and reports generated in Power BI are efficiently archived and accessible within SharePoint.

1. Begin by publishing the semantic model in the Power BI Workspace. This model defines the data structure and relationships required for generating meaningful reports and analysis.
![image](https://github.com/user-attachments/assets/a36552eb-a49e-45a7-9b65-d6ef39c876dd)

2. Develop a DAX (Data Analysis Expressions) query to extract the desired table output from Power BI. This query enables the selection of specific data subsets or aggregated metrics needed for reporting. This is also the query to add in parameter of the run **data against the dataset action**.
![image](https://github.com/user-attachments/assets/9509c299-c645-465d-988b-5baed84172cc)

3. Design a flow in Power Automate to handle the automation of the data export process. This flow will manage the steps required to move data from Power BI to SharePoint. Establish the required connections between Power BI, Power Automate, and SharePoint to ensure smooth data transfer. Set up a system for dynamically naming exported files and specifying their destination directory within SharePoint, enhancing organization and retrieval.
![image](https://github.com/user-attachments/assets/80a643dd-d6b8-42a9-9c79-97230c1a40a4)

![image](https://github.com/user-attachments/assets/b2fdf131-34d1-48dc-aa9a-690d8c78fe09)

![image](https://github.com/user-attachments/assets/227c5d8b-e474-477f-aa03-70102ed289d1)

![image](https://github.com/user-attachments/assets/3aeaeda7-2eef-4cbc-bf05-fd18f87d24ba)

4. With the automation in place, data from Power BI reports is automatically exported to SharePoint, reducing the need for manual intervention and ensuring timely updates.
![image](https://github.com/user-attachments/assets/42ecbd42-3e85-4c6e-b36d-2220d4e95198)



