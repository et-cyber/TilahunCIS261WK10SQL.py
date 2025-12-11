# Eyob Tilahun
# CIS 261 – Week 10 Assignment
# December 15, 2025

import sqlite3

# Create database connection and cursor
conn = sqlite3.connect("phone.db")
cursor = conn.cursor()

# CREATE TABLE statement
cursor.execute("""
CREATE TABLE phone (
    phone_id INT PRIMARY KEY,
    country_code INT NOT NULL,
    phone_number INT NOT NULL,
    phone_type VARCHAR(12)
)
""")

# SELECT statement
cursor.execute("""
SELECT phone_number
FROM phone
WHERE country_code = "US"
""")

# UPDATE statement
cursor.execute("""
UPDATE phone
SET phone_type = "MOBILE"
WHERE phone_type = "CELLULAR"
""")

# DELETE statement
cursor.execute("""
DELETE FROM phone
WHERE country_code = "XX"
""")

# DROP TABLE statement
cursor.execute("""
DROP TABLE phone
""")

# Commit changes and close connection
conn.commit()
conn.close()
