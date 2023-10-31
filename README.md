# Advanced-Exercise-Data-Analyzer

This code performs the following functions:

1. **Imports and Initial Setup**:
   - Necessary modules such as `os`, `requests`, and `datetime` are imported.
   - Several environment variables are fetched using the `os` module to get specific values such as API credentials (`APP_ID`, `API_KEY`), exercise API endpoint (`excercise_endpoint`), and the Sheety API endpoint (`sheety_endpoint`).

2. **Setting API Headers**:
   - Two types of headers are set:
     - `headers` for the exercise API, which uses the `APP_ID` and `API_KEY`.
     - `bearer_headers` for the Sheety API which requires an authorization token.

3. **User Input & Parameters Configuration**:
   - The user is prompted to enter the type of exercise they performed today. This input is used to set the `query` parameter.
   - Other parameters such as gender, weight, height, and age are set using predefined values.

4. **Making an API Request**:
   - A POST request is made to the `excercise_endpoint` (an external service that likely provides exercise-related data) using the parameters and headers.
   - The server's response is parsed to JSON format and stored in the `result` variable.

5. **Processing and Sending Data to Sheety**:
   - The current date and time are fetched.
   - For each exercise returned in the `result`, relevant data is extracted and structured in the `sheet_parameters` dictionary. This includes the date, time, name of the exercise, its duration, and calories burned.
   - A POST request is made to the `sheety_endpoint` (likely a service to log or track exercises in a sheet-like format) with the `sheet_parameters` and the `bearer_headers`.

6. **Output**:
   - The response from the Sheety API is printed out to the console.

**Description**:

The code prompts the user to specify an exercise they did today. 
It then fetches data related to the mentioned exercise, like duration and calories burned, from an external API. Finally, it logs this information, along with the current date and time, 
to a Sheety service (which seems to be an online spreadsheet or database) and prints the Sheety response. The process leverages environment variables for API credentials and endpoints.
