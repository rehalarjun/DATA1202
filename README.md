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
