---
layout: project
type: project
image: images/recordkeeper.png
title: Record Keeper
permalink: projects/recordkeeper
# All dates must be YYYY-MM-DD format!
date: 2017-08-01
labels:
  - C++
  - Unix
  - SCCS
summary: A record keeper program created as a project for ICS 212.
---

<img class="ui medium right floated rounded image" src="../images/recordkeeperexample.png">

This program is a record keeper tasked during ICS 212, Summer 2017. This project taught me how to use Unix to compile my C/C++ code along with managing my files within the Unix environment using Makefiles and SCCS.

This record keeper allows users to input names and addresses associated with a unique account number. The program keeps track of added records through different sessions, and allows users to modify and delete existing records as well.

I gained experience in using C++ to code the record keeper, as well as using makefiles and SCCS within a Unix environment to help with management of the files involved in the project.
 
Here is some sample code from the record keeper:

```C++
while (menu == 1)
    {
        cout << "\n";
        #ifdef DEBUG
            cout << "Currently running in DEBUG MODE...\n\n";
        #endif
        
        cout << "Please type in the number of the choice you would like to make.\n";
        cout << "1. Add a new record in the database.\n";
        cout << "2. Modify a record in the database.\n";
        cout << "3. Print information about a specific record.\n";
        cout << "4. Print all information in the database.\n";
        cout << "5. Delete an existing record from the database.\n";
        cout << "6. Reverse the records in the database.\n";
        cout << "7. Exit the program.\n";
        cout << "Please enter a choice: ";
        cin >> choice;
        if (cin.fail())
        {
            choice = 8;
        }
        cin.clear();
        cin.ignore(INT_MAX, '\n');
        cout << "\n";
        if (choice == 1)
        {
            getAccountno(accountno);
            cout << "Please enter the name of the record (maximum of 50 characters for name): ";
            getname(name, 50);
            cout << "Please enter the address for the record. To signify the end of the record, enter the character '~':\n";
            getaddress(address, 100);
            if (mylist.addRecord(accountno, name, address) == 1)
            {
                cout << "Record added successfully.\n";
            }
            else
            {
                cout << "Reocrd not successfully added.\n";
            }
        }
     ...
...
}
```
