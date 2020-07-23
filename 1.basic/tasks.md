#### write commands for following mongodb opertaions

1. create a database named `sports`
// Answer here ..
use sports

2. list all databases present in local mongod server.
// Answer here..
show dbs

3. create 3 collections named `cricket`, `football`, `TT` in sports database.
db.createCollection('cricket')
db.createCollection('football')
db.createCollection('TT')


4. add 3 players in each of above collections which should have fields like `name`, `age`, `email`, state and auction_price.
db.cricket.insertMany([{name:"Karan",age:"29",email:"abc@gmail.com",state:"maharashtra",auction_price:10},
{name:"Poachie",age:"28",email:"abc@gmail.com",state:"delhi",auction_price:11},
{name:"Panther",age:"27",email:"abc@gmail.com",state:"chandigarh",auction_price:12}])

db.football.insertMany([{name:"Ed",age:"29",email:"abc@gmail.com",state:"maharashtra",auction_price:10},
{name:"Edd",age:"28",email:"abc@gmail.com",state:"delhi",auction_price:11},
{name:"Eddy",age:"27",email:"abc@gmail.com",state:"chandigarh",auction_price:12}])

db.TT.insertMany([{name:"Amar",age:"29",email:"abc@gmail.com",state:"maharashtra",auction_price:10},
{name:"Akbar",age:"28",email:"abc@gmail.com",state:"delhi",auction_price:11},
{name:"Anthony",age:"27",email:"abc@gmail.com",state:"chandigarh",auction_price:12}])

5. list all collections in sports database.
db.cricket.find()
db.football.find()
db.TT.find()


6. rename `TT` collection to `tennis`.
db.TT.renameCollection("tt")


7. create a capped collection called `khokho` which should have max 3 documents.
  Try inserting more than 3 and output the result here ?

db.createCollection("khokho",{capped:true, size:100000 ,max:3})

db.khokho.insertMany([{name:"Amar",age:"29",email:"abc@gmail.com",state:"maharashtra",auction_price:10},
{name:"Akbar",age:"28",email:"abc@gmail.com",state:"delhi",auction_price:11},
{name:"Poachie",age:"28",email:"abc@gmail.com",state:"delhi",auction_price:11},
{name:"Anthony",age:"27",email:"abc@gmail.com",state:"chandigarh",auction_price:12}])

//When I add more than three, the top entries are getting deleted to allocate the new ones

8. check whether a collection is capped or not?
db.khokho.isCapped()

9. remove all documents from `football` collection.
db.football.deleteMany({})

10. delete cricket collection completely.
db.cricket.drop()

11. rename database sports to games

12. delete sports database. 
db.dropDatabase()