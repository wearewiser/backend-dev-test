![Alt Wiser](https://wearewiser.com/assets/images/wiser-logo/wiser-purple.svg)

# Backend Developer Test

## About This Test

This test is for a backend developer position with Wiser. There are --- parts to this test. Fork this test to provide solutions. You'll find labeled directories in this repository corresponding to each part of the test. When complete, email a repository link to ---.

Any required content will be provided in the `material` directory. Please create and put your answers in a `solution` directory. Create a new branch `part(x)` for each part of the test. Package dependencies for each part should be installed separately in each `solution` directory.

Please commit your answers regularly. There is no time limit, though we will be looking at the commit metrics. We will be looking for DRY code and good coding practices. Include a README in each `solution` directory. Please include BDD tests - bonus marks for code coverage reporting.

One more thing! Please write your server code using [TypeScript Node](https://www.npmjs.com/package/ts-node).

## The Test

### Part 1

The directory `material` contains a simple HTML file. The file makes an AJAX request to a server. Open the file in Google Chrome and you'll notice that the request fails. You do not have access to the server. The server endpoint is [http://dev-test.madebywiser.com/part1](http://dev-test.madebywiser.com/part1), and is defined in a JavaScript variable called `api_address`. You're tasked with ensuring that the client code can access the API content from the provided server endpoint.

> **Note**: _before starting, feel free to ensure the server is operational by running something similar to the following UNIX command:_

`$ curl -X GET http://dev-test.madebywiser.com/part1`

### Part 2

The directory `material` contains an HTML file. The file has an input[type:number] and a button. The user is expected to enter a number `x` into the input, and when the button is clicked it makes a GET request to `<proto>://<your-api><path>/:x` asynchronously and waits for the server's response before rendering the server's response into the view.

For a given value `x`, the server should return a value corresponding the the rules in the table below:

| x%3!=0 && x%5!=0 | x%3==0 | x%5==0 | x%3==0 && x%5==0 |
|:----------------:|:------:|:------:|:----------------:|
| x                | Fizz   | Buzz   | FizzBuzz         |

The HTML file has a variable `api_address`. You can configure this variable to your local development environment so you can view the results in your browser.

### Part 3

The directory `material` contains an HTML document similar to the one in [Part 2](#part-2). You're now required to extend your answer from [Part 2](#part-2). In addition to following the rules for [Part 2](#part-2), the server should concatenate a special word to the suffix of the response iff the GET url parameter x is divisible by 7.

In order to access the special word, your server will need to access the API at [http://dev-test.madebywiser.com/part3/:x](http://dev-test.madebywiser.com/part3/7). The special word will be returned in the following format:

```json
{
	"value":"<special word>"
}
```

Please note that you will need to authenticate in order to get a response from the server. The server uses _Basic Authorization_. Use the following credentials:

| username | password |
|:--------:|:--------:|
| wiserdev | password |

> **Note**: _before starting, feel free to ensure the server is operational by running something similar to the following UNIX command:_

`$ curl -X GET http://dev-test.madebywiser.com/part3/7777 --user wiserdev:password`