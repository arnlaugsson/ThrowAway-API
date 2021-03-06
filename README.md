# Throwaway API - for anything and nothing
a [Sails][sails] application.

This App exposes two models, through an CRUD API
(no authentication, no hassle). The existing models are called `games` and
`misc`. They have no predefined attributes and can be used as needed.

![ThrowAwayAPI](assets/images/trash.png)

### Table of Contents
1. [How to setup and run locally.](#local)
2. [Deploy to Heroku](#heroku)
3. [CRUD operations](#crud)

## <a name="local"></a>How to use locally
This assumes you have installed [Sails][sails], but if you don't; run:

`npm install -g sails`

1. In the project's directory, start the application:

    `sails lift`

2. You will be asked how to deal with migrations, for throwaway data, it
shouldn't matter, just enter `1`.
3. The App should now be running locally on port 1337, head over to
[the App][app]

## <a name="deploy"></a>Deploy an instance to Heroku
This assumes you have installed [Heroku's CLI][heroku-cli], and that you are
logged into your account.

1. In the project's directory, create an Heroku App:

    `heroku apps:create`

2. Deploy the project as the App:

    `git push heroku master`

3. Open the App for inspection:

    `heroku open`

4. That's it. Happy prototyping.
5. Data is cleared out on Heroku sleep for the App.

## <a name="crud"></a>Create, Read, Update and Delete
Assuming you are running locally, otherwise swap out `http://localhost:1337`
for whatever URL your deployed Heroku version is running on.

### View list
GET [http://localhost:1137/misc](http://localhost:1337/misc)

Using cUrl:

```
curl -X GET -H "Content-Type: application/json" "http://localhost:1337/misc/"
```

### View single (by ID)
GET [http://localhost:1137/misc/ID/](http://localhost:1337/misc/ID/)

Using cUrl:

```
curl -X GET -H "Content-Type: application/json" "http://localhost:1337/misc/ID/"
```

### Create
POST `http://localhost:1337/misc/create/?someAttribute=whatever`

```
curl -X POST -H "Content-Type: application/json" -d '{ "someKey": "someValue" }' "http://localhost:1337/misc/create"
```

### Update existing (by ID)
PATCH `http://localhost:1337/misc/update/ID/?newAttr=someValue`

Using cUrl:

```
curl -X PATCH -H "Content-Type: application/json" -d '{ "silly": "LoveSongs" }' "http://localhost:1337/misc/update/ID"
```

### Delete existing (by ID)
DELETE `http://localhost:1337/misc/ID`

Using cUrl:

```
curl -X DELETE "http://localhost:1337/misc/update/ID"
```

[sails]: http://sailsjs.or
[heroku-cli]: https://devcenter.heroku.com/articles/heroku-cli
[app]: http://localhost:1337
