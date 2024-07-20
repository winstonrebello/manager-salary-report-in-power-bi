# **Manager Salary Report in Power BI**

## This project uses Power BI Desktop and Excel for cleaning survey of manager salary and analyzing data. 

## **Key Insights:**
![image](https://github.com/user-attachments/assets/7ea8dbfa-6b7f-4e42-a6bc-0e80a3e6ba38)


## **Built with:**
1. Power BI Desktop
2. Jupyter Notebook

## **REPORT**
![image](https://github.com/user-attachments/assets/8162d735-53de-4161-9340-895c40384a20)

![image](https://github.com/user-attachments/assets/286c1993-5049-4f4f-93d3-b7777b46ed20)

## **Data cleaning process**

### SOME SETPS TO CLEAN THE NOICE
1. Checking for null values :- data.isna().sum()
2. Rename columns :- data.rename(columns={' age': 'age', ' industry ': 'industry' }, inplace=True)
3. To chek data types :- data.dtypes
4. Fill null values with other :- data[' race'] = data[' race'].fillna('other') 
5. TO find count of unique values :- data['education'].value_counts() 
6. TO change object to float :- data['salary'] = data['salary'].str.replace(',', '').astype(float)
7. To remove text :- data['m_exp'] = data['experience'].str.replace(' years', '').str.replace(' year or less', '').str.replace('or more', '')
8. A function to remove hyphen and counting average value :- ![image](https://github.com/user-attachments/assets/8f6f6e05-9421-4589-aab1-b17cc7a82588)
9. Eliminate irrelevant rows :- data = data[data['m_exp'] <  data['m_age'] - 10 ]
10. Converting time format :- data['date'] = pd.to_datetime(data['Timestamp'], format='%B %d, %Y')
11. Using lambda function to find manager in string :- data.loc[:, 'M_or_other'] = data['Job title'].apply(lambda x: 'Manager' if 'manager' in x.lower() else 'Other')

## **Reference**

Dataset fetched from https://oscarbaruffa.com/messy/
