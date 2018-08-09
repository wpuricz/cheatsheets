---
title: Python Postgres
---

### Usage

    pip install psycopg2

### Connect
```python
conn = psycopg2.connect(database='budget_api_development', user='wpuricz', password="will123!")
```

```python
if conn:
    conn.close()
```

### Error Checking

```
try:
    // DB action here

except psycopg2.DatabaseError, e: 
    print 'Error %s' % e    
```

### Select
```
sql = "SELECT * FROM Categories"
cur = conn.cursor()
cur.execute(sql)
rows = cur.fetchall()
for row in rows:
    print(row[0])
```

### Insert
```
sql = """INSERT INTO TRANSACTIONS(account_id,category_id) VALUES(%s,%s);"""
cur = conn.cursor()
cur.execute(sql,(account,category))
conn.commit()
```

### Resources

- [Postgres Python Insert](http://www.postgresqltutorial.com/postgresql-python/insert/) _(www.postgresqltutorial.com)_
- [Postgres Python](http://zetcode.com/db/postgresqlpythontutorial/)