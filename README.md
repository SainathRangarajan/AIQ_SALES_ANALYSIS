# AIQ_SALES_ANALYSIS
Sales Analysis README
Overview
This data pipeline processes sales data, fetches weather conditions, and generates visualizations for analysis. It consists of several components, including data retrieval, data transformation, weather API integration, and visualization.
Components
1.	Data Retrieval:
•	Fetches user information and sales data from REST API and CSV file, respectively.
2.	Data Transformation:
•	Converts sales data into a structured DataFrame.
•	Generates synthetic store locations based on customer coordinates.
•	Calculates line totals and aggregates sales data.
3.	Weather API Integration:
•	Retrieves weather conditions, temperature, pressure, humidity, and wind speed using the OpenWeatherMap API.
•	Utilizes concurrent processing for faster data fetching.
4.	Visualizations:
•	Generates interactive bar graphs for monthly and quarterly sales using Plotly Express.
•	Creates a bar graph for average sales by weather condition using Matplotlib.
5.	Database Storage:
•	Connect to Snowflake Database with appropriate connection string and schema details.
•	Write the Transformed/Aggregated Dataframes into Tables in the DB.
Dependencies
•	Python 3.x
•	pandas
•	numpy
•	matplotlib
•	plotly
•	requests
•	concurrent.futures
•	snowflake.connector
•	snowflake.connector.pandas_tools 
Setup Instructions
1.	Install Python and the required libraries (pandas, numpy, matplotlib, plotly, requests).
2.	Clone or download the repository containing the script and sales data CSV file.
3.	Update the API key in the script with your own OpenWeatherMap API key.
4.	Run the script data_pipeline.py to execute the data pipeline and generate visualizations.
Data Manipulation Tasks
1.	Fetch user information and sales data.
2.	Convert sales data into a structured DataFrame.
3.	Generate synthetic store locations based on customer coordinates.
4.	Calculate line totals and aggregate sales data.
5.	Retrieve weather conditions and additional weather data using the OpenWeatherMap API.
6.	Generate visualizations for monthly and quarterly sales, as well as average sales by weather condition.
Usage
•	Execute the script data_pipeline.py using Python to process the data and generate visualizations.
•	Review the generated graphs to analyze monthly sales, quarterly sales, and average sales by weather condition.
Database Schema Description
1.	Users Table
•	Columns:
•	id (Primary Key): Unique identifier for each user.
•	name: User's name.
•	username: User's username.
•	email: User's email address.
•	phone: User's phone number.
•	website: User's website URL.
•	address_street: Street address.
•	address_suite: Address suite information.
•	address_city: City.
•	address_zipcode: ZIP code.
•	address_geo_lat: Latitude coordinate.
•	address_geo_lng: Longitude coordinate.
•	company_name: Company name.
•	company_catchPhrase: Company catchphrase.
•	company_bs: Company business strategy.
2.	Sales Table
•	Columns:
•	order_id (Primary Key): Unique identifier for each order.
•	customer_id (Foreign Key to Users Table): Identifier for the customer who placed the order.
•	product_id: Identifier for the product sold.
•	quantity: Quantity of the product purchased.
•	price: Price of the product.
•	order_date: Date and time of the order.
3.	Weather Table
•	Columns:
•	id (Primary Key): Unique identifier for each weather record.
•	store_lat: Latitude coordinate of the store.
•	store_long: Longitude coordinate of the store.
•	weather_condition: Weather condition description.
•	temperature: Temperature in Celsius.
•	pressure: Atmospheric pressure in hPa.
•	humidity: Relative humidity in percentage.
•	wind_speed: Wind speed in meters per second.
•	timestamp: Timestamp of the weather data.
4.	Monthly Sales Table
•	Columns:
•	year: Year of the sales data.
•	month: Month of the sales data.
•	monthly_sales: Total sales amount for the month.
5.	Quarterly Sales Table
•	Columns:
•	year: Year of the sales data.
•	quarter: Quarter of the sales data (1, 2, 3, 4).
•	quarterly_sales: Total sales amount for the quarter.
6.	Product Statistics Table
•	Columns:
•	product_id (Primary Key): Identifier for the product.
•	avg_quantity: Average quantity sold for the product.
7.	Weather Statistics Table
•	Columns:
•	weather_condition (Primary Key): Weather condition description.
•	avg_sales: Average sales amount for the weather condition.


