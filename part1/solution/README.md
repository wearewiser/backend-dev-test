![Alt Wiser](https://wearewiser.com/assets/images/wiser-logo/wiser-purple.svg)

# Backend Developer Test | Part 1

## Solution

1. Create a web service that will serve as proxy web application when requesting `http://dev-test.madebywiser.com/part1` url.
 
```
$ cd /part1/solution/typescript-node-api-01
```

```
$ npm install request
```
 
```
...
    let router = express.Router();

    let requestUrl = 'http://dev-test.madebywiser.com/part1';

    router.get('/0000/part1/', (req, res, next) => {

      request(requestUrl', function (error, response, body) {
        if (!error && response.statusCode === 200) {
          //console.log(body);
          res.json(JSON.parse(body));
        } else {
          res.json(error);
        }

      });
    });
...
```

2. Run the proxy web service on your local/staging server.
```
# Staging
https://raed.ph/0000/part1/
```

3. Use the local/staging url in the `api_address` variable.

4. See [Working Demo](https://raed.ph/0000/index-part01.html)

```
DISCLAIMER.

NGINX reverse proxy configuration, API development were not discussed here.

```

```
/part1/solution/typescript-node-api-01 is where the proxy web service code resides.
```