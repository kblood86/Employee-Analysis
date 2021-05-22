# SQL Analysis

## Background

It is a beautiful spring day, and it is two weeks since you have been hired as a new data engineer at Pewlett Hackard. Your first major task is a research project on employees of the corporation from the 1980s and 1990s. All that remain of the database of employees from that period are six CSV files.

The CSVs were inspected and using quickdatabbasediagrams.com an ERD was created.

![table_erd](https://user-images.githubusercontent.com/77282780/119243089-c0f4ea80-bb31-11eb-91fc-3161a6e71aed.png)

From this ERD we can see that the employee table and the department table are the two "main" tables to connect the data.

Using these CSVs and the ERD, a table schema was created and the CSV files were imported into the corresponding SQL table.

After completing the import, the following queries were run:

1. List the following details of each employee: employee number, last name, first name, sex, and salary.

2. List first name, last name, and hire date for employees who were hired in 1986.

3. List the manager of each department with the following information: department number, department name, the manager's employee number, last name, first name.

4. List the department of each employee with the following information: employee number, last name, first name, and department name.

5. List first name, last name, and sex for employees whose first name is "Hercules" and last names begin with "B."

6. List all employees in the Sales department, including their employee number, last name, first name, and department name.

7. List all employees in the Sales and Development departments, including their employee number, last name, first name, and department name.

8. In descending order, list the frequency count of employee last names, i.e., how many employees share each last name.

## Bonus

After becoming suspisious that the data given is fake, visualization of the data is generated to help confirm the suspision.

First, the SQL database is imported into pandas. The starting point for this was given as the following:

   ```sql
   from sqlalchemy import create_engine
   engine = create_engine('postgresql://localhost:5432/<your_db_name>')
   connection = engine.connect()
   ```

To visualize the most common salary ranges for employees, a histogram is created.

![Common Salary Ranges for Employees](https://user-images.githubusercontent.com/77282780/119243271-36ad8600-bb33-11eb-8f25-7655791a3e2c.png)

It is an abnormally high number of salaries on the lower end of the scale.

To visualize the average salary by title, a bar chart is created.

![Average Salary by Title](https://user-images.githubusercontent.com/77282780/119243328-a459b200-bb33-11eb-9719-69ffa889873f.png)

The title of Senior Engineer has the same approximate salary as Engineer and Assistant Engineer leading me to the conclusion that the data is fake. Another aspect leading to the conclusion of fake data is that the Staff have a higher average salary than Senior Engineers. 


## Epilogue

Evidence in hand, you march into your boss's office and present the visualization. With a sly grin, your boss thanks you for your work. On your way out of the office, you hear the words, "Search your ID number." You look down at your badge to see that your employee ID number is 499942.

Report submitted by: April Foolsday

