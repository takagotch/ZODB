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

import persistent
import persistent.list

class Book(persistent.Persistent):
  def __init__(self, title):
    self.title = title
    self.authors = persistent.list.PersistentList()
    
  def add_author(self, author):
    self.authors.append(author)

import persistent
from BTrees.OOTree import TreeSet

class Book(persistent.Persistent):
  def __init__(self, title):
    self.title = title
    self.authors = TreeSet()
    
  def add_author(self, author):
    self.authors.add(author)

class Book(persistent.Persistent):
  publisher = 'UNKNOWN'
  
  def __init__(self, title, publisher):
    self.title = title
    self.publisher = publisher
    self.authors = TreeSet()
    
  def add_author(self, author):
    self.authors.add(author)

from catalog import Publication as Book


book = Book("ZODB")
connection = ZODB.connection(None)
connection.add(book)
book._p_changed, bool(book._p_oid), book._p_serial == z64

import transaction
transaction.commit()
book._p_changed, bool(book._p_oid), book._p_serial == z64

book._p_changed = None
book._p_changed, bool(book._p_oid)


class BookEq(persistent.Persistent):
  def __init__(self, title):
    self.title = title
    self.authors = ()
  
  def add_author(self, author):
    self.authors += (author, )
    
  def __eq__(self, other):
    return self.title == other.title and self.authors == other.authors
   
  def __hash__(self):
    return hash((self.title, self.authors))


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


