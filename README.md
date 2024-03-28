# Project: Data Extraction from CoinMarketCap API and Persistence in AWS RDS

This project aims to extract data from the CoinMarketCap API and persist it in an AWS RDS database. Here is a detailed description of each step of the project:

## Step 1: Environment Setup

To begin, it's necessary to set up the Python environment and ensure all dependencies are correctly installed. Make sure you have access to the AWS RDS and have your CoinMarketCap API key ready for use.

## Step 2: Database Modeling

Before extracting and persisting data, it's important to define the database structure. In the `model.py` file, you will find the definition of the data model, including the necessary tables and columns. Review this file and make any necessary adjustments according to your specific requirements.

### Coins Database Table

The `Coins` table contains information about various cryptocurrencies.

- `id`: Primary key for the table.
- `name`: Name of the cryptocurrency.
- `symbol`: Symbol of the cryptocurrency.
- `data_added`: Date when the cryptocurrency was added.
- `last_updated`: Date when the information was last updated.
- `price`: Price of the cryptocurrency.
- `volume_24h`: 24-hour trading volume of the cryptocurrency.

## Step 3: Data Extraction from API

The `app.py` script is responsible for extracting data from the CoinMarketCap API. It makes a GET request to the API, passing the necessary parameters such as the starting point, limit, and conversion currency. It then processes the received data and converts it into a pandas DataFrame.

## Step 4: Data Validation

After data extraction, it's important to validate whether the data is correct and complete. The script checks if the DataFrame is empty and if all essential columns are filled. Otherwise, it terminates script execution and displays an error message.

## Step 5: Data Persistence in the Database

Once validated, the data is loaded into the RDS database. The script uses SQLAlchemy to create a database session and persist the data in the table defined in Step 2. After successful loading, the session is closed, and the database is closed.

## Script Execution

To execute the script and perform data extraction and persistence, follow these steps:

1. Open a Python session.

2. Run the `app.py` script.

3. Monitor the script's progress as it extracts data from the API, validates it, and loads it into the database.

## Notes

- Ensure all access settings and credentials are correct before running the script.
- Review and adjust the data extraction parameters as needed, such as the number of records to retrieve from the API.

