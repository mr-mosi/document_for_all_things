## Mongo notes

- intalling is little tricky and exist in internet.
- `show dbs` shows all data bases.
- `use [db name]` use a data base or if not exist create it.
- to create user: `db.createUser({user:'[user_name]', pwd:'[password]', roles:["readWrite", "dbAdmin", "some th else"]})`
- in mongo we have no table but instead of table we have collections that is similar to table.
- to create collections use this command`db.createClollection('[collection_name]')`.
- `show collections` shows all collections in the data base.
- to insert into a collection this command will help `db.collection_name.insert({attr:"value",...});`
- `db.collection_name.find()` shows all items in a collection.
- we can add several item by using insert instruction with set of item in this way `... .inset([{attr:"value",...}, {attr:"value",...}, ...)`.
- to show collection items in better way we can use this pretty option in this way `db.collection_name.find().prtty()`.
- using `db.collection_name.remove({})` to delete the entire collection.
- using `db.dropDatabase()` to remove the Database. 