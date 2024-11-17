# LLM-Driven Data Processor

## Overview

This project implements a **Large Language Model (LLM)-driven Data Processor**, which combines the power of advanced natural language processing (NLP) and data processing pipelines. It aims to provide a user-friendly interface for querying and processing data, allowing non-technical users to extract meaningful insights without requiring expertise in SQL or data analytics.

---

## Objectives

1. **Simplify Data Interaction**: Enable users to query and interact with data using natural language.
2. **Automate Data Processing**: Streamline complex data processing workflows into a seamless, efficient pipeline.
3. **Enhance Decision-Making**: Provide actionable insights in real time, aiding decision-making across various domains.
4. **Schema-Agnostic Functionality**: Allow the processor to adapt dynamically to different database schemas.
5. **Visualization Support**: Present the processed data in an intuitive format, including visual representations like charts and graphs.

---

## Features

1. **Natural Language Querying**: Users can input queries in plain English, and the LLM converts them into SQL queries.
2. **Dynamic Schema Handling**: The system interprets and maps queries to the underlying database schema.
3. **Data Transformation and Analysis**: Supports advanced data processing, including aggregation, filtering, and predictive analytics.
4. **Extensibility**: Modular design allows for easy addition of new functionalities, such as integrating external APIs or adding new types of data visualizations.

---

## What We Have Done

### 1. **Developed a Query Processing Pipeline**
- **Input**: Natural language query.
- **Output**: SQL query mapped to the schema of the database.
- **Tools Used**: LLMs (e.g., OpenAI GPT-based models), LangChain for prompt engineering.

### 2. **Created an Interactive UI**
- Developed a simple web interface for user interaction.
- Users can input natural language queries and view results as tables or visualizations.

### 3. **Built a Schema-Aware Backend**
- Designed a flexible backend that parses and understands the database schema dynamically.
- Used this capability to translate natural language inputs into schema-specific SQL queries.

### 4. **Implemented Data Visualization**
- Integrated libraries like Matplotlib, Seaborn, or Plotly for creating dynamic visual representations.
- Supported charts: bar, line, pie, scatter plots, and more.

### 5. **Tested with Multiple Scenarios**
- Verified the pipeline across diverse datasets and queries to ensure robustness.

---

## Database Schema Overview

The database schema is designed to handle data related to a fictional **retail system**. The schema includes the following tables:

### Tables

1. **Customers**
   - **Columns**:
     - `CustomerID` (Primary Key): Unique identifier for each customer.
     - `Name`: Full name of the customer.
     - `Email`: Email address.
     - `Phone`: Phone number.
     - `SignupDate`: Date when the customer registered.

2. **Products**
   - **Columns**:
     - `ProductID` (Primary Key): Unique identifier for each product.
     - `Name`: Name of the product.
     - `Category`: Product category (e.g., electronics, apparel).
     - `Price`: Price of the product.
     - `StockQuantity`: Number of units in stock.

3. **Orders**
   - **Columns**:
     - `OrderID` (Primary Key): Unique identifier for each order.
     - `CustomerID` (Foreign Key): ID of the customer placing the order.
     - `OrderDate`: Date when the order was placed.
     - `TotalAmount`: Total amount of the order.

4. **OrderDetails**
   - **Columns**:
     - `OrderDetailID` (Primary Key): Unique identifier for each line item in an order.
     - `OrderID` (Foreign Key): ID of the order.
     - `ProductID` (Foreign Key): ID of the product.
     - `Quantity`: Number of units ordered.
     - `LineTotal`: Total price for the line item (calculated as `Quantity * Price`).

5. **Categories**
   - **Columns**:
     - `CategoryID` (Primary Key): Unique identifier for each category.
     - `CategoryName`: Name of the category.
     - `Description`: Description of the category.

### Relationships
- `Customers` → `Orders` (One-to-Many): A customer can place multiple orders.
- `Orders` → `OrderDetails` (One-to-Many): Each order contains multiple line items.
- `Products` → `OrderDetails` (One-to-Many): A product can appear in multiple order details.
- `Products` → `Categories` (Many-to-One): Each product belongs to one category.

---

## How to Run the Project

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/your-repo/llm-data-processor.git
   cd llm-data-processor
   ```

2. **Install Dependencies**:
   ```bash
   pip install -r requirements.txt
   ```

3. **Run the Application**:
   ```bash
   python app.py
   ```

4. **Access the Web Interface**:
   - Open a web browser and navigate to `http://localhost:5000`.

---

## Future Enhancements

1. Add support for real-time streaming data.
2. Expand visualization options with advanced analytics.
3. Enhance schema parsing for highly normalized databases.
4. Integrate additional AI models for predictive and prescriptive analytics.

---

This project is a step towards making data analytics more accessible, efficient, and insightful for users of all skill levels. Feedback and contributions are welcome!
