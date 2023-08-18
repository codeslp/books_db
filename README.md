# GoodReads Best Books Analysis Project

## Introduction

This repository contains the code and artifacts for analyzing the Kaggle GoodReads Best Books dataset. The goal is to load the data into an RDBMS, normalize it, perform exploratory data analysis, and train a model to generate fictional books.

## Requirements

- An RDBMS such as PostgreSQL (which was used here)
- Python 3.x
- Jupyter Notebook
- Packages & modules are in artifacts/requirements.txt

## Directory Structure

- **\`src\`**: Contains the IPython Notebook files with all the analysis code.
- **\`data\`**: Houses the original GoodReads Best Books dataset files.
- **\`artifacts\`**: Includes the Entity Relationship Diagram (ERD) representing the normalized data schema made with drawio and requirements.txt file.
- **\`doc\`**: Notebook used to record cleaning and normalization tasks.

## Getting Started

1. **Download Data**: Ensure that the GoodReads Best Books data is downloaded and placed in the \`data\` folder.
2. **Set Up Virtual Environment**: Navigate to the project folder and activate the virtual environment:

   ```bash
   . venv/bin/activate
   ```

3. **Launch Jupyter Notebook**: Start the Jupyter Notebook:

   ```bash
   jupyter notebook src/your_notebook_name.ipynb
   ```

## Process Overview

The project performs the following tasks:

1. **Data Loading**: The GoodReads Best Books dataset is loaded from the `data` folder.

2. **Data Cleaning**: The following cleaning steps are performed using Pandas DataFrames:
    - Handling missing values.
    - Transformation of specific columns.
    - Type conversion and validation.
    - Ensuring correct data types for each attribute.

3. **Data Normalization**: The cleaned data is then normalized according to the rules of First Normal Form (1NF), Second Normal Form (2NF), achieving a normalized schema that's efficient for analysis.

4. **Database Population**: After normalization, the data is loaded into a PostgreSQL database. This involves the creation of the necessary tables, and insertion of the data into the tables.

5. **Data Analysis**: Utilizing both SQL and Pandas, exploratory data analysis is conducted to derive insights and train a model for generating fictional books.

## Setup

1. Clone this repository to your local machine.

    ```bash
    git clone https://github.com/yourusername/books_db.git
    ```

2. Navigate to the project directory.

    ```bash
    cd books_db
    ```

3. Install the required Python packages. It is recommended to use a virtual environment for this.

    ```bash
    python3 -m venv venv
    . venv/bin/activate  # On Windows, use 'venv\Scripts\activate'
    pip install -r artifacts/requirements.txt
    ```


4. **Set up PostgreSQL**: You need a running PostgreSQL instance to which the script can connect. Here's a detailed explanation of this step:

    - **Install PostgreSQL**: If not already installed, you need to install PostgreSQL on your machine. The installation steps can vary by operating system. You can refer to the official PostgreSQL documentation for detailed instructions.

    - **Create a database**: After installation, create a new PostgreSQL database that will be used to store the normalized GoodReads data. You can do this through the `psql` command line interface, or using a graphical interface like pgAdmin.

    - **Update the database connection string**: Open the books_db notebook in an editor. Look for the line where the database connection string is defined. It should look something like this:

        ```python
        engine = create_engine(f"postgresql+psycopg2://{DB_USER}:{DB_PASSWORD}@localhost/{DB_NAME}")
        ```

        If your PostgreSQL server is not running on the local machine, or if it's running on a non-default port, you need to update this connection string accordingly.


5. **Create a .env file** with your database credentials:

    ```bash
    DB_USER=your_db_username
    DB_PASSWORD=your_db_password
    DB_NAME=your_database_name
    ```

6. **Update the database connection string** in the appropriate notebook within the `src` folder.

7. **Running the Jupyter Notebook**:

   Work for this project is done in the `src` folder. Open the .ipynb files and run them as needed.