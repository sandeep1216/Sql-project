//employee table:
//creation of employee table:

CREATE TABLE employee (
    employee_id INT PRIMARY KEY,
    employee_name VARCHAR(50),
    date_of_birth DATE,
    address VARCHAR(100),
    contact_number VARCHAR(15),
    hire_date DATE,
    job_title VARCHAR(50),
    salary DECIMAL(10, 2)
);

//inserting some rows into the employee table:

INSERT INTO employee (employee_id, employee_name, date_of_birth, address, contact_number, hire_date, job_title, salary)
VALUES
    (1, 'John Smith', '1985-04-15', '123 Main Street, Cityville, USA', '+1 (555) 123-4567', '2010-09-01', 'Software Engineer', 75000.00),
    (2, 'Jane Doe', '1990-11-10', '456 Park Avenue, Townsville, USA', '+1 (555) 987-6543', '2015-03-15', 'Marketing Manager', 85000.00),
    (3, 'Michael Johnson', '1988-08-22', '789 Oak Road, Villageland, USA', '+1 (555) 222-3333', '2012-06-30', 'Sales Representative', 60000.00),
    (4, 'Emily Williams', '1992-02-28', '246 Elm Street, Hamletown, USA', '+1 (555) 444-5555', '2018-11-20', 'Human Resources Specialist', 70000.00),
    (5, 'Robert Lee', '1980-12-05', '135 Pine Avenue, Forestville, USA', '+1 (555) 777-8888', '2005-01-10', 'Project Manager', 90000.00);

//retriving information from employee table
select * from employee
//department table
//creation of department table:

CREATE TABLE department (
    department_id INT PRIMARY KEY,
    department_name VARCHAR(50),
    department_manager_id INT,
    manager_name VARCHAR(50),
    manager_salary DECIMAL(10, 2),
    FOREIGN KEY (department_manager_id) REFERENCES employee (employee_id)
);

//inserting some rows into the department table:

INSERT INTO department (department_id, department_name,department_manager_id, manager_name, manager_salary) VALUES
    (1, 'Marketing', 2, 'Jane Doe', 85000.00),
    (2, 'Sales', 3, 'Michael Johnson', 60000.00),
    (3, 'Human Resources', 4, 'Emily Williams', 70000.00),
    (4, 'Engineering', 1, 'John Smith', 75000.00),
    (5, 'Finance', 5, 'Robert Lee', 90000.00);

//retriving information from employee table
select * from department;

//grades_of_employee table
//creation of grades_of_employee table:

CREATE TABLE grades_of_employee (
    grade_id INT PRIMARY KEY,
    employee_id INT,
    grade VARCHAR(5),
    FOREIGN KEY (employee_id) REFERENCES employee (employee_id)
);

//inserting some rows into the grades_of_employee table:

INSERT INTO grades_of_employee (grade_id, employee_id, grade)
VALUES
    (1, 1, 'A'),
    (2, 2, 'B'),
    (3, 3, 'C'),
    (4, 4, 'B+'),
    (5, 5, 'A-');

//retriving information from grades_of_employee table
select * from grades_of_employee;
