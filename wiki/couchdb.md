# couchdb

## docker
connect two containers easily: `docker run --name my-couchdb-app --link my-couchdb:couchdb -d app-that-uses-couchdbd`

## API

Create Database: `PUT http://admin:password@127.0.0.1:5984/dbname`
Delete DB: `DELETE  http://admin:password@127.0.0.1:5984/dbname`

Create Document: `PUT http://admin:password@127.0.0.1:5984/dbname/6e1295ed6c29495e54cc05947f18c8af -d '{"title":"There is Nothing Left to Lose","artist":"Foo Fighters"}'`
Retrieve a Document: `GET http://admin:password@127.0.0.1:5984/albums/6e1295ed6c29495e54cc05947f18c8af`
Modify Document: 
   - _If you want to change a document in CouchDB, you don’t tell it to go and find a field in a specific document and insert a new value. Instead, you load the full document out of CouchDB, make your changes in the JSON structure (or object, when you are doing actual programming), and save the entire new revision (or version) of that document back into CouchDB. Each revision is identified by a new rev value_
   - `PUT http://admin:password@127.0.0.1:5984/albums/6e1295ed6c29495e54cc05947f18c8af \`
     `-d '{"_rev":"1-2902191555","title":"There is Nothing Left to Lose","artist":"Foo Fighters","year":"1997"}'`
   
   

