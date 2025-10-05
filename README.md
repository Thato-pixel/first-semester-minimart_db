

MiniMart Data Analysis and Reporting System 📊
This project is a complete Python application designed to connect to a PostgreSQL database, execute complex sales analysis and reporting queries, and simulate new orders while applying essential business logic and data type handling.

Project Structure
The project is organized to separate database utilities, business logic, and the main execution script:

month2_minimart_analysis/
├── python/
│   ├── main.py                   # Main entry point and execution workflow
│   ├── report_generator.py       # SQL query execution and report generation logic
│   ├── utils.py                  # Custom business logic (discounts, currency conversion)
│   └── .env.example              # Template for database connection details
└── sql/
    └── create_tables.sql         # Database schema setup (tables: orders, products, customer)
Setup and Installation
Follow these steps to set up the project locally and ensure all dependencies are met.

1. Prerequisites
You must have the following installed:

Python 3.x

PostgreSQL Database instance running.

2. Database Configuration
Create Tables: Ensure your PostgreSQL database has the necessary tables (orders, products, customer) using the schema defined in your sql/create_tables.sql file.

Environment File: Create a file named .env in the python/ directory (next to main.py). Use the following template and replace the bracketed values with your actual PostgreSQL credentials:

Code snippet

# .env file content
DB_NAME=[Your_Database_Name]
DB_USER=[Your_Database_User]
DB_PASSWORD=[Your_Database_Password]
DB_HOST=localhost
DB_PORT=5432
3. Python Dependencies
Install the required Python libraries using the requirements.txt file (if you have one) or manually:

Bash

pip install python-dotenv psycopg2-binary
Running the Application
The script must be executed as a Python module from the project's root directory to ensure all internal imports are resolved correctly.

Navigate to the project root:

Bash

cd first-semester-projects
Execute the main module:

Bash

python -m month2_minimart_analysis.python.main
Expected Output
The script will first connect to the database, run the analysis to generate the Retail Data Summary Report, then insert and summarize the Simulated Orders, and finally close the connection.

Key Features & Logic
Robust Reporting: Generates a report showing Total Products Sold, Most Popular Product, and Revenue Per Customer by joining orders, products, and customer tables.

Conditional Logic: The simulate_orders function demonstrates conditional logic by applying discounts, calculating totals, and flagging orders based on a "Large Order" threshold (e.g., R1000).

Data Integrity: Includes robust data handling to prevent common errors, such as explicitly converting PostgreSQL's high-precision decimal.Decimal types to Python float before currency conversion.

Idempotency: The insert_simulated_orders function prevents duplicate entries by checking if an identical order already exists before insertion.









