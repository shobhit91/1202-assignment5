# 1202-assignment5

![Python Logo](https://www.python.org/static/community_logos/python-logo.png "Python logo")

This repository is for assignment - 5 for 1202 - DATA ANALYSIS TOOLS ANALYTICS. In this Python code is retriving the 1000 records from master dataset and exporting the CSV of the 1000 records based on filter.

# Python code description

1. First of all, I have imported required libraries such as numpy, scipy, pandas, matplot and seaborn by using following piece of code -

```
#Import Python Libraries
import numpy as np
import scipy as sp
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns
```

2. Then I have imported the dataset from my local machine by using following code
```
# Set file path to a variable
input_file_path = r"C:\Users\hp\Documents\PythonDATA1202-Omar\youtube_dataset.csv"
```

3. Once dataset is imported then I have read the dataset by using Python's default function 
```
# Read Data into a DataFrame
df = pd.read_csv(input_file_path)
```

4. Then after I have used the Python's head() function to check the dataset's first record
```
#show data from dataset
df.head()
```

5. In the next step I have used another Python function named as info(). this function gave me information about the dataset along with their datatype and length.
```
#get dataset information
df.info()
```

6. After checking the dataset I have applied the filter based on the requriment by using following piece of code
```
df['channeltype'] = df['channeltype'].astype('|S')
```

7. In the next step I have retrived the first 1000 records based on the filter from the actual dataset
```
#limit of records
df1=df.head(1000)
```

8. Then after I have created my custom function to create a histogram graph based on the dataset

```
#custom function for histogram graph
def histogram_function():
fig=plt.figure(figsize=(20,20))
#Use matplotlib to draw a histogram of a salary data
plt.hist(df1['channeltype'],bins=15, density= True)

#call function to show graph
histogram_function()
```


9. In the last step I have used another prebuild function to export the filtered records to CSV, this function created a CSV file on my machine with name "1000_records_new.csv".

```
#export 1000 records to a new csv file
df1.to_csv('1000_records_new.csv')
```

10. That's all, happy coding
