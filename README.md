# 51.Python-SQLite-InMemory-Database

import sqlite3

try:
    # File-based database connection
    sqlite_Connection = sqlite3.connect('temp.db')

    # In-memory database connection
    conn = sqlite3.connect(':memory:')
    print("\nMemory database created and connected to SQLite.")

    # SQL query
    sqlite_select_Query = "select sqlite_version();"
    cursor = conn.cursor()
    cursor.execute(sqlite_select_Query)

    # Fetch result
    record = cursor.fetchone()
    print("\nSQLite Database Version is:", record)

    conn.close()

except sqlite3.Error as error:
    print("\nError while connecting to sqlite", error)

finally:
    if sqlite_Connection:
        sqlite_Connection.close()
        print("\nThe SQLite connection is closed.")

Output:
Memory database created and connected to SQLite.

SQLite Database Version is: ('3.50.4',)

The SQLite connection is closed.
