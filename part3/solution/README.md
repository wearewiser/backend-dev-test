![Alt Wiser](https://wearewiser.com/assets/images/wiser-logo/wiser-purple.svg)

# Backend Developer Test | Part 3

## Solution

1. Create a web service that will handle business logic required.
 
```
$ cd /part3/solution/typescript-node-api-03
```
 
```
...
...
  // Configure Express middleware.
  private middleware(): void {
    this.express.use(logger('dev'));
    this.express.use(bodyParser.json());
    this.express.use(bodyParser.urlencoded({ extended: false }));
    this.express.use((req, res, next) => {
      res.setHeader('Access-Control-Allow-Origin', 'null');
      res.setHeader('Access-Control-Allow-Headers', 'Authorization');
      next();
    });
  }

  // Configure API endpoints.
  private routes(): void {

      let router = express.Router();

      let auth = basicAuth({
            users: { 'wiserdev': 'password' }
      });

      router.get('/0000/part3/:x', auth, (req, res, next) => {

      let x = req.params.x;

      let result;

      if(x%3==0) {
        result = 'Fizz';
      } else if(x%5==0) {
        result = 'Buzz';
      } else if(x%7==0) {
        result = 'vaingloriously';
      } else if(x%3==0 && x%5==0) {
        result = 'FizzBuzz';
      } else if(x%3!=0 && x%5!=0) {
        result = x;
      }

      res.json({
        value: result
      });
    });

    this.express.use('/', router);
  }
...
...
```

2. Run the proxy web service on your local/staging server.
```
# Staging
https://raed.ph/0000/part3/:x
```

3. Use the local/staging url in the `api_address` variable.

4. See [Working Demo](https://raed.ph/0000/index-part03.html)

```
DISCLAIMER.

NGINX reverse proxy configuration, API development were not discussed here.

```

```
/part2/solution/typescript-node-api-03
```