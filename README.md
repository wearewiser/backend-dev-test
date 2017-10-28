![Alt Wiser](https://wearewiser.com/assets/images/wiser-logo/wiser-purple.svg)

# Backend Developer Test

## About This Test

This test is for a backend developer position with Wiser. There are --- parts to this test. Fork this test, and provide the answers in ---. You'll find labeled directories in this repository corresponding to each question.

Any required content will be provided in the `---` directory. Please put your answers in the `---` directory.

Please commit your answers regularily. There is no time limit, though we will be looking at the commit metrics. We will be looking for DRY code and good coding practices. Include a README in each `---` directory. Please include BDD tests - bonus marks for code coverage reporting.

## The Test

### Part 1

The directory --- contains a simple HTML file. The file makes an AJAX request to a server. Open the file in Google Chrome and you'll notice that the request fails. You do not have access to the server. The server endpoint is ---. You're tasked with ensuring that the client code can access the API content at the provided server endpoint.

**Note**: _before starting, feel free to ensure the server is operational by running something similar to the following UNIX command:_

`$ curl -X GET https://---`

### Part 2

The directory --- contains an HTML file. The file has an input[type:number] and a button. The user is expected to enter a number into the input, and when the button is clicked it should POST that number asynchronously and wait for the server's response before rendering the response into the view.

For a given value `x`, the server should return a value corresponding the the rules in the table below:

| x%3!=0 && x%5!=0 | x%3==0 | x%5==0 | x%3==0 && x%5==0 |
|:----------------:|:------:|:------:|:----------------:|
| x                | Fizz   | Buzz   | FizzBuzz         |

The HTML file has two variables named `host` and `port`. When configured, they should communicate with a server to at the specified address. You can configure these values to your local development environment so you can view the results in your browser.
