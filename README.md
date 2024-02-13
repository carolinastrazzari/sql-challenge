# Modify this code to update the DB schema diagram.
# To reset the sample schema, replace everything with
# two dots ('..' - without quotes).

departments
-
dept_no VARCHAR(4) PK
dept_name VARCHAR(25)


titles
-
title_id VARCHAR(5) PK
title VARCHAR(25)


employees
-
emp_no INT PK
emp_title_id VARCHAR(5) FK >- titles.title_id	
birth_date VARCHAR(10)	
first_name VARCHAR(25)
last_name VARCHAR(25)	
sex VARCHAR(1)
hire_date VARCHAR(10)

dept_manager
-
dept_no VARCHAR(4) FK >- departments.dept_no
emp_no INT PK FK >- employees.emp_no

dept_emp
-
emp_no INT PK FK >- employees.emp_no
dept_no VARCHAR(4) PK FK >- departments.dept_no

salaries
-
emp_no INT PK FK - employees.emp_no
salary INT
