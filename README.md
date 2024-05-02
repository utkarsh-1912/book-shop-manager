# Book Shop Management System

### Concept used:
- **OOPs**
- **DBMS**

MySQL Database Required

## Tables

### Books

- **id** INT PRIMARY KEY
- **name** VARCHAR(255)
- **auth** VARCHAR(255)
- **price** INT
- **qty** INT
- **supplier_id** INT FOREIGN KEY REFERENCES suppliers(id)

### Suppliers

- **id** INT PRIMARY KEY
- **name** VARCHAR(255)
- **phn** BIGINT
- **addr_line1** VARCHAR(255)
- **addr_line2** VARCHAR(255)
- **addr_city** VARCHAR(255)
- **addr_state** VARCHAR(255)

### Purchases

- **ord_id** INT PRIMARY KEY
- **book_id** INT FOREIGN KEY REFERENCES books(id)
- **supp_id** INT FOREIGN KEY REFERENCES suppliers(id)
- **qty** INT
- **dt_ordered** DATE
- **eta** INT
- **received** CHAR(1) CHECK(received IN ('T', 'C', 'F')) DEFAULT 'F'
- **inv** INT

### Employees

- **id** INT PRIMARY KEY
- **name** VARCHAR(255)
- **addr_line1** VARCHAR(255)
- **addr_line2** VARCHAR(255)
- **addr_city** VARCHAR(255)
- **addr_state** VARCHAR(255)
- **phn** BIGINT
- **date_of_joining** DATE
- **salary** BIGINT
- **mgr_status** CHAR(1) CHECK(mgr_status IN ('T', 'F')) DEFAULT 'F'

### Members

- **id** INT PRIMARY KEY
- **name** VARCHAR(255)
- **addr_line1** VARCHAR(255)
- **addr_line2** VARCHAR(255)
- **addr_city** VARCHAR(255)
- **addr_state** VARCHAR(255)
- **phn** BIGINT
- **beg_date** DATE
- **end_date** DATE
- **valid** VARCHAR(10)

### Sales

- **invoice_id** INT PRIMARY KEY
- **member_id** INT FOREIGN KEY REFERENCES members(id)
- **book_id** INT FOREIGN KEY REFERENCES books(id)
- **qty** INT
- **amount** INT
- **date_s** DATE
