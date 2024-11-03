# Sales-Analytics-for-Video-Games
Sales Analytics for Video Games
![image](https://github.com/user-attachments/assets/28247f1e-1d7a-40c8-9cd9-d6f013a008e3)

Certainly! Here’s a step-by-step guide to implementing your interactive video game sales dashboard in Tableau:

Step 1: Import the Data
Open Tableau.
Connect to your data:
Click on "Connect" and choose "Text File".
Navigate to your CSV file and select it.
Step 2: Explore Your Data
Examine the dataset:
Check the fields available: Rank, Name, Platform, Year, Genre, Publisher, and sales figures for different regions.
Step 3: Create Parameters
Create a Parameter for Sales Zones:
Right-click in the Data pane and select "Create Parameter...".
Name it "Zone Sales".
Set Data type to String.
Choose List under Allowable values and add:
EU Sales
Global Sales
Japan Sales
North American Sales
Other Sales
Click OK.
Step 4: Create Calculated Field
Create a Calculated Field for Sales Calculation:
Right-click in the Data pane and select "Create Calculated Field...".
Name it "Zone Sales Calculation".
Enter the following formula:
sql
Copy code
CASE [Zone Sales]
  WHEN 'EU Sales' THEN [EU Sales]
  WHEN 'Global Sales' THEN [Global Sales]
  WHEN 'Japan Sales' THEN [Japan Sales]
  WHEN 'North American Sales' THEN [North American Sales]
  WHEN 'Other Sales' THEN [Other Sales]
END
Click OK.
Step 5: Create the First Visualization
Create a New Worksheet:
Click on the "New Worksheet" icon.
Drag Year to the Columns shelf.
Drag the "Zone Sales Calculation" to the Rows shelf.
Right-click on the "Zone Sales Calculation" in the view and select "Filter" to remove null values.
Step 6: Show Parameter Control
Show the Parameter Control:
Right-click on the "Zone Sales" parameter in the Data pane and select "Show Parameter Control".
Step 7: Enhance the Visualization
Customize Your Visualization:
Rename the worksheet to something meaningful (e.g., "Sales by Year").
You can duplicate this sheet if you want to create different types of visualizations (like area charts).
Step 8: Create Additional Parameters for Date Filtering
Create Parameters for Date Filtering:
Create two new parameters named "Start Date" and "End Date" with integer data types.
Create a calculated field named "Sales Period" with the formula:
sql
Copy code
IF [Year] >= [Start Date] AND [Year] <= [End Date] THEN 1 ELSE 0 END
Set this calculated field as a filter in your worksheet to only include values where Sales Period = 1.
Step 9: Create Additional Visualizations
Create More Worksheets:
Create additional worksheets for visualizing:
Top 10 Names by Sales
Top 10 Platforms by Sales
Total Sales by Genre
Ensure all worksheets use the same parameters for interactivity.
Step 10: Format Worksheets
Format Your Worksheets:
Adjust the colors, font sizes, and labels in the Format pane.
Add titles and ensure everything is visually appealing.
Step 11: Create the Dashboard
Create a New Dashboard:
Click on the "New Dashboard" icon.
Set the dashboard size based on your preferences.
Drag and drop your worksheets onto the dashboard canvas.
Step 12: Arrange and Finalize the Dashboard
Arrange Your Dashboard Elements:
Position the worksheets logically for better user experience.
Add interactivity by ensuring that filters and parameters are accessible.
Step 13: Test the Dashboard
Test Functionality:
Check all filters and parameters to ensure they work as intended.
Make any necessary adjustments.
Step 14: Publish the Dashboard
Publish Your Dashboard:
Once satisfied with your dashboard, publish it to Tableau Public or your Tableau Server.
Step 15: Share Your Work
Share the Published Dashboard:
Share the link with others or embed it into websites as needed.
By following these steps, you should be able to create a comprehensive and interactive video game sales dashboard in Tableau!
