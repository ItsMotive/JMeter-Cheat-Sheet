# Parameterization with CSV Data Set Config

- This chapter explains how to set up CSV Data Set Config in JMeter to provide dynamic input data for your tests. 

- You’ll learn how to use variables from CSV files to simulate multiple users or different requests during test execution.

## Table of Contents

- [Section 1: Introduction to Parameterization](#section-1-introduction-to-parameterization)

- [Section 2: Setting up CSV Data Set Config for Dynamic Input Data](#section-2-setting-up-csv-data-set-config-for-dynamic-input-data)

- [Section 3: Using Variables to Simulate Multiple Users or Requests](#section-3-using-variables-to-simulate-multiple-users-or-requests)

- [Summary](#summary)

## Section 1: Introduction to Parameterization

- **Parameterization**

    - The process of using dynamic data in your test instead of hardcoded values.
    
    - This allows you to simulate multiple users with different credentials or requests without manually creating separate tests for each scenario.

- In JMeter, CSV Data Set Config is a useful component for parameterizing your tests with external data, such as usernames, passwords, or URLs, stored in a CSV file.

## Section 2: Setting up CSV Data Set Config for Dynamic Input Data

- The CSV Data Set Config element reads data from a CSV file and provides this data to JMeter's samplers as variables. 

- Each line of the CSV file corresponds to a set of values for one test iteration (or user).

- Key Configuration Options:

    - **File Name**: The path to the CSV file that contains the dynamic input data.
    
    - **Variable Names**: A comma-separated list of variable names that match the data fields in the CSV file.
    
    - **Delimiter**: The character that separates the data fields in the CSV file (default is a comma).
    
    - **Sharing Mode**: Defines how the CSV data is shared across threads, such as sharing the same data for all threads or giving each thread its own set of data.

- Steps to Add a CSV Data Set Config:
        
    1. Right-click on the Thread Group.

    2. Select Add > Config Element > CSV Data Set Config.

    3. In the CSV Data Set Config panel, specify:

        - The path to the CSV file (e.g., users.csv).
        
        - The variable names that correspond to each column in the CSV (e.g., username, password).
        
        - Other options, such as delimiter and sharing mode if necessary.

- For example, if your CSV file (users.csv) contains the following data:

    ```
    user1,password1
    user2,password2
    user3,password3
    ```

- You would use the variables ```${username}``` and ```${password}``` in your HTTP requests to dynamically inject this data.

## Section 3: Using Variables to Simulate Multiple Users or Requests

- Once the CSV Data Set Config is set up, JMeter will automatically substitute the variable values in each iteration of the test.

- Example:

    - In an HTTP Request Sampler, you might set the Username field to ```${username}``` and the Password field to ```${password}```. 
    
    - For each thread (or user) in the test, JMeter will use the corresponding data from the CSV file.
    
    - This setup allows you to simulate multiple users logging into an application with different credentials.
    
- By using CSV Data Set Config and variables, you can easily scale your test scenarios to hundreds or thousands of unique users or requests.

## Summary

- In this chapter, you learned how to use CSV Data Set Config to parameterize your JMeter tests. 

- By pulling data from CSV files and using variables, you can dynamically simulate multiple users or requests, making your tests more flexible and realistic.

<div style="display: flex; justify-content: space-between; width: 100%; margin-top: 100px;">
    <a href="../Chapter-7/README.md" style="padding: 10px 20px; background-color: #007bff; color: white; text-decoration: none; border-radius: 5px;">Previous</a>
    <a href="../Chapter-9/README.md" style="padding: 10px 20px; background-color: #007bff; color: white; text-decoration: none; border-radius: 5px;">Next</a>
</div>