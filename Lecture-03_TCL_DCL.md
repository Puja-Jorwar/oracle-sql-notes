📘 Lecture 03 – TCL & DCL (Oracle SQL)

📅 Topic covered in today’s lecture:
Transaction Control Language (TCL) & Data Control Language (DCL)

🔹 Transaction Control Language (TCL)

TCL is used to control database transactions.
A transaction is a set of SQL statements executed as a single unit.

🟢 TCL Commands

COMMIT

ROLLBACK

SAVEPOINT

🔸 COMMIT

Saves all changes made by DML commands permanently.

INSERT INTO SPORTS VALUES (1, 'VIRAT', 'CRI');
COMMIT;


✔ Changes are saved
❌ Cannot rollback after commit

🔸 ROLLBACK

Undoes changes made after the last COMMIT.

DELETE FROM SPORTS WHERE PLAYER_ID = 1;
ROLLBACK;


✔ Restores previous state

🔸 SAVEPOINT

Creates a checkpoint inside a transaction.

SAVEPOINT s1;


Rollback to savepoint:

ROLLBACK TO s1;

🔸 SAVEPOINT Example
INSERT INTO SPORTS VALUES (2, 'ROHIT', 'CRI');
SAVEPOINT s1;

INSERT INTO SPORTS VALUES (3, 'DHONI', 'CRI');
ROLLBACK TO s1;

COMMIT;


👉 Only ROHIT is saved.

🔹 Data Control Language (DCL)

DCL is used to control access to database objects.

🟢 DCL Commands

GRANT

REVOKE

🔸 GRANT

Gives permission to a user.

GRANT SELECT ON EMP TO HR;

🔸 Grant Multiple Privileges
GRANT SELECT, INSERT, UPDATE ON EMP TO HR;

🔸 Grant with GRANT OPTION
GRANT SELECT ON EMP TO HR WITH GRANT OPTION;

🔸 Column-Level Grant
GRANT UPDATE (SAL, COMM) ON EMP TO HR;

🔸 REVOKE

Removes permission.

REVOKE SELECT ON EMP FROM HR;

🔁 Difference Between TCL and DCL
Feature	TCL	DCL
Purpose	Control transactions	Control access
Commands	COMMIT, ROLLBACK, SAVEPOINT	GRANT, REVOKE
Works on	Data	Users & privileges
✍️ Lecture Notes Summary

TCL manages saving and undoing data

DCL manages who can access data

Both ensure data safety and control
