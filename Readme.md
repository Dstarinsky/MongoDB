* Open terminal and run mongo server with the command:
```
mongod
```
* Open new terminal window and run the command:
```
mongo
```
* run the command:
```
use mongo_practice
```
* create collection called movies:
```
db.createCollection("movies")
```
* insert to the collection the movies:
```
db.movies.insert([
{
    title:"Fight Club",
    writer:"Chuck Palahniuk",
    year:1999,
    actors:[
            "Brad Pitt",
            "Edward Norton"
    ]
},
{
    title:"Pulp Fiction",
    writer:"Quentin Tarantino",
    year:1994,
    actors:[
            "John Travolta",
            "Uma Thurman"
    ]
},
{
    title:"Inglorious Basterds",
    writer:"Quentin Tarantino",
    year:2009,
    actors:[
            "Brad Pitt",
            "Diane Kruger",
            "Eli Roth"
    ]
},
{
    title:"The Hobbit: An Unexpected Journey",
    writer:"J.R.R. Tolkein",
    year:2012,
    franchise:"The Hobbit"
},
{
    title:"The Hobbit: The Desolation of Smaug",
    writer:"J.R.R. Tolkein",
    year:2013,
    franchise:"The Hobbit"
},
{
    title:"The Hobbit: The Battle of the Five Armies",
    writer:"J.R.R. Tolkein",
    year:2012,
    franchise:"The Hobbit",
    synopsis:"Bilbo and Company are forced to engage in a war against an array of combatants and keep the Lonely Mountain from falling into the hands of a rising darkness."
},
{
    title:"Pee Wee Herman's Big Adventure"
},
{
    title:"Avatar"
}])
```
* queies:
```
db.movies.find()
db.movies.find({writer:{$eq:"Quentin Tarantino"}})
db.movies.find({actors:{$eq:"Brad Pitt"}})
db.movies.find({franchise:{$eq:"The Hobbit"}})
db.movies.find({year:{$gte:1990, $lt:2000}})
db.movies.find({$or:[{year:{$lte:2000}},{year:{$gte:2010}}]})
db.movies.remove({title:"Pee Wee Herman's Big Adventure"})
db.movies.remove({title:"Avatar"})
```
* Relationships:
```
db.createCollection("users")
db.users.insert([
{
    username:"GoodGuyGreg",
    first_name:"Good Guy",
    last_name :"Greg"
},
{
    username:"ScumbagSteve",
    first_name:"Scumbag",
    last_name:"Steve"
}])
db.createCollection("posts")
db.posts.insert([
{
    username:"GoodGuyGreg",
    title:"Passes out at party",
    body:"Wakes up early and cleans house"
},
{
    username:"GoodGuyGreg",
    title:"Steals your identity",
    body:"Raises your credit score"
},
{
    username:"GoodGuyGreg",
    title:"Reports a bug in your code",
    body:"Sends you a Pull Request"
},
{
    username:"ScumbagSteve",
    title:"Borrows something",
    body:"Sells it"
},
{
    username:"ScumbagSteve",
    title:"Borrows everything",
    body:"The end"
},
{
    username:"ScumbagSteve",
    title:"Forks your repo on github",
    body:"Sets to private"
}])
```
* queries:
```
db.users.find()
db.posts.find()
db.users.aggregate([
  {
    "$match": {
      "last_name": "Greg"
    }
  },
  {
    "$lookup": {
      "from": "posts",
      "localField": "username",
      "foreignField": "username",
      "as": "posts"
    }
  },
  {
    "$project": {
      posts: 1
    }
  }
])
db.users.aggregate([
  {
    "$match": {
      "last_name": "Steve"
    }
  },
  {
    "$lookup": {
      "from": "posts",
      "localField": "username",
      "foreignField": "username",
      "as": "posts"
    }
  },
  {
    "$project": {
      posts: 1
    }
  }
])
```

