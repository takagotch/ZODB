### zodb
---
http://www.zodb.org/en/latest/

```py
import persistent

class Book(persistent.Persistent):
  def __init__(self, title):
    self.title = title
    self.authors = ()
    
  def add_author(self, author):
    self.authors += (author, )

import persistent
import persistent.list

class Book(persistent.Persistent):
  def __init__(self, title):
    self.title = title
    self.authors = persistent.list.PersistentList()
    
  def add_authors(self, author):
    self.authors.append(author)








conn = db.open()

with db.transaction() as connection:
  connection.root.foo = 1
  
root = conn.root()
root
root['foo']

conn.root.foo

import persistent

class Book(persistent.Persistent):
  def __init__(self, title):
    self.title = title
    self.authors = []
    
  def add_author(self, author):
    self.authors.append(author)
    self._p_changed = True
```

```
```

```
```


