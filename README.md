# SQL Project: Security-Related Queries Using Filters

## Project Description

In this project, I utilized SQL filters to perform security-related tasks for an organization. The goal was to ensure the system's security by investigating potential issues and updating employee computers when necessary. Below are several SQL queries I wrote to filter data based on different security concerns.

## SQL Queries:

1. **Retrieve After-Hours Failed Login Attempts**  
A potential security incident occurred after business hours (after 18:00). I needed to investigate all failed login attempts that occurred after hours.

    ```sql
    SELECT * 
    FROM log_in_attempts
    WHERE login_time > '18:00' AND success = FALSE;
    ```

    This query filters for login attempts that occurred after 18:00 and were unsuccessful.

2. **Retrieve Login Attempts on Specific Dates**  
A suspicious event occurred on 2022-05-09. I needed to investigate login attempts that occurred on this date and the day before (2022-05-08).

    ```sql
    SELECT * 
    FROM log_in_attempts
    WHERE login_date = '2022-05-09' OR login_date = '2022-05-08';
    ```

    This query filters for login attempts on either 2022-05-09 or 2022-05-08.

3. **Retrieve Login Attempts Outside of Mexico**  
After reviewing the organization's data, I found that login attempts outside of Mexico should be investigated.

    ```sql
    SELECT * 
    FROM log_in_attempts
    WHERE country NOT LIKE 'MEX%';
    ```

    This query filters for login attempts that occurred outside of Mexico by excluding entries where the country code starts with "MEX".

4. **Retrieve Employees in the Marketing Department**  
I needed to update the computers of employees in the Marketing department located in the East building.

    ```sql
    SELECT * 
    FROM employees
    WHERE department = 'Marketing' AND office LIKE 'East%';
    ```

    This query filters for employees who work in the Marketing department and are located in the East building.

5. **Retrieve Employees in Finance or Sales**  
To apply a different security update, I needed to get information about employees in the Finance or Sales departments.

    ```sql
    SELECT * 
    FROM employees
    WHERE department = 'Finance' OR department = 'Sales';
    ```

    This query filters for employees in either the Finance or Sales departments.

6. **Retrieve Employees Not in IT**  
Finally, I needed to gather information about employees who are not in the Information Technology (IT) department for another security update.

    ```sql
    SELECT * 
    FROM employees
    WHERE department NOT LIKE 'IT';
    ```

    This query filters for employees who are not in the IT department.

## Summary

In this project, I applied SQL filters to retrieve specific information related to login attempts and employee machines. I worked with two main tables: `log_in_attempts` and `employees`. I used various SQL operators like `AND`, `OR`, `NOT`, and `LIKE` to filter data and retrieve the information needed for security-related tasks.
