# Complaint Management System Project in Python Source Code

The **Complaint Management System in Python** is a simple desktop application and the database used in this system is Sqlite3. 

The **Complaint Management System** project file contains python scripts(complain-system-main.py, configdb.py, complaintListing.py) and sqlite database. 

Complaint Management System is using a Tkinter graphical user interface(GUI).

To start creating a **Complaint Management System in Python**, make sure you have PyCharm IDE and SQLITE3 installed on your computer.

By the way, if you are new to Python programming and don’t know what Python IDE to use, I have here a list of the Best Python IDE for Windows, Linux, and Mac OS that will suit you.

## How to Create a Complaint Management System Project in Python?

1. **Create a Project Name**.

First step open the PyCharm IDE and click “File” and select “New Project” and then create a project name after that click the “create” button.

2. **Create a Python File**.

In the second step after creating a project name, “right” click the project name, and then click “New.” After that choose “Python File”.

<img width="1366" height="728" alt="image" src="https://github.com/user-attachments/assets/c337e4e8-76dd-4e6b-ac57-98f59a7580ff" />

3. **Name the Python File**.

The third step after choosing Python File name the file “Complaint System” and then click “Enter”.

4. **The actual code**.

Now you can start coding, you are free to copy the code that being provided below.

## Code Explanations

1. **Importing Tkinter Module**

Tkinter is the standard GUI library for Python. Python when combined with Tkinter provides a fast and easy way to create GUI applications. 

```
from tkinter import *
from tkinter.ttk import *
from tkinter.messagebox import *
```
In the code above, which is for importing tkinter just write 3 lines of code.


2. **Importing the Sqlite3 Module**

SQLite is a C library that provides a lightweight disk-based database that doesn’t require a separate server process and allows accessing the database using a nonstandard variant of the SQL query language. 

```
import sqlite3
```

In the code above, which is for importing sqlite just write one line of code.

3. **Create Database**

This module is for Creating a Database.

```
def __init__(self):
self._db = sqlite3.connect('complaintDB.db')
self._db.row_factory = sqlite3.Row
self._db.execute('create table if not exists complainTable(ID integer primary key autoincrement, FirstName varchar(255), LastName varchar(255), Address Text, Gender varchar(255), Comment text)')
self._db.commit()
```

In the code above, which is for creating a database name “complaintDb.db” and for the table name “complainTable.”

4. **Main Window**

The Design and Style for the Main Window.

So first of all you have to design the main screen. This display screen has a label of first name, last name, gender, and comment, the radio buttons have only two male and female, and for the buttons, it is view complain and submit now.

So let’s see the way to put it into effect:

```
conn = ConnectionDatabase()
root = Tk()
root.geometry('550x350')
root.title('Complaint Management System')
root.configure(bg='blue')


labels = ['First Name:', 'Last Name:', 'Address:', 'Gender:', 'Comment:']
for i in range(4):
Label(root, text=labels[i]).grid(row=i, column=0, padx=10, pady=10)


ButtonList = Button(root, text='View Complain')
ButtonList.grid(row=5, column=1)

BuSubmit = Button(root, text='Submit Now')
BuSubmit.grid(row=5, column=2)

# Entries
firstname = Entry(root, width=40, font=('Arial', 14))
firstname.grid(row=0, column=1, columnspan=2)

lastname = Entry(root, width=40, font=('Arial', 14))
lastname.grid(row=1, column=1, columnspan=2)

address = Entry(root, width=40, font=('Arial', 14))
address.grid(row=2, column=1, columnspan=2)

GenderGroup = StringVar()
Radiobutton(root, text='Male', value='male', variable=GenderGroup).grid(row=3, column=1)
Radiobutton(root, text='Female', value='female', variable=GenderGroup).grid(row=3, column=2)

comment = Text(root, width=40, height=5, font=('Arial', 14))
comment.grid(row=4, column=1, columnspan=2, padx=10, pady=10)
```

* You can also minimize or maximize the design of the main screen window in line with your choice and make it extra attractive.
* When the above code is executed, let’s see the output of this code.

### Output:

<img width="552" height="382" alt="image" src="https://github.com/user-attachments/assets/1cc4881d-cc47-4018-8e98-53dced86a19f" />

5. **Create Table**

This Module is for Creating a Table.

```
class ComplaintListing:
def __init__(self):
self.connectionDB = ConnectionDatabase()
self.connectionDB.row_factory = sqlite3.Row
self.root = Tk()
self.root.title('List of Complaints')
tree = Treeview(self.root)
tree.pack()
tree.heading('#0', text='ID')
tree.configure(column=('#FirstName', '#LastName', '#Address', '#Gender', '#Comment'))
tree.heading('#FirstName', text='First Name')
tree.heading('#LastName', text='Last Name')
tree.heading('#Address', text='Address')
tree.heading('#Gender', text='Gender')
tree.heading('#Comment', text='Comment')
tree.column('#0', stretch=NO, minwidth=0, width=100)
tree.column('#1', stretch=NO, minwidth=0, width=100)
tree.column('#2', stretch=NO, minwidth=0, width=100)
tree.column('#3', stretch=NO, minwidth=0, width=100)
tree.column('#4', stretch=NO, minwidth=0, width=100)
tree.column('#5', stretch=NO, minwidth=0, width=300)
cursor = self.connectionDB.ListRequest()
for row in cursor:
tree.insert('', 'end', '#{}'.format(row['ID']), text=row['ID'])
tree.set('#{}'.format(row['ID']), '#FirstName', row['FirstName'])
tree.set('#{}'.format(row['ID']), '#LastName', row['LastName'])
tree.set('#{}'.format(row['ID']), '#Address', row['Address'])
tree.set('#{}'.format(row['ID']), '#Gender', row['Gender'])
tree.set('#{}'.format(row['ID']), '#Comment', row['Comment'])
```

In the code above, This method will show you how to create a table in the complaint management system window.

When the above code is executed, it produces the following result below.

<img width="805" height="259" alt="image" src="https://github.com/user-attachments/assets/a69e9527-4d68-4253-8d83-07225c5ef7a7" />

### 📌 Here's the full documentation for the [Complaint Management System in Python](https://itsourcecode.com/free-projects/python-projects/complaint-management-system-project-in-python-with-source-code/)
---
### Related Articles

* **[Complaint Management System in PHP](https://itsourcecode.com/free-projects/php-project/complaint-management-system-source-code-php/)**
* **[Complaint Management System in Django](https://itsourcecode.com/free-projects/python-projects/complaint-management-system-project-in-django-with-source-code/)**
* **[Complaint Management System Project in C++](https://itsourcecode.com/free-projects/cplusplus-projects/complaint-management-system-in-c-with-source-code/)**
