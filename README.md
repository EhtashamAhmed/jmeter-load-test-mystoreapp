# JMeter Load Test for My Store

This repository contains a JMeter load test project designed to test the performance of the "My Store" website hosted on Azure. The test plan includes three HTTP GET requests to key pages of the site and two listeners to analyze the results.

## Project Overview

This JMeter project is set up to perform a load test on the "My Store" website. The site name is parameterized using JMeter's User Defined Variables for flexibility, allowing easy updates to the target URL if needed.

- **Site Name**: The base URL of the site is stored in a variable named `BASE_URL_1`, which is set to `mystore.azurewebsites.net`. This variable is used in all HTTP requests to construct the full URLs dynamically.

## Test Plan Structure

The test plan consists of the following key elements:

### 1. User Defined Variables
   - The variable `BASE_URL_1` is defined with the value `mystore.azurewebsites.net`. This allows the site name to be easily changed in one place without modifying each HTTP request individually.

### 2. HTTP Requests
   The test includes three HTTP GET requests to simulate user interactions with the following pages:
   - **Home Page**: `https://mystore.azurewebsites.net/`
     - A GET request to the root path (`/`) of the website.
   - **Privacy Page**: `https://mystore.azurewebsites.net/PRIVACY`
     - A GET request to the `/PRIVACY` path.
   - **Clients Page**: `https://mystore.azurewebsites.net/CLIENTS`
     - A GET request to the `/CLIENTS` path.

   Each request uses the `BASE_URL_1` variable for the server name, ensuring consistency and ease of maintenance.

### 3. Listeners
   Two listeners are included to capture and display the test results:
   - **View Results Tree**: Displays the response of each HTTP request, including the response code, response body, and headers. This is useful for debugging and verifying that the requests are functioning as expected.
   - **Summary Report**: Provides a summary of the overall test execution, including key metrics such as total execution time, average response time, throughput, and error rate. It is essential for assessing the performance of the website under load.

## How to Run the Test
   - Open JMeter and load the `My_Store.jmx` file.
   - Review the test plan to ensure it meets your requirements (e.g., adjust the number of threads in the Thread Group if needed).
   - Click the "Run" button (green play icon) in the JMeter toolbar to start the test.
   - Monitor the test execution using the View Results Tree and Summary Report listeners.

### Analyzing Results
   - Use the **View Results Tree** to check individual request responses and ensure they return the expected status codes (e.g., 200 OK).
   - Use the **Summary Report** to evaluate overall performance metrics, such as response times and error rates.

## Additional Notes
- The test is configured with default settings in the Thread Group (e.g., number of threads, ramp-up period). You can modify these settings to simulate different load scenarios.
- For more advanced configurations or to learn more about JMeter, refer to the [official JMeter documentation](https://jmeter.apache.org/usermanual/index.html).