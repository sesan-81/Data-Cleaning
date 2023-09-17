# Data-Cleaning Process

Introduction

The process of data cleaning is often an underappreciated but vital step in the journey from raw data to actionable insights. In the world of data analysis and data science, data is seldom pristine upon arrival. Often, it arrives in various states of disarray, riddled with inconsistencies, errors, and gaps. This report is a comprehensive exploration of the meticulous data cleaning process, a critical phase that precedes any meaningful analysis. Data cleaning is the unsung hero of data analysis. It is the process of identifying, correcting, and handling errors, inconsistencies, and missing values in datasets. While it may not be as glamorous as predictive modeling or data visualization, it is the foundation upon which accurate and insightful analyses are built.

Why is data cleaning so crucial?
●	Data Accuracy: Accurate data is paramount. Incorrect or inconsistent data can lead to erroneous conclusions, potentially causing costly mistakes or missed opportunities.
●	Decision-Making: In a data-driven world, decisions are only as good as the data they are based on. Clean data ensures that decisions are well-informed and reliable.
●	Model Performance: For machine learning and statistical models to perform at their best, they require clean, consistent, and complete data. Garbage in, garbage out is a common adage in data science.
●	Data Trustworthiness: Data is often collected from various sources and systems. Cleaning ensures that data can be trusted, even when it originates from disparate places.

The Dataset: Unveiling Imperfections
Our journey begins with a dataset, sourced from the file "assignment_3_data.csv." This dataset is like many others; it has the potential to reveal valuable insights, but only if we're willing to roll up our sleeves and address its imperfections. The dataset contains a multitude of columns, each representing different aspects of the data. However, upon initial examination, it becomes evident that it is far from pristine. Missing values lurk in certain columns, duplicates may be lurking in the shadows, and inconsistencies in formatting and naming threaten to confuse and mislead. Our objective is clear: to transform this dataset into a clean, reliable, and well-structured resource for analysis. To achieve this, we embark on a comprehensive data cleaning journey, meticulously addressing each challenge that the dataset presents. This report is a detailed roadmap of our data cleaning expedition. We will leave no stone unturned as we explain, justify, and execute each step along the way. As we navigate this process, we'll discover not only the technical intricacies of data cleaning but also the broader significance it holds in the realm of data analysis and decision-making. Are you ready to dive into the world of data cleaning? Buckle up, as we embark on a journey to transform imperfect data into valuable insights. From handling missing values to standardizing column names, we will illustrate why each step is necessary and how it contributes to the overarching goal of data quality.

Step 1: Data Loading
The initial phase of the data cleaning process involves loading the dataset from the provided CSV file. This step is critical as it sets the foundation for all subsequent data manipulation and cleansing tasks. We employ the versatile Pandas library, a fundamental tool for data handling and analysis in Python, to accomplish this.

![image](https://github.com/sesan-81/Data-Cleaning/assets/104377031/aeb98986-e060-43c5-a5f6-67fd6876ecb5)

 
Fig 1: Data Loading

●	Importing Necessary Libraries: To get started, we import the required Python libraries, with Pandas taking center stage. This powerful library provides data structures and functions that are essential for reading, processing, and transforming data.
●	Loading the Dataset: We proceed to load the dataset from the CSV file using the pd.read_csv() function. This function reads the data into a Pandas DataFrame, which is a two-dimensional, tabular data structure resembling a spreadsheet.
●	Viewing the dataset: Using the head() function, we printed the first few rows of the dataset on the output cell. We viewed the dataset including the different columns, inspecting the dataset's structure, examined its contents, and began the process of identifying and rectifying data issues.

Step 2: Data Exploration
After loading the data, it's a good practice to perform an initial exploration and inspection. This includes checking the first examining column names, data types, data summary and identifying potential issues such as missing values, duplicates, and inconsistencies.
a)	Data Summary
To gain a preliminary understanding of the dataset's characteristics, we start by examining the summary statistics. This provides key insights into the distribution of numerical data, including measures such as mean, median, standard deviation, and quartiles.

![image](https://github.com/sesan-81/Data-Cleaning/assets/104377031/23fd2e15-2619-48c3-b74b-27c355f21abb)

 
Fig 2: Data Summary

The summary statistics help us identify outliers, understand data distributions, and detect potential errors or anomalies in the data.
b)	Data Information
Next, we investigate the dataset's information to obtain a comprehensive overview of its structure, including the data types of each column and the presence of any missing values.

![image](https://github.com/sesan-81/Data-Cleaning/assets/104377031/bd744fbd-37fe-4570-a04a-536cebf336da)

 
Fig 3: Data Information

Understanding the data types is crucial as it informs subsequent data cleaning and transformation steps. Also, checking for missing values is essential to assess data completeness.

c)	Missing Values
One common data quality issue is missing values, which can adversely affect analysis and modeling. We systematically assess the dataset for missing values in each column.

