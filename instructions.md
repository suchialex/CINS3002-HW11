# Instructions

<details>
  <summary>
    Assignment Instructions
  </summary>
 
We maintain employee inventory, by writing code to accomplish the following operations using SQL statements     
- Add Employee
- Lookup Employee
- Update Name
- Update Department
- Update Salary
- Delete Employee
- Display Employees  
  
</details>


# Start Working

<details>
  <summary>
    ✅ Create Pycharm Project
  </summary>

  - Create project
  - Copy contents of main.py 
  - Create a folder `hw11`
  - Inside hw11 copy contents of validations.py
  - Inside hw11 create new file db_functions.py
  - Copy employee_operations() function from from previous assignments class_functions.py (from employees folder)
  - Inside hw11, ceate new file `employees.db`
</details>

## In db_functions.py

<details>
  <summary>
    ✅ Modify employee_operations()
  </summary>

  - Remove the function call to file_to_dictionary() 
  - Open connection to database named employees.db (import the required package)  
    ⏩ Refer to Tutorial 14-5 a,b
  - Get the cursor for the connection ⏩ Refer to Tutorial 14-5c
  - Comment out the rest of the code (we will uncomment as we need it)
</details>


<details>
  <summary>
    ✅ Create table <code>employees</code>
  </summary>

  - In employee_operations function, after getting the cursor
  - Write statement to create table named `employees` only if it doesn't exist (⏩ Refer to 14-6e)
  - Columns are as follows
    - empid - integer and primary key
    - name - text
    - department - text
    - salary - real number
    - email - text
  - Commit the changes (⏩ Refer to 14-5e)
</details>


## In main.py

<details>
  <summary>
    ✅ Call employee_operations
  </summary>

  - Import the db_functions module
  - Call employee operations inside main body
</details>


## In employees/db_functions.py


<details>
<summary>
  ✅ Define add_employee()
</summary>

  - It accepts two parameters, connection and cursor
  - It doesn't return anything
  - In the function body:
    - Get employee name, department, salary, email using the validate functions in validations.py
    - Create a tuple of the above values (⏩ Refer to Tutorial 7-27c)
    - Write a parametrized statement to insert these values into the table `employees` (⏩ Refer to 14-7e)
    - Using the cursor, execute this by passing this statement and tuple as parameters      
    💡 We don't need to generate next ID and insert it because the database does it for you  
    - Commit the changes (⏩ Refer to 14-5e)  
    🚩 Make sure the number of elements in the tuple match the number of `?`

</details>


<details>
<summary>
  ✅ Call add_employee
</summary>

  - Uncomment the appropriate if-elif-else block to call add_employee function
  - Make sure to pass the connection and cursor as arguments
  - Execute code to make sure there are no errors
</details>


<details>
<summary>
  ✅ Define display_employees()
</summary>

  - It accepts one parameter, cursor
  - It returns nothing
  - In function body:
    - Write a SQL statement that selects all the rows from the table `employees` (⏩ Refer to 14-5e) 
    - Execute that statement using the cursor that is passed as the parameter
    - Get the rows using fetchall and store in a variable
    - This is a list of tuples or multi-dimensional list  
    Use `suchi_print` to see how the data looks like    
    - Using a for loop, print each data element
    - Use appropriate alignment and width to fit your data  
    💡 Hint: Check out the display_employees function in multilist_functions.py
</details>


<details>
<summary>
  ✅ Call display_employees()
</summary>
  
  - Uncomment the appropriate if-elif-else block to call display_employees function
  - Make sure to pass the cursor as argument
  - Execute code to see if employees are printed correctly
</details>



<details>
<summary>
  ✅ Define lookup_employee()
</summary>

  - It accepts parameters, cursor, empid   
  - It returns a Boolean
  - In the body,
    - Build a parametrized SQL Select statement to select all the columns from the table `employees` and in the WHERE clause check if the empid column matches the user entered empid (⏩ Refer to 14-8d) 
    - Using the cursor, execute it by passing the statement and tuple as arguments 
    - Get the row using fetchone
    - Print each data element in a new line
</details>


<details>
<summary>
  ✅ Call lookup_employee()
</summary>

  - Uncomment the appropriate if-elif-else block to call lookup_employee function
  - Get the employee ID from the user using an input statement
  - Make sure to pass the cursor and the employee ID as arguments
  - Execute code to see if employees are looked up correctly
</details>



<details>
<summary>
  ✅ Define update_employee_name()
</summary>

  - Parameters: connection, cursor  
  - Return: None
  - In the function body:
    - Ask the user to input employee ID
    - Build a parametrized SQL Update statement (⏩ Refer to 14-9a Try this) 
    - Execute that statement using the cursor that is passed as the parameter
    - Get the rowcount using the cursor (⏩ Refer to 14-9b)
    - If the rowcount is equal to zero,
      - print `Employee Not Found`
    - Otherwise,
      - Commit the changes using the connection that is passed as the parameter (⏩ Refer to 14-5e)
      - Print `Employee Name Updated`
</details>


<details>
<summary>
  ✅ Call update_employee_name()
</summary>

  - Uncomment the appropriate if-elif-else block to call update_employee_name function
  - Make sure to pass the cursor as argument
  - Execute code to see if employee name is updated correctly
</details>


<details>
  <summary>
    ✅ Complete writing code for other update functions
  </summary>

  - update_employee_department()
  - update_employee_salary()
</details>

<details>
<summary>
  ✅ Define delete_employee()
</summary>

  - Parameters: connection, cursor  
  - Return: None
  - In the function body:
    - Build a parametrized SQL Delete statement (⏩ Refer to 14-9c)   
    - Execute that statement using the cursor that is passed as the parameter
    - Get the rowcount using the cursor (⏩ Refer to 14-9b) 
      - If the rowcount is equal to zero,
        - print `Employee Not Found`
      - Otherwise,
        - Commit the changes using the connection that is passed as the parameter (⏩ Refer to 14-5e)
        - Print `Employee Deleted`
</details>


<details>
<summary>
  ✅ Call delete_employee()
</summary>

  - Uncomment the appropriate if-elif-else block to call delete_employee function
  - Make sure to pass the cursor as argument
  - Execute code to see if employee is deleted correctly
</details>


<details>
<summary>
  ✅ Modify employee_operations()
</summary>

  - After the while loop
    - Delete the function dictionary_to_file
    - Close the database connection (⏩ Refer to 14-5f)
</details>
