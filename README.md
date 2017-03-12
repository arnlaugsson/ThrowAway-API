# Throwaway API - for anything and nothing
a [Sails][sails] application. This App exposes two models, through an CRUD API
(no authentication, no hassle). The existing models are called `games` and
`misc`. They have no predefined attributes and can be used as needed.


## How to use locally
This assumes you have installed [Sails][sails].

1. In the project's directory, start the application:

    sails lift

2. You will be asked how to deal with migrations, for throwaway data, it
shouldn't matter, just enter `1`.
3. The App should now be running locally on port 1337, head over to
[the App][app]
4. Both of the models are exposed:
    - [http://localhost:1337/games][http://localhost:1337/games]
    - [http://localhost:1137/misc][http://localhost:1337/misc]
5. To create an instance of either send a POST request to:
    - `http://localhost:1337/MODEL/create/?someAttribute=whatever`
6. To update:
    - `http://localhost:1337/MODEL/update/1/?someAttribute=somethingElse`
7. To delete:
    - `http://localhost:1337/MODEL/destroy/1/`


## Deploy an instance to Heroku
This assumes you have installed [Heroku's CLI][heroku-cli], and that you are
logged into your account.

1. In the project's directory, create an Heroku App:

    heroku apps:create

2. Deploy the project as the App:

    git push heroku master

3. Open the App for inspection:

    heroku open

4. That's it. Happy prototyping.

[sails]: http://sailsjs.or
[heroku-cli]: https://devcenter.heroku.com/articles/heroku-cli
[app]: http://localhost:1337
