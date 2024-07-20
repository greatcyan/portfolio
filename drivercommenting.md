## Real-time Commenting App

### Overview
This project, developed in Power Apps, is a crucial component of the Revenue Analytics project. Its primary function is to automate real-time commenting on the top and bottom drivers, dramatically reducing processing time from 4 hours to just seconds. By leveraging API, Power BI Streaming datasets, and Power Apps, this solution ensures swift and efficient analysis and commentary, providing immediate insights and enhancing decision-making capabilities.

### Tools Used
- **Power Apps:** For creating the user interface and data input mechanism.
- **Power BI:** For real-time data visualization.
- **Push Dataset:** For handling real-time data updates.

### Step-by-Step Implementation
#### 1. Create the Push Dataset
In the Power BI Workspace, click the New button and select the Streaming dataset option. A window titled "Streaming dataset" will appear, allowing you to choose the data source. For this project, I selected API.
![image](https://github.com/user-attachments/assets/94fddd27-c900-4b10-a971-301a37a7f28c)

Next, give a name to your dataset and set up the column fields.
![image](https://github.com/user-attachments/assets/90dbb974-9caf-4b92-87ac-76829b9b8705)

Once done, the streaming dataset is added to the workspace, generating API information as shown in the snapshot.
![image](https://github.com/user-attachments/assets/af671dfb-5ef1-48e7-858c-6831f98f0166)

Using this API information, we can then integrate it into our Power Apps for real-time data entries for each user's inputs.

#### 2. Develop the Power Apps Application:
I developed the user interface in Power Apps Studio using a mobile layout to fit within the Power BI Dashboard. The app has five main components: a dropdown option for the revenue bucket, a dropdown option for geography, a user input box for free text, a reset input button, and a submit button for finalizing entries. 
![image](https://github.com/user-attachments/assets/4c1c5db6-be01-43c0-846a-7c8a5addca34)

On the backend, all details inputted by the user are captured and automatically loaded into our push dataset through the code embedded in the OnSelect property of the Submit button. Here is the code:

Setting the Revenue_Drivers variable
![image](https://github.com/user-attachments/assets/a38bd860-0474-4f92-b472-878b9105d063)
This Set function creates a record called Revenue_Drivers with the following fields:
- Bucket: The selected value from the bucketdropdown.
- Geo: The selected value from the geodropdown.
- Submitted on: The current date and time.
- Comment: The text entered in the commenttextinput field.
- Relationship ID: A unique identifier created by concatenating the values from the bucketdropdown and geodropdown.

Converting the record to JSON
![image](https://github.com/user-attachments/assets/090a4f43-a4e4-475f-b669-13894d09c306)
- This Set function converts the Revenue_Drivers record into a JSON object and stores it in the Drivers_Data variable.
- JSON(Revenue_Drivers) converts the record to a JSON string.
- ParseJSON(JSON(Revenue_Drivers)) parses the JSON string back into a JSON object.

Adding rows to the Power BI dataset
![image](https://github.com/user-attachments/assets/146010bd-584c-4a85-ba1b-4a417435865f)
PowerBI.AddRows is a function that sends data to a Power BI streaming dataset.
- "f429cde2-6dde-4e2b-bcb6-fe2bc186a170" is the Workspace ID where the dataset is located
- "3f9a7849-caff-44fe-bcf7-c807c7b21a1b is the dataset ID

This app is ready and can be added to the Power BI dashboard for easy access by users. We can then add the push dataset as our source in our Power BI project, and update and configure the data model to include our streaming dataset.

#### How to use the Commenting App
1. Enable the Commenting App
- In the Revenue Analytics Summary page, switch on the toogle button to show the commenting app.
![image](https://github.com/user-attachments/assets/a7f94402-4ff7-4ad0-85ba-2cc61ee01541)

2. Input Data
-  Select the appropriate revenue bucket and geography from the dropdown options.
-  Enter your driver commentaries and analysis in the provided text box.

3. Submit Your Comments
-  Once you have completed your input, click the submit button to finalize your entry.

4. View Comments
 - Hover over the summary table to view the driver comments in a tooltip.
![image](https://github.com/user-attachments/assets/0efdfc10-67fe-4b96-8012-c00cd14d2351)

## Impact

The new Power Apps automation in the Revenue Analytics project has replaced the outdated Analyze in Excel method, enabling real-time feedback directly within Power BI. This shift has accelerated data analysis and decision-making by providing immediate insights on revenue drivers. Improved collaboration and accuracy are achieved as stakeholders engage directly with reports, reducing communication delays and errors. The solution also enhances workflow efficiency by eliminating the need for manual data transfers and is scalable to accommodate business growth. Overall, these improvements facilitate quicker responses to trends and opportunities, driving strategic growth.
