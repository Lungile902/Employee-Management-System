# Employee-Management-and-Analytical-System
database management for employees 
Employees at Ekuhlaleni company needed an employee database to manage their employees. Their employees must be managed in every contribution to the company. This includes their personal details, work they perform to the company, and to their salaries. Therefore, a complete database was established which contains a database schema, tables, sql queries, triggers, functions, and views.

## Database Design Objectives Overview
The Employee Performance and HR Analytics System database was designed to achieve sound conceptual, logical, and physical database design principles. The primary objective is to provide a secure, scalable, and eZicient database that supports the organization's Human Resources operations while enabling analytical reporting for management decision-making.
The design ensures that business rules are accurately represented, data redundancy is minimized, and the database performs eZiciently while remaining easy to maintain and extend.

### Conceptual Design
The conceptual design focuses on identifying the business entities, their relationships, and the organization's business requirements.
Objectives
• Store employee information securely.
• Organize employees into departments and job positions.
• Maintain employee salary history over time.
• Record employee attendance.
• Manage employee leave requests.
• Track employee training participation.
• Store employee performance review records.
• Record employee promotion history.
• Support HR analytics and reporting for informed business decision-making.

### Logical Design
The logical database design transforms the conceptual model into a structured relational database while ensuring data integrity and reducing redundancy.
Objectives
• Normalize the database to Third Normal Form (3NF).
• Define entities and relationships according to business rules.
• Establish appropriate cardinality between related entities.
• Enforce primary keys and foreign keys.
• Apply integrity constraints to maintain data consistency.
• Eliminate redundant data and update anomalies.

### Physical Design
The physical design focuses on implementing the database within PostgreSQL while ensuring performance, scalability, and maintainability.
Objectives
• Provide eZicient and flexible data storage.
• Optimize query performance through appropriate indexing and constraints.
• Support future cloud deployment.
• Maintain cost-eZective database management.
• Ensure the database is easy to maintain and scale.
• Preserve data integrity through constraints and validation rules

## Database Normalisation
The Employee Performance and HR Analytics System database has been normalized to Third Normal Form (3NF). Normalization improves database quality by reducing redundancy, preventing data anomalies, and ensuring that each table stores information about a single business entity.
Benefits of Normalization
• Eliminates duplicate data.
• Prevents insert, update, and delete anomalies.
• Improves data integrity.
• Simplifies database maintenance.
• Enhances scalability.
• Produces a well-structured relational database.

### First Normal Form (1NF)
The database satisfies First Normal Form (1NF) by ensuring that:
• Each table has a primary key.
• Every column contains atomic (indivisible) values.
• No repeating groups or multivalued attributes exist.
• Each record is unique.
Example: Employees
EmployeeID FirstName LastName Email
1001 John Smith john@email.com

### Second Normal Form (2NF)
The database satisfies Second Normal Form (2NF) by ensuring that:
• It already satisfies 1NF.
• Every non-key attribute is fully dependent on the entire primary key.
• Partial dependencies have been eliminated.
For example, employee details are stored only in the Employees table, while department information is stored separately in the Departments table and referenced using foreign keys.

### Third Normal Form (3NF)
The database satisfies Third Normal Form (3NF) by ensuring that:
• It already satisfies 2NF.
• No transitive dependencies exist.
• Non-key attributes depend only on the primary key.
• Each table represents a single business entity.
Examples include separating: Employees, Departments, Positions, Salaries, Attendance, Leave requests,Performance review, Training, Promotions

## The following entities/ database objects were created in order to form an accurate relational database schema for the business rules.
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

## DESIGN DECISIONS
The design decisions were primarily made to ensure the database provides functionality, adaptability, and maintainability.
Functionality
Functionality focuses on ensuring that the database operates effectively and satisfies the defined business rules. Firstly, it was important to identify all the entities required by the database. The identified entities were based on the different aspects of the business requirements and were used to determine the relationships between them.
The database was also designed to preserve historical information. Salary, training, and promotion information are stored separately from the employee information, allowing historical records to be retained rather than overwritten when changes occur. Similarly, performance reviews are separated from employee information because an employee may receive multiple performance reviews over time.
The design also supports in-depth data analysis through the use of database views. These views contain predefined business queries that can be used to retrieve meaningful information for reporting and analysis. In addition, trigger functions were incorporated to perform automatic calculations for numerical values, reducing the need for these calculations to be performed manually.
Adaptability
Adaptability prioritises the flexibility of the database when integrating with third-party software and when changes occur to the hardware or software environment. PostgreSQL was selected as the database management system because it provides compatibility with external tools and applications.
For example, the database can be connected to Power BI for further data analysis and reporting. The views created in the database can be imported into Power BI and used as data sources for reports, dashboards, and visualisations. This allows the database to remain focused on storing and processing data while Power BI can be used for more advanced reporting and data visualisation.
Furthermore, PostgreSQL is not dependent on a specific hardware configuration, which provides flexibility when the underlying hardware or software environment changes.
Maintainability
Maintainability focuses on making it easier to perform insert, update, and delete operations and to manage changes to the database over time. The database was structured into separate entities with clearly defined relationships, which makes individual components easier to manage and modify without unnecessarily affecting unrelated data.
The EmployeeTraining entity was introduced to resolve the many-to-many relationship between employees and training. An employee can participate in multiple training programmes, while a training programme can be attended by multiple employees. Rather than creating a direct many-to-many relationship, the EmployeeTraining entity acts as an associative entity between the two tables. This improves the structure of the database and provides a suitable location for storing information specific to an employee's participation in a particular training programme.
Overall, these design decisions were intended to create a database that is functional in meeting the business requirements, adaptable to external reporting and software environments, and maintainable as the system and its data requirements evolve.







