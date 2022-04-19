# DevSqlite3-new
DevSqlite3 now is supported MySQL Database and Sqlite Database.

# how to use?

Create your python file

```
from DevSqlite3.core import MySqlDatabase, Table, Database

# mysql database

@MySqlDatabase('Database', host='localhost', user='root', password='password')
class Whitelist(Table):
    id = Table.integerField(primary=True, null=False) # column id
    discord = Table.integerField() # column discord 
    whitelisted = Table.booleanField() # column whitelisted


# sqlite database exmaple

@Database('settings', path='database')
class Settings(Table):
    id = Table.integerField(primary=True, null=False) # column id
    autoRemove = Table.booleanField() # column autoRemove 
    autoGiver = Table.booleanField() # column autoGiver
    managers = Table.listField() # column managers
```

# how to use it?
just in your python app import your python file you have created, for example
```
from yourfile import Whitelist, Settings

db = Whitelist()
find = db.where('discord').equals('value').first()
if find:
  find.whitelisted = False
  find.save() # update
else:
  db.discord = 'value'
  db.whitelisted = False
  db.save() # insert new.
```
for more info look at: https://github.com/omar-othmann/DevSqlite3
