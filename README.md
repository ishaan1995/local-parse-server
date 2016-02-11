# local-parse-server
Own Parse-server that runs on node.js

### For Local Development

* Make sure you have at least Node 4.1. `node --version`
* Clone this repo and change directory to it.
* install npm package express --> sudo npm install express --save.
* install npm package parse-server --> sudo npm install parse-server.
* `npm install`
* Install mongo locally using http://docs.mongodb.org/master/tutorial/install-mongodb-on-os-x/
* Run `mongo` to connect to your database, just to make sure it's working. Once you see a mongo prompt, exit with Control-D
* Run the server with: `npm start`
* By default it will use a path of /parse for the API routes.  To change this, or use older client SDKs, run `export PARSE_MOUNT=/1` before launching the server.
* You now have a database named "dev" that contains your Parse data


### Using it

You can use the REST API, the JavaScript SDK, and any of our open-source SDKs:

Example request to a server running locally:

```
curl -X POST \
  -H "X-Parse-Application-Id: myAppId" \
  -H "Content-Type: application/json" \
  -d '{"score":1337,"playerName":"Sean Plott","cheatMode":false}' \
  http://localhost:1337/parse/classes/GameScore
  
curl -X POST \
  -H "X-Parse-Application-Id: myAppId" \
  -H "Content-Type: application/json" \
  -d '{}' \
  http://localhost:1337/parse/functions/hello
```

For Android Studio integration:

```
Parse.initialize(new Parse.Configuration.Builder(getApplicationContext())
                        .applicationId("your_app_id")

                        .server("your_local-server_url")

                        .build()

        );





