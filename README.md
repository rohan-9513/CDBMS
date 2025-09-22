# Marvellous DBMS (Java)

A simple **Database Management System (DBMS) Simulator** built using **Java**.  
It demonstrates how a DBMS works internally by supporting operations like **insert, select, delete, and backup/restore** using file serialization.

---

## 📌 Features

- Insert new employee records into the database.
- Display all employee records.
- Select employee records by:
  - Employee ID
  - Employee Name
- Delete employee records by ID.
- Backup the database to a file (`MarvellousDBMS.ser`).
- Restore the database from the backup file.
- Auto-generated unique `EmpID` for every employee.

---

## 🗂️ Project Structure

```
.
├── Employee.java         # Employee class (Serializable)
├── MarvellousDBMS.java   # Core DBMS operations
├── CDBMS.java            # Main driver program with CLI
├── MarvellousDBMS.ser    # Backup file (created at runtime)
```

---

## ⚙️ How It Works

- **Employee class**
  - Holds employee details (`EmpID`, `Name`, `Age`, `Address`, `Salary`).
  - `EmpID` is auto-incremented using a static counter.
  - Implements `Serializable` for persistence.

- **MarvellousDBMS class**
  - Maintains an in-memory `LinkedList<Employee>` as the database table.
  - Provides methods to insert, select, delete, backup, and restore records.
  - Uses **Java Serialization** for saving and loading the database.

- **CDBMS class**
  - Acts as the main driver program.
  - Provides a **menu-driven CLI** for the user to interact with the DBMS.

---

## ▶️ How to Run

1. **Compile the program**  
   ```bash
   javac CDBMS.java
   ```

2. **Run the program**  
   ```bash
   java CDBMS
   ```

3. **Choose operations from the menu**  
   ```
   1 : insert into employee
   2 : select * from employee
   3 : Take a backup of table
   4 : select * from employee where EmpID = ___
   5 : select * from employee where EmpName = ___
   6 : delete from employee where EmpID = ___
   20 : Terminate the DBMS
   ```

---

## 💾 Backup & Restore

- The database is stored in the file **`MarvellousDBMS.ser`** when you take a backup.
- On the next run, the system attempts to **restore the backup** automatically.
- If the backup file is missing, a **new DBMS instance** is created.

---

## 📖 Example Usage

```
--------------------------------------------------
---------------- Marvellous DBMS -----------------
--------------------------------------------------
1 : insert into employee
2 : select * from employee
3 : Take a backup of table
4 : select * from employee where EmpID = ___
5 : select * from employee where EmpName = ___
6 : delete from employee where EmpID = ___
20 : Terminate the DBMS
--------------------------------------------------
Please select the desired operation on the database
```

---

## 🛠️ Technologies Used

- **Java SE**
- **File Handling**
- **Object Serialization**
- **LinkedList**

---

## 📌 Future Enhancements

- Add **update query support** (update employee details).
- Support for **multiple tables**.
- Implement **SQL-like query parsing** instead of menu-driven CLI.
- Add **export/import in JSON/CSV** format.

---