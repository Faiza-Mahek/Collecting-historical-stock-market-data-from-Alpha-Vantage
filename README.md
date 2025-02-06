# Collecting Historical Stock Market Data from Alpha Vantage

**Assigned On:** 26 Jan 2025 at 09:31:31  
**Due Date:** 02 Feb 2025  
**Status:** Pending

---

## Table of Contents
1. [Project Overview](#project-overview)  
2. [Prerequisites](#prerequisites)  
3. [Dataset Details](#dataset-details)  
4. [Implementation Steps](#implementation-steps)
5. [Presentation](#presentation)  
6. [Usage](#usage)  
7. [References](#references)

---

## Project Overview

This task involves retrieving and preprocessing historical stock market data for **NSE** (National Stock Exchange) and **BSE** (Bombay Stock Exchange) using the [Alpha Vantage API](https://www.alphavantage.co/documentation/). The processed data will serve as input for subsequent stock market prediction tasks.

**Key Deliverables**:
1. A **Python script** (not shown here) that retrieves the data using Alpha Vantage  
2. **Preprocessed DataFrames** (in CSV format) for both NSE and BSE

---

## Prerequisites

1. **Alpha Vantage API Key**  
   - Obtain a free API key by signing up at the official [Alpha Vantage site](https://www.alphavantage.co/support/#api-key).
   - This key is required to access the stock market data endpoints.

2. **Python Environment**  
   - Ensure Python 3.x is installed on your system.
   - Recommended libraries include **pandas** (for data manipulation) and **requests** (for making HTTP requests).
   - Additional libraries such as **NumPy** or **datetime** may be useful but are optional based on project needs.

3. **Internet Connectivity**  
   - An active internet connection is needed to call the Alpha Vantage API.

---

## Dataset Details

**Data Source**: Alpha Vantage’s “TIME_SERIES_DAILY_ADJUSTED” endpoints for NSE and BSE.  

- **NSE Endpoint**:  
  - A standard URL that includes the query parameter `symbol=NSE` along with your API key.
- **BSE Endpoint**:  
  - Similarly, a URL that includes the query parameter `symbol=BSE` plus your API key.

The JSON responses typically include daily Open, High, Low, Close, Adjusted Close, and Volume for each trading date.

---

## Implementation Steps

1. **Obtain the API Key**  
   - Sign up at Alpha Vantage to generate your personal API key.
   - Keep the key secure; it will be appended to the endpoint when you make requests.

2. **Formulate the API Endpoints**  
   - Construct the request URLs for NSE and BSE by combining the base endpoint with the query parameters (function, symbol, and your API key).
   - Ensure the `symbol` parameter is set to “NSE” or “BSE” respectively.

3. **Retrieve the Data**  
   - Use an HTTP library (e.g., requests in Python) to send GET requests to the prepared URLs.
   - Confirm a successful response by checking the status code or relevant indicators.

4. **Load Data into DataFrames**  
   - Convert the JSON responses into a tabular format.
   - Create pandas DataFrames for NSE and BSE, each structured with date indices and columns for open, high, low, close, adjusted close, and volume.

5. **Clean and Preprocess**  
   - Convert text-based dates into a proper date or datetime type.
   - Convert numeric fields (e.g., prices, volume) into numerical data types.
   - Handle any missing or inconsistent values by filling or dropping them. Use domain knowledge to decide the best approach (e.g., forward-fill for missing prices).

6. **Export to CSV**  
   - After ensuring each DataFrame is consistent and contains no critical gaps, save them as CSV files (e.g., `nse_preprocessed.csv` and `bse_preprocessed.csv`).
   - These CSVs will be inputs for modeling in future tasks.

---

## Presentation

### PPT Link
> **[Click Here to View the Presentation Slides](https://www.canva.com/design/DAGd9-FKQ_Y/YQFtk22df_-M9kygbuwujQ/edit)**

---

## Usage

1. **Script Execution**  
   - Run the Python script designed for this task (not included here) after configuring it with your valid Alpha Vantage API key.
   - The script should download and preprocess NSE/BSE data, then output CSV files.

2. **Integration in Other Projects**  
   - Import or load the CSV files into notebooks, scripts, or applications that require historical NSE/BSE data.
   - Further transformations or merges with external datasets may be performed as needed.

3. **Custom Date Range or Frequency**  
   - If desired, update the function or parameters in your API queries to retrieve different frequencies (e.g., weekly or monthly) or to request a specific date range.

---

## References
 
- **Alpha Vantage Documentation:** [https://www.alphavantage.co/documentation/](https://www.alphavantage.co/documentation/)  
- **Alpha Vantage - API Key Signup:** [https://www.alphavantage.co/support/#api-key](https://www.alphavantage.co/support/#api-key)  
- **Official Pandas Documentation:** [https://pandas.pydata.org/](https://pandas.pydata.org/)  
