# YouTube Channel Analysis

## Short Description

This Python script analyzes YouTube channel data from a dataset, calculates the distribution of channel types from the top 1000 records, and loads the data into a MySQL database.

## Getting Started

### Prerequisites

Ensure you have the following installed:

- Anaconda
- Jupiter Notebook    
- MYSQL Workbench

## Installing

Run the jupiter notebook and and include follwing library. these library will allow the user to use the functions in the jupiter notebook.
```bash
import pandas as pd
import pandas as pd
from sqlalchemy import create_engine
import pymysql
```

now to connect the python with the database int the mysql use the following command. 
The command pip install pymysql installs the pymysql Python package, enabling communication with MySQL databases through Python scripts.
```bash
pip install pymysql
```


The create_engine command establishes a connection to a MySQL database named "assignment4" hosted on the local machine, using the username "usert" and password "password."

```bash
# create engine
engine = create_engine('mysql+pymysql://usert:password@localhost/assignment4')
```

The conn = engine.connect() command establishes a connection (conn) to a database using the SQLAlchemy engine (engine).

```bash
# create engine
conn = engine.connect()
```
Now we are all set to do the youtube channel analysis  
you can downlaod the dataset from here https://github.com/rehalarjun/DATA1202/blob/main/youtube_dataset.csv

## Running the analysis
- to run the analyisi first downlaod the assignemt4.ipynb file in your local machine and then start the jupiter notebook.  ![image](https://github.com/rehalarjun/DATA1202/assets/113398985/f8733b6c-fa09-4886-837f-a38bb6c5361c)

- now go the the file section of the jupiter notebook and locate the assignemt4.ipynb and then click on it
![image](https://github.com/rehalarjun/DATA1202/assets/113398985/82b8c945-0c50-4e73-b1fc-fa3aba195c29)

- when you click on it you will have this kind of interface
![image](https://github.com/rehalarjun/DATA1202/assets/113398985/068eabf0-547b-45cd-a246-2aabdc9decdd)

- now srat running the command by just selecting the cell and hitting on the run button on the above rebin.
- make sure to change the path of the file  to where you have downlaoded the dataeset
  ![image](https://github.com/rehalarjun/DATA1202/assets/113398985/40f12a53-9739-40b4-bc5b-983a003ac1fa)

- lastly change the credential according to what the user have set on ones mysql workbench to connect to it
  ![image](https://github.com/rehalarjun/DATA1202/assets/113398985/e5e1ba97-57b2-4398-8b6b-d487e265512f)

  ### Breakdown of Tests

1. **Calculate Channel Distribution:**
   - Description: Calculates the distribution of channel types from the loaded dataset.
   - Command: 
     ```python
     channel_distribution_result = calculate_channel_distribution(data)
     print(channel_distribution_result)
     ```

2. **Load Top 1000 Data:**
   - Description: Loads the top 1000 records from the sorted dataset into a CSV file.
   - Command: 
     ```python
     top_1000_data = load_data_top_1000(data)
     ```

3. **Read and Verify Loaded Data:**
   - Description: Reads the CSV file containing the top 1000 records and displays the loaded DataFrame.
   - Command: 
     ```python
     data2 = pd.read_csv('top_1000_channels.csv')
     data2.head()
     ```

4. **Database Connection and Query:**
   - Description: Creates a connection to a MySQL database using SQLAlchemy and reads a simple query into a DataFrame.
   - Command: 
     ```python
     df = pd.read_sql("SELECT * FROM assignment4.youtube_dataset", conn)
     print(df.head())
     ```

5. **Write Data to MySQL Table:**
   - Description: Writes the loaded DataFrame to a MySQL table.
   - Command: 
     ```python
     data2.to_sql(table_name, con=engine, if_exists='replace', index=False)
     ```

Note: Ensure that the MySQL server is running and the database and table names match your actual setup.

Feel free to modify the descriptions and commands as needed for your specific project.


##  Deployment 
To deploy this script, make sure you have a MySQL database set up and modify the connection details in the script. Then, run the script to load the data into the database.

## Author
Arjun Rehal

## Lisence
This project is licensed under the MIT License - see the LICENSE.md file for details.




