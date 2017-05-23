TODO API!
=========

You love your Todo demos. Now you have an API to throw in the mix like a
grown up.

Find it on heroku (for now) at [http://high-robot-9464.herokuapp.com/][u]

RESTful API
===========

POST /lists
-----------

Creates a new lists.

### body

```javascript
{
  list: {
    name: <name>
  }
}
```

### response

```javascript
{
  list: {
    id: <id>,
    name: <name>
  }
}
```

### notes

All lists are public and destroyed when the server is restarted, or after a week.

GET /lists/:list_id
------------------

Gets a list by ID with embedded items.

### response

```javascript
{
  list: {
    id: <id>,
    name: <name>,
    items: [item]
  }
}
```

POST /items
-----------

Creates an item in a list.

### body

```javascript
{
  item: {
    list_id: <list_id>,
    description: <description>
  }
}
```

### response

```javascript
{
  item: {
    id: <id>,
    description: <description>
    complete: <true/false>
    ...
  }
}
```

DELETE /items/:item_id
----------------------

Removes a list item.

### response

```javascript
'item deleted'
```