![image](https://github.com/sesan-81/Data-Cleaning/assets/104377031/7480d568-783d-405a-9230-73ff4016344e)

 
Fig 4: Missing Values

Identifying columns with missing values is the first step in deciding how to handle them. Depending on the extent of missingness and the nature of the data, we may choose to remove rows with missing values, impute missing values with appropriate strategies, or retain the data as-is.

Step 3: Handling Missing Values
To address the issue of missing values, we take the following action:
●	Dropping Null Values: In this specific dataset, we have opted to remove rows with missing values. The dropna method is applied to eliminate rows containing any null values, ensuring data integrity.

![image](https://github.com/sesan-81/Data-Cleaning/assets/104377031/e31592e5-bb07-48f3-9de5-00d940309644)

 
Fig 5: Handling Missing Values

The decision to drop rows with missing values should be made judiciously, considering the dataset's size, the significance of the missing data, and the objectives.

Step 4: Data Deduplication
Duplicate records within a dataset can distort analysis results and lead to incorrect conclusions. To identify and handle duplicate rows, we examine the dataset for duplicated records to remove them. The presence of duplicate records is assessed based on all columns in the dataset. In this dataset, we did not identify any duplicates, which inferred that we had a dataset with unique records.

Step 5: Cleaning Column 'x41' - Price
Data cleaning often involves addressing issues within specific columns. In this dataset, the 'x41' column contains price values with non-numeric characters and formatting inconsistencies. To clean this column, we define a custom function, clean price, which removes non-numeric characters and converts the values to float data type.

 ![image](https://github.com/sesan-81/Data-Cleaning/assets/104377031/455bc1ff-395d-485d-8b54-fdc020263c6a)

Fig 6: Column leaning ,x41

Cleaning the 'x41' column is essential as it ensures that the price values are in a consistent numerical format, facilitating subsequent analysis tasks such as calculations and aggregations.

Step 6: Printing Unique Values in Categorical Columns
For categorical columns, it is essential to identify unique values and check for inconsistencies, misspellings, or unexpected entries. To facilitate this, we define a function, print_unique_values, which iterates through each column and prints unique values for categorical columns. 

![image](https://github.com/sesan-81/Data-Cleaning/assets/104377031/36072242-34e1-48b6-9ff5-e31ee04364b4)


Fig 7: Printing Unique Values in Categorical Columns
 
Using this function, we can inspect unique values in the dataset's categorical columns to identify and rectify any inconsistencies or misspellings. This step helps ensure that the categorical data is correctly labeled, spelt and ready for analysis.

Step 7: Cleaning Column 'x35' - Day of the Week
Another common data cleaning task is standardizing data values. In the 'x35' column, we encounter abbreviated day names ('wed,' 'thur,' 'fri'), which should be expanded to their full forms ('Wednesday,' 'Thursday,' 'Friday'). We achieve this by defining a day mapping dictionary and creating a new list with expanded day names. The 'x35' column is then updated with the expanded day names.

![image](https://github.com/sesan-81/Data-Cleaning/assets/104377031/0cffda0d-ba04-4815-b63f-ae8e383c47e5)

Fig 8: Cleaning Column 'x35' 

Standardizing the 'x35' column ensures consistency in the representation of days of the week, making the data more understandable and interpretable. In the process of standardizing the 'x35' column, we also address a specific issue where 'thurday' is misspelled as 'thurday.' To ensure consistent spelling, we correct this error using the str.replace method.

Step 8: Cleaning Column 'x45' - Percentage
Data cleaning also involves ensuring consistent formatting and units. In the 'x45' column, we encounter percentages represented with '%' symbols. To facilitate numerical analysis, it is essential to remove these symbols and convert the values to numeric format. Removing the '%' symbol from the 'x45' column is crucial for accurate numerical calculations. Failure to do so would result in the 'x45' column being treated as a string with '%' characters, which could lead to erroneous analysis results.

Step 9: Handling Specific Corrections
Data cleaning may require addressing specific issues or anomalies in the dataset. In this dataset, we identified and corrected specific misspellings and abbreviations in certain columns ('x93,' 'x68,' 'x34'). We use correction dictionaries to map incorrect values to their correct counterparts. 
Justification for handling specific corrections:

●	Column 'x93': The correction of 'euorpe' to 'europe' is essential for ensuring accurate geographical analysis. Inconsistent or misspelled values can lead to incorrect interpretations.
●	Column 'x68': Correcting 'dev' to 'dec' ensures that the month abbreviation adheres to standard naming conventions, making it easier to interpret the data.
●	Column 'x34': Rectifying 'mercades' to 'mercedes' is crucial for brand analysis. Misspelled brand names can distort brand-specific insights and visualizations.


Step 10: Saving the Cleaned Data
Once the data cleaning process is complete, it is essential to save the cleaned dataset to a new file. This ensures that the cleaned data is preserved and can be used for subsequent analysis without the need to repeat the cleaning process.



Conclusion
In conclusion, the data cleaning process is a critical step in data preparation that involves several essential tasks. These tasks include addressing missing values, handling duplicates, standardizing data formats, correcting errors, and preserving the cleaned data for future analysis. Each step in the data cleaning process has been carefully explained, justified, and executed in this report to ensure the dataset's accuracy, reliability, and readiness for further analysis. The resulting cleaned dataset, saved as "cleaned_assignment_3_data.csv," is now suitable for various analytical and modeling tasks. Data cleaning is an iterative process, and its success is pivotal in obtaining trustworthy insights and making informed decisions based on data-driven evidence.

