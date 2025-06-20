# Historical Weather Data Project

I created a Python program to collect historical weather information from Open Meteo API for a specific location and date from the last five years. 
The data retrieved include mean temperature, max wind speed, and total precipitation for a chosen location and date in each of the five years. 
These data are then aggregated and stored in a local database named `my_database.db`. 
The program also includes functions for adding, querying or deleting records of weather data in this database.

## Project files

- `W_class.py`: contains a class named "W" with several methods for retrieving and aggregating weather data.
- `main.py`: creates and populates the __Weather_Data__ table in a local SQLite database named `my_database.db`. It also contains functions to add, query and delete records.
- `test.py`: is designed to test the functionality of the "W" class using Python's unittest framework.
- `my_database.db`: the local SQLite database created through `main.py`.
- `requirements.txt`: contains all the required packages to run .py scripts.

## Installation

Install the required packages listed in `requirements.txt`

## Usage 

Call the functions in `main.py` to interact with the Weather_Data table stored in `my_database.db`.

### Commands

Use the following code in a Python shell to import main.py and its functions:  

```
from main import add_record, display_last_record, display_all_records, delete_all
```

Call the following funtions to interact with the weather data logging system:
1. The __add_record__ function retrieves weather data for a specified location and date (see Inputs section), aggregates it, and saves it to the database.
2. The __display_last_record__ function displays the most recetly added record
3. The __display_all_records__ function displays all the records in the Weather_Data table
4. The __delete_all__ function delete all records in the Weather_Data table

### Inputs

To add a record using __add_record__ function, specify inputs for the following parameters:
- Latitude: Latitude of the location (e.g., 30).
- Longitude: Longitude of the location (e.g., 80.5).
- Month: Month for which data is fetched (e.g., 10 for October).
- Day: Day of the month (e.g., 5).
- Year: Year for which data is fetched (e.g., 2024).

Examples of how to call the __add_record__ function:

- Example 1:  
latitude = 30  
longitude = 80.5  
month = 10  
day = 5  
year = 2024  
add_record(latitude, longitude, month, day, year)

- Example 2:  
add_record(30,80.5,10,5,2024)

### Outputs

When the __add_record__ funtion is called, weather data is retrieved and saved to `my_database.db`. The program returns "New record is added." message.  
If the added record already exists, the program will return "Record already exists." message.

When the __display_last_record__ or __display_all_records__ functions are called, the program outputs records in the Weather_Data table with the following information:

- Record ID
- Latitude
- Longitude
- Month
- Day
- Year
- Aggregated statistics including:
  - Average temperature
  - Minimum temperature
  - Maximum temperature
  - Average wind speed
  - Minimum wind speed
  - Maximum wind speed
  - Total precipitation
  - Minimum precipitation
  - Maximum precipitation 

If there is no record in the table, the program returns the message: "Weather_Data table has no record!"

When the __delete_all__ functions are called, the program deletes all records in the table and returns the message: "All records have been deleted"
