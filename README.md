
# pythonmongo
Python MongoDB Cheat Sheet

Source: https://www.w3schools.com/python/python_mongodb_getstarted.asp

## How to dev

### Linux
```bash
git clone https://github.com/dssantos/pythonmongo.git pythonmongo
cd pythonmongo
python -m venv .pythonmongo
source .pythonmongo/bin/activate
python -m pip install -U pip
pip install -r requirements.txt

```

### Windows
```bash
git clone https://github.com/dssantos/pythonmongo.git pythonmongo
cd pythonmongo
python -m venv .pythonmongo
Set-ExecutionPolicy Unrestricted -Scope Process -force
./.pythonmongo/Scripts/activate
python -m pip install -U pip
pip install -r requirements.txt

```

### Cheat SHeet
```bash
# Create database
import pymongo
myclient = pymongo.MongoClient("mongodb://localhost:27017/")
mydb = myclient["mydatabase"]

# Create collection
import pymongo
myclient = pymongo.MongoClient("mongodb://localhost:27017/")
mydb = myclient["mydatabase"]
mycol = mydb["customers"]

# Insert
mydict = { "name": "John", "address": "Highway 37" }
x = mycol.insert_one(mydict)

# Find First
x = mycol.find_one()
print(x)

# Find All
for x in mycol.find():
  print(x)

# Query
myquery = { "address": "Park Lane 38" }
mydoc = mycol.find(myquery)
for x in mydoc:
  print(x)

# Query advanced
myquery = { "address": { "$gt": "S" } }
mydoc = mycol.find(myquery)
for x in mydoc:
  print(x)

# Query with regex
myquery = { "address": { "$regex": "^S" } }
mydoc = mycol.find(myquery)
for x in mydoc:
  print(x)

# Sort
mydoc = mycol.find().sort("name")
for x in mydoc:
  print(x)

# Sort descending
mydoc = mycol.find().sort("name", -1)
for x in mydoc:
  print(x)

# Update
myquery = { "address": "Valley 345" }
newvalues = { "$set": { "address": "Canyon 123" } }
mycol.update_one(myquery, newvalues)
for x in mycol.find():
  print(x)

# Delete
myquery = { "address": "Mountain 21" }
mycol.delete_one(myquery)

```
