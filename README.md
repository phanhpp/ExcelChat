# Building a Structured Data Extraction and LLM-Query Pipeline from Complex Excel Files with LlamaIndex

## Introduction

This notebook is designed to extract structured shipment data from Excel files that contain multiple sheets. Each sheet represents a shipment, which consists of multiple packages, and each package contains multiple items.

Due to the hierarchical structure and complexity of the Excel format, including nested cells, simple Pandas-based extraction is insufficient. To address this, we employ a structured approach using Pydantic models (`Shipment`, `Package`, `Item`) to represent the data in a hierarchical manner.

## Pipeline Process

1. **Reading the Excel file** using Pandas and converting its contents into LlamaIndex's Document format.
2. **Extracting structured data** by leveraging an LLM to parse the documents and populate the Pydantic models.
3. **Storing the structured data** in a SQL database since the extracted data is too large for direct querying with an LLM.
4. **Retrieving relevant data** using LlamaIndex's `NLSQLRetriever`, which translates natural language queries into SQL statements executed against the database.
5. **Formatting the retrieved data** into a Pandas DataFrame and exporting it back to an Excel file for further analysis or reporting.

This pipeline enables scalable and efficient structured data extraction, storage, and retrieval, making it possible to interact with complex shipment data using natural language queries.

## Key Components

- **Pydantic Models**: Hierarchical data representation
- **LlamaIndex Documents**: Structured document format
- **LLM Integration**: Intelligent parsing of complex structures
- **SQL Database**: Efficient storage and retrieval
- **NLSQLRetriever**: Natural language to SQL translation

## Benefits

- Process complex hierarchical Excel data
- Maintain relationships between entities
- Query using natural language
- Scale to handle large volumes of data
