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
     
![Screenshot (654)](https://github.com/user-attachments/assets/cd6bb04a-3fe2-48b2-87a1-5eb5fb6e083d)
![Screenshot (655)](https://github.com/user-attachments/assets/5add113c-4cb7-42ca-8861-18153e9d8221)
![Screenshot (656)](https://github.com/user-attachments/assets/f6798a81-0220-4c83-860a-0aace9753f28)
![Screenshot (657)](https://github.com/user-attachments/assets/535dda03-be1d-4bf3-b129-f09ebdf09d67)
![Screenshot (658)](https://github.com/user-attachments/assets/311fe713-a423-4b9c-84a9-cc578614f97c)
![Screenshot (659)](https://github.com/user-attachments/assets/95d1b037-3d35-4925-9850-1ed59dac3796)
![Screenshot (660)](https://github.com/user-attachments/assets/eae5087f-39d5-49bb-ad7c-7526bc59f230)
![Screenshot (661)](https://github.com/user-attachments/assets/b78267c6-8c48-46ad-bfff-d99445bf25a1)
![Screenshot (662)](https://github.com/user-attachments/assets/3ee8fdee-e9f0-460d-a7a5-440e684c3d12)
![Screenshot (663)](https://github.com/user-attachments/assets/2f189eca-8555-43e5-bace-a1831d6726af)
![Screenshot (664)](https://github.com/user-attachments/assets/42236811-e526-4f50-b703-7b73006002f0)
![Screenshot (665)](https://github.com/user-attachments/assets/0b7fc639-fde3-488a-a189-74487b0c93c5)
![Screenshot (666)](https://github.com/user-attachments/assets/4259a48f-4972-4d68-b69f-5fb8f8edecea)
![Screenshot (667)](https://github.com/user-attachments/assets/be7ef72f-51c7-4676-9d02-cb83638a23cc)
![Screenshot (668)](https://github.com/user-attachments/assets/8afd59c1-b533-4ce0-a2a1-a24e0ca3d85e)
![Screenshot (669)](https://github.com/user-attachments/assets/2901d230-7fb6-4124-af82-8de77e9b0eb8)
![Screenshot (670)](https://github.com/user-attachments/assets/75b4673a-fb87-441a-9dbb-7f7780cc3fe6)
![Screenshot (671)](https://github.com/user-attachments/assets/7cc9b056-ad2c-47f2-9f0a-5d8acd302752)
![Screenshot (672)](https://github.com/user-attachments/assets/c15c00f7-4b1f-44e5-a477-e60e586eb007)
![Screenshot (673)](https://github.com/user-attachments/assets/3d7a4516-3cc1-4d6f-8106-3e6b86d63f98)
 
     
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
     
     
    
