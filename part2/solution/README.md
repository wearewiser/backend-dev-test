![Alt Wiser](https://wearewiser.com/assets/images/wiser-logo/wiser-purple.svg)

# Backend Developer Test | Part 2

## Solution

1. Create a web service that will handle business logic required.
 
```
$ cd /part2/solution/typescript-node-api-02
```
 
```
...
...
    let router = express.Router();

    router.get('/0000/part2/:x', (req, res, next) => {

      let x = req.params.x;

      let result;

      if(x%3==0) {
        result = 'Fizz';
      } else if(x%5==0) {
        result = 'Buzz';
      } else if(x%3==0 && x%5==0) {
        result = 'FizzBuzz';
      } else if(x%3!=0 && x%5!=0) {
        result = x;
      }

      res.json({
        value: result
      });
    });
...
...
```

2. Run the proxy web service on your local/staging server.
```
# Staging
https://raed.ph/0000/part2/:x
```

3. Use the local/staging url in the `api_address` variable.

4. See [Working Demo](https://raed.ph/0000/index-part02.html)

```
DISCLAIMER.

NGINX reverse proxy configuration, API development were not discussed here.

```

```
/part2/solution/typescript-node-api-02
```