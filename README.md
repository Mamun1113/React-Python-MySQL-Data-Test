# Stock Market Data Application

## Overview

This project is a web application built with React, which displays stock market data from JSON file and also a MySQL database. It features CRUD (Create, Read, Update, Delete) functionality, a search bar for filtering data, and a multi-axis chart for visualizing stock prices and volumes.

## Model Variation

- **JSON Model**: Retrieves data from JSON file and shows in the web application.
- **SQL Model**: Retrieves data from MySQL using phpMyAdmin and shows in the web application.

## Features

- **CRUD Operations**: Add, edit, and delete stock market data entries.
- **Search Functionality**: Filter stock market data by any column value.
- **Data Visualization**: Line and bar charts for visualizing 'close' prices and 'volume'.
- **Responsive Design**: User-friendly interface with form inputs, table, and charts.
- **Dynamic Row Count**: Displays the total number of filtered rows.

## Installation [JSON Model] : React + Python

1. Clone the repository:

   ```bash
   git clone https://github.com/Mamun1113/React-Python-MySQL-Data-Test.git
   cd React-Python-MySQL-Data-Test
   ```

2. Install dependencies for the server:

   ```bash
   cd jsonModel/server
   npm install
   ```

3. Install dependencies for the client:
   ```bash
   cd jsonModel/client
   npm install
   ```

## Installation [SQL Model] : React + MySql

1. Clone the repository:

   ```bash
   git clone https://github.com/Mamun1113/React-Python-MySQL-Data-Test.git
   cd React-Python-MySQL-Data-Test
   ```

2. Install dependencies for the server:

   ```bash
   cd sqlModel/server
   npm install
   ```

3. Install dependencies for the client:

   ```bash
   cd sqlModel/client
   npm install
   ```

4. Set up the MySQL database:

   - Create a database named `react`.
   - Create a table `stock_market_data` with the following columns:
     ```sql
     CREATE TABLE stock_market_data (
       id BIGINT PRIMARY KEY,
       date DATE NOT NULL,
       trade_code VARCHAR(255) NOT NULL,
       high DECIMAL(10, 2),
       low DECIMAL(10, 2),
       open DECIMAL(10, 2),
       close DECIMAL(10, 2),
       volume BIGINT
     );
     ```

5. Populate the database with data from JSON or CSV files using a script or a tool like phpMyAdmin.
   Data files is located in: `sqlModel/datafiles/`

6. Configure your MySQL connection in `sqlModel/server/server.js`:
   ```javascript
   const db = mysql.createConnection({
     host: "localhost",
     user: "root",
     password: "",
     database: "react",
   });
   ```

## Running the Application [JSON Model]

1. Start the server:

   ```bash
   cd jsonModel/server
   python main.py
   ```

2. Start the client:

   ```bash
   cd jsonModel/client
   npm run dev
   ```

3. Open your browser and navigate to `http://localhost:5173`.
   (You will find the URL in terminal)

## Running the Application [SQL Model]

1. Start the server:

   ```bash
   cd sqlModel/server
   npm start
   ```

2. Start the client:

   ```bash
   cd sqlModel/client
   npm run dev
   ```

3. Open your browser and navigate to `http://localhost:5173`.
   (You will find the URL in terminal)

## Usage

### Adding Data

- Fill in the form fields (date, trade code, high, low, open, close, volume) and click the "Add" button to insert new stock market data.
- The date field allows selecting a date from a calendar.
- The trade code must consist of alphanumeric characters only.

### Editing Data

- Click the "Edit" button next to a row in the table to load its data into the form.
- Modify the data as needed and click "Update" to save changes.

### Deleting Data

- Click the "Delete" button next to a row in the table to remove it from the database.

### Searching Data

- Use the search bar above the table to filter the data by any column value. The table and row count will update dynamically based on the search term.

### Data Visualization

- The multi-axis chart at the top-right shows the 'close' prices on a line chart and 'volume' on a bar chart.
- Use the dropdown above the chart to filter the data by trade code.

## Project Structure

## Dependencies

### Server

- Express.js
- MySQL
- CORS
- Body-parser

### Client

- React
- Axios
- Chart.js
- React-chartjs-2
- React-datepicker
