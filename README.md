# Employee-Management-System
database management for employees 
Employees at Ekuhlaleni company needed an employee database to manage their employees. The employees must be managed in every contribution to the company. This includes their personal details, work they perform to the company, to their salaries. Therefore a complete database was established,with a database schema, table, sql inserts, sql table, sql queries, trigers, function, and views.

### The following entities/ database objects were created in order to form an accurate relational database schema for the business rules.
attendence: employee records which give information about the attendence of employees. Furthermore, these records explain which time employees check in and out
departments: records containing information about the departments each employee works for
employees: contain recors which give in depth description about each employee. This table contains personal information about each employee that works in the company, their names, contact number, gender etc.
employee training:
leave requests: 
performance review, 
positions:
promotion,:
salary:
training:

### Database schema
sequence,
tables: 
ERD
<img width="1174" height="1116" alt="database for employees" src="https://github.com/user-attachments/assets/eda17fb0-2593-4868-8dd7-19c78f3759e3" />

functions,triger functions, views

###Database queries with scripts
CREATE SCRIPT ATTENDENCE TABLE
-- Table: public.attendance

-- DROP TABLE IF EXISTS public.attendance;

CREATE TABLE IF NOT EXISTS public.attendance
(
    attendenceid integer NOT NULL DEFAULT nextval('attendance_attendenceid_seq'::regclass),
    employeeid integer,
    dateattend date,
    checkin time without time zone,
    checkout time without time zone,
    hoursworked numeric(10,2),
    CONSTRAINT pk_attendence PRIMARY KEY (attendenceid),
    CONSTRAINT fk_employee_id FOREIGN KEY (employeeid)
        REFERENCES public.employees (employeeid) MATCH SIMPLE
        ON UPDATE CASCADE
        ON DELETE SET NULL
)

TABLESPACE pg_default;

ALTER TABLE IF EXISTS public.attendance
    OWNER to postgres;

CREATE SCRIPT DEPARTMENTS TABLE
-- Table: public.departments

-- DROP TABLE IF EXISTS public.departments;

CREATE TABLE IF NOT EXISTS public.departments
(
    departmentid integer NOT NULL DEFAULT nextval('departments_departmentid_seq'::regclass),
    departmentname character varying(100) COLLATE pg_catalog."default" NOT NULL,
    managerid integer,
    located character varying(100) COLLATE pg_catalog."default",
    CONSTRAINT pk_departments PRIMARY KEY (departmentid)
)

TABLESPACE pg_default;

ALTER TABLE IF EXISTS public.departments
    OWNER to postgres;


    
