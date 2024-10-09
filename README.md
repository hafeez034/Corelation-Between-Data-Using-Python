# Exploratory Data Analysis,Handling values and finding corelation between data 
## Importing python libraries
#### import pandas as pd  
#### import seaborn as sn
#### import matplotlib
#### import matplotlib.pyplot as plt
#### plt.style.use('ggplot')
#### from matplotlib.pyplot import figure 
#### %matplotlib inline
#### matplotlib.rcParams['figure.figsize'] = (15, 8)


#### sn.heatmap(df.isnull())
#### plt.show()

![image](https://github.com/user-attachments/assets/297cd65d-e8fc-473a-9766-b994d23dd83a)

![image](https://github.com/user-attachments/assets/80b67a34-57bf-4b0f-8d58-15c97af2487c)


## Filling null mean values for numerical Data

![image](https://github.com/user-attachments/assets/32b3f7b5-1c08-4087-856f-30f332b7230e)

## In this Step We have added new non-null values to the original df
df[df.select_dtypes(include='float').columns] =df2      

df[['Score','votes','budget','gross']] = df[['Score','votes','budget','gross']].astype("int64")



## Now Finding corelation between different parameters
plt.scatter(x=df['budget'], y=df['gross'])
plt.title('Budget Vs Gross Earnings')
plt.xlabel('Budget')
plt.ylabel('Gross')
plt.show()

![image](https://github.com/user-attachments/assets/42a1b302-16a0-4499-a4ba-3dc5bb75fb6e)


## Using Seaborn For Graph
sn.regplot(x='budget',y='gross',data=df,scatter_kws={'color':'orange'} , line_kws={'color':'blue'})

![image](https://github.com/user-attachments/assets/0dd8789c-5279-4844-b091-9ae648cc3851)

## Its not showing corelation as some data in object type to get corelation in this step we are converting it to numerical code


df_numerized = df

for col_name in df_numerized.columns:
    if(df_numerized[col_name].dtype =='object'):
        df_numerized[col_name] = df_numerized[col_name].astype('category')
        df_numerized[col_name] =  df_numerized[col_name].cat.codes
        
df_numerized

![image](https://github.com/user-attachments/assets/9deab655-0626-41c5-a67a-389fa0841cd8)

![image](https://github.com/user-attachments/assets/233ba38a-4bea-46c4-950c-32c1c22a2285)

![image](https://github.com/user-attachments/assets/64c04a2c-8ad0-49a4-b86e-700c3304b260)

![image](https://github.com/user-attachments/assets/b7f61233-4f9f-4d85-a684-0b5ac9a4fcc1)

![image](https://github.com/user-attachments/assets/b7385c29-069a-4cb6-aa19-7cb81da7459c)


























