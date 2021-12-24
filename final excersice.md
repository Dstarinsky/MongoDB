# MongoDB Practice

MongoDB Exercise in mongo shell

Connect to a running mongo instance, use a database named `mongo_practice`.

## Insert Documents

Insert the following documents into a `movies` collection.

```
title : Fight Club
writer : Chuck Palahniuk
year : 1999
actors : [
  Brad Pitt
  Edward Norton
]
```
```
title : Pulp Fiction
writer : Quentin Tarantino
year : 1994
actors : [
  John Travolta
  Uma Thurman
]
```
```
title : Inglorious Basterds
writer : Quentin Tarantino
year : 2009
actors : [
  Brad Pitt
  Diane Kruger
  Eli Roth
]
```
```
title : The Hobbit: An Unexpected Journey
writer : J.R.R. Tolkein
year : 2012
franchise : The Hobbit
```
```
title : The Hobbit: The Desolation of Smaug
writer : J.R.R. Tolkein
year : 2013
franchise : The Hobbit
```
```
title : The Hobbit: The Battle of the Five Armies
writer : J.R.R. Tolkein
year : 2012
franchise : The Hobbit
synopsis : Bilbo and Company are forced to engage in a war against an array of combatants and keep the Lonely Mountain from falling into the hands of a rising darkness.
```
```
title : Pee Wee Herman's Big Adventure
```
```
title : Avatar
```

## Query / Find Documents

query the `movies` collection to

1. get all documents
1. get all documents with `writer` set to "Quentin Tarantino"
1. get all documents where `actors` include "Brad Pitt"
1. get all documents with `franchise` set to "The Hobbit"
1. get all movies released in the 90s
1. get all movies released before the year 2000 or after 2010

## Update Documents

1. add a synopsis to "The Hobbit: An Unexpected Journey" : "A reluctant hobbit, Bilbo Baggins, sets out to the Lonely Mountain with a spirited group of dwarves to reclaim their mountain home - and the gold within it - from the dragon Smaug."
1. add a synopsis to "The Hobbit: The Desolation of Smaug" : "The dwarves, along with Bilbo Baggins and Gandalf the Grey, continue their quest to reclaim Erebor, their homeland, from Smaug."


## Delete Documents

1. delete the movie "Pee Wee Herman's Big Adventure"
1. delete the movie "Avatar"

## Relationships

### Insert the following documents into a `users` collection

```
username : GoodGuyGreg
first_name : "Good Guy"
last_name : "Greg"
```
```
username : ScumbagSteve
first_name : "Scumbag"
last_name : "Steve"
```

### Insert the following documents into a `posts` collection

```
username : GoodGuyGreg
title : Passes out at party
body : Wakes up early and cleans house
```

```
username : GoodGuyGreg
title : Steals your identity
body : Raises your credit score
```

```
username : GoodGuyGreg
title : Reports a bug in your code
body : Sends you a Pull Request
```
```
username : ScumbagSteve
title : Borrows something
body : Sells it
```

```
username : ScumbagSteve
title : Borrows everything
body : The end
```

```
username : ScumbagSteve
title : Forks your repo on github
body : Sets to private
```

## Querying related collections

1. find all users
1. find all posts
1. find all posts that was authored by user with last name `Greg`
1. find all posts that was authored by user with last name `Steve`
