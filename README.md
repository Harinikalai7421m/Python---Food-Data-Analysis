# Python Food-Data-Analysis
A food data analysis is done to know the profit, cost of the food and to visualize for insights.

### Project Overview
   This project involves analyzing a dataset related to the detail regarding order ID, Customer ID, Order date and time, delivery date and time, sourced from Kaggle, using Python. The goal is to uncover meaningful insights about various discount and offers, delivery fee, payment processing fee it describe the entire information about the food delivery.

### Data Sources. 
Sales data:
    The primary data set used for this analysis is taken from the kaggle dataset.

### Tools.
    Excel - Data is stored.
    Python - Data analysis.

### Steps
   In kaggle select a data set and download the csv file and convert it into excel.
   Open google collab or jupyter notebook and upload the excel csv file (food delivery costs).
   
   import pandas as pd        -  were pandas isused for data manipulation.
   df =pd.read_csv ('food delivery costs.csv')     - data ia displayes
   df.head()      - the 1st 5 rows are displayed.
   
   df.info()      - the data type is displayed,
   df['Order Date and Time'] =pd.to_datetime(df['Order Date and Time'])
   df.info()
   
   df['Delivery Date and Time'] = pd.to_datetime(df['Delivery Date and Time'])
   df.info()
   
   df['Discounts and Offers'] = df['Discounts and Offers'].apply(extract)
   df['Discounts and Offers']       - the discount based on the offers are shown.
   df - to read data 
   
   def removep(value):
   if "%" in value:
     a=value.replace("%", "")
     return float(a)
  else:
     return float(value)
     
     df['Discounts and Offers'] = df['Discounts and Offers'].apply(removep)
     df
     
     df.loc[(df['Discounts and Offers']<=15),'Discounts and Offers'] = (df['Discounts and Offers']/100)*df['Order Value']
     df
     
     df['Discounts and Offers']=df['Discounts and Offers'].fillna(0)
     df
     
     df['Costs']=df['Delivery Fee'] + df['Discounts and Offers']+df['Payment Processing Fee']
     df
     
     df['Profits']=df['Commission Fee'] - df['Costs']
     df
     
     df.Profits.sum()
     
     cost_dist = df[['Delivery Fee','Discounts and Offers','Payment Processing Fee']].sum()
     cost_dist
     
     import matplotlib.pyplot as plt      - to display the figure.
     
     plt.pie(cost_dist,labels = cost_dist.index, autopct = "%1.2f%%")          # .2 refers to the precision of percentage value
     plt.show() - calculates the sum of elements.
     
     profits = df[['Costs','Commission Fee','Profits']].sum()
     profits
     
     plt.bar(profits.index,profits)         - this creates bar graph.
     plt.xticks(rotation=90)          - this rotates the x-axis labels by 90 degrees for better readability.
     plt =plt.figure(figsize=(3,3))         - to create a new figure with a specific size.
     plt.show()           - this is used to display the plot.
     
![Screenshot (549)](https://github.com/user-attachments/assets/38ece127-1449-4287-8803-3be58354154f)

![Screenshot (550)](https://github.com/user-attachments/assets/2a866f9a-57c6-4657-840f-215a38a31751)

![Screenshot (551)](https://github.com/user-attachments/assets/d4973177-9107-4615-9f14-0422cdd4ed5a)

![Screenshot (552)](https://github.com/user-attachments/assets/ad037de5-abed-4dc5-85f8-a15877c19b69)

![Screenshot (553)](https://github.com/user-attachments/assets/27992353-197c-47c8-aab5-9e11881b96bc)

![Screenshot (554)](https://github.com/user-attachments/assets/c79c90d3-0d05-4d2d-b218-8c97aa52e7b8)

![Screenshot (555)](https://github.com/user-attachments/assets/82760677-00f5-48ad-a205-84fef1231661)

![Screenshot (556)](https://github.com/user-attachments/assets/79d0b4a0-fcef-47fb-8308-4e1623c6e7d0)











     
     
     
  ### Result.
     The discount and offer is 55.97% , Delivery fee is 21.56% , Payment processing fee is 22.47%
     As a result Costs  is 132741.85 (cost is increasing) , Commission Fee is 126990.00 (increasing) but Profits  is -5751.85 (decreasing).

  ### Analysis.
     Use data analysis to determine the minimum effective discount required to attract customers without eroding profits.
     Work with delivery service providers to negotiate lower rates.
     Encourage customers to use payment methods with lower fees (e.g., bank transfers)
     Implement measures to minimize waste in production or logistics
     Focus on platforms with lower fees or better conversion rates.
     Adjust pricing to reflect costs while maintaining competitiveness.

  ### Recommendation.
     Regularly analyze financial metrics to track the impact of implemented changes.
     Experimentation: Test strategies in small increments to determine their effectiveness before scaling.
     Customer Feedback: Understand customer behavior and preferences to refine offerings.
     
     
    
