# Server Log Data Extraction and User History Database Update

## Project Overview

This data engineering project focuses on extracting email addresses and timestamps from server log files, processing the data through a comprehensive pipeline, and storing it in both MongoDB and SQLite databases for analysis.

## Technologies Used

- **Python 3.12.3** - Primary programming language
- **MongoDB** - NoSQL database for initial data storage
- **SQLite** - Relational database for analysis
- **Regex** - Pattern matching for data extraction
- **Pandas** - Data manipulation and analysis
- **PyMongo** - MongoDB Python driver
- **gdown** - Google Drive file download utility

## Project Structure

```
Server Log Data Extraction and User History Database Update_ASS_3/
├── DE3.ipynb                   # Main Jupyter notebook with complete pipeline
├── mbox.txt                    # Input dataset (email server logs)
├── user_history.db             # SQLite database file
├── README.md                   # Project documentation
└── requirements.txt            # Python dependencies
```

## Problem Statement

The project addresses the challenge of processing server log files containing email data and transforming them into a structured format suitable for database storage and analysis. The goal is to:

1. Extract email addresses and corresponding timestamps from log files
2. Transform and clean the data for database storage
3. Implement a dual-database architecture (MongoDB + SQLite)
4. Perform comprehensive data analysis using SQL queries
5. Generate business insights from email activity patterns

## Data Pipeline

```
mbox.txt → Data Extraction → MongoDB → SQLite → Analysis & Insights
```

### Pipeline Steps:

1. **Data Extraction**: Parse email addresses and dates using regex patterns
2. **Data Transformation**: Standardize date formats and structure data
3. **MongoDB Storage**: Store processed data in NoSQL database
4. **SQLite Migration**: Transfer data to relational database
5. **Analysis**: Execute SQL queries for business insights

## Installation and Setup

### Prerequisites

- Python 3.12 or higher
- MongoDB server running locally
- Jupyter Notebook or JupyterLab

### Installation Steps

1. **Clone the repository:**
   ```bash
   git clone <repository-url>
   ```

2. **Install required packages:**
   ```bash
   pip install -r requirements.txt
   ```

3. **Run the Jupyter notebook:**
   ```bash
   jupyter notebook DE3.ipynb
   ```

## Database Configuration

- **MongoDB Configuration**: Connection string, database name, collection name
- **SQLite Configuration**: Database file path and table schema
- **SQL Queries**: Predefined queries for analysis

## Project Tasks

### Task 1: Extract Email Addresses and Dates
- Read the log file and extract all occurrences of email addresses
- Capture the date associated with each email address
- Use regex patterns for reliable data extraction

### Task 2: Data Transformation
- Ensure extracted data is structured for database insertion
- Format dates into standard format (YYYY-MM-DD HH:MM:SS)
- Validate data quality and handle parsing errors

### Task 3: Save Data to MongoDB
- Save processed data into MongoDB collection named 'user_history'
- Implement proper error handling and duplicate prevention
- Verify data integrity after insertion

### Task 4: Database Connection and Data Upload
- Fetch data from MongoDB collection
- Insert data into SQLite database with proper constraints
- Implement primary key constraints and data validation

### Task 5: Run Queries on the Database
Execute comprehensive SQL analysis including:
- List all unique email addresses
- Count emails received per day
- Find first and last email dates for each address
- Count emails from each domain
- 10 additional custom analysis queries

## Analysis Results

### Key Metrics
- **Total Records**: 1,797 email-date pairs
- **Unique Emails**: 42 distinct email addresses
- **Date Range**: October 2007 to January 2008
- **Unique Domains**: 21 different email domains

### Top Insights
1. **Most Active Domain**: iupui.edu (535 emails)
2. **Busiest Day**: 2007-10-29 (84 emails)
3. **Most Active User**: zqian@umich.edu (195 emails)
4. **Activity Pattern**: Weekdays (1,668) vs Weekends (127)
5. **Peak Hour**: 10 AM (198 emails)

## Custom SQL Analysis

The project includes 10 custom SQL queries providing insights into:

1. **User Activity**: Top 5 most active email addresses
2. **Temporal Patterns**: Busiest days and hours
3. **Domain Analysis**: Email distribution across domains
4. **Engagement Metrics**: Single vs. multiple email users
5. **Time-based Analysis**: Weekend vs. weekday patterns

## File Descriptions

### Core Files
- **DE3.ipynb**: Complete data pipeline with documentation
- **mbox.txt**: Input dataset (email server logs)

### Generated Files
- **user_history.db**: SQLite database with processed data
- **README.md**: Project documentation

## Usage

1. **Run the complete pipeline:**
   ```python
   # Execute all cells in DE3.ipynb
   # This will download data, process it, and run analysis
   ```

2. **Access the database:**
   ```python
   import sqlite3
   conn = sqlite3.connect('user_history.db')
   cursor = conn.cursor()
   cursor.execute("SELECT * FROM user_history LIMIT 5")
   ```

## Technical Features

### Data Quality
- Regex-based email extraction with validation
- Date parsing with error handling
- Duplicate prevention using primary keys
- Data type validation and standardization

### Database Design
- **MongoDB**: Flexible schema for initial data storage
- **SQLite**: Structured schema with constraints
- **Primary Key**: Composite key (email, date) for uniqueness
- **Indexing**: Optimized for query performance

### Error Handling
- Graceful handling of malformed dates
- Database connection error recovery
- Data validation and integrity checks
- Comprehensive logging and reporting

## Performance Considerations

- **Data Processing**: Efficient regex patterns for extraction
- **Database Operations**: Batch inserts for better performance
- **Memory Management**: Streaming large file processing
- **Query Optimization**: Indexed queries for fast analysis

## Future Enhancements

1. **Real-time Processing**: Implement streaming data processing
2. **Additional Analytics**: Machine learning insights
3. **Web Interface**: Dashboard for data visualization
4. **API Development**: RESTful API for data access
5. **Cloud Deployment**: AWS/Azure integration

## Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Add tests if applicable
5. Submit a pull request

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Contact

For questions or support, please open an issue in the repository.

---


**Note**: This project demonstrates a complete data engineering pipeline from raw log files to actionable business insights, showcasing best practices in data processing, database design, and analytical querying. 
