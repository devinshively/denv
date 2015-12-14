# `dotenv command line script`
Used to run a command with environment variables loaded from the .env file in your current working directory. This script was inspired by bkeepers [dotenv](https://github.com/bkeepers/dotenv) ruby gem. 

Storing [configuration in the environment](http://12factor.net/config) is one of the tenets of a [twelve-factor app](http://12factor.net). Anything that is likely to change between deployment environments–such as resource handles for databases or credentials for external services–should be extracted from the code into environment variables.

But it is not always practical to set environment variables on development machines or continuous integration servers where multiple projects are run. denv loads variables from a `.env` file into `ENV`.

## Installation
    bash <(curl -s --no-sessionid https://raw.githubusercontent.com/devinshively/denv/master/install)

## Example usage
```
    denv yourcommmand arg1 arg2

    $ cat .env
	# This is an example .env file
	CUSTOM_VAR=test 	
	CLIENT_KEY=client-key
	SECRET_KEY=top-secret # This is top secret ok

	$ cat ./test.sh
	echo "CUSTOM_VAR: $CUSTOM_VAR"
	echo "CLIENT_KEY: $CLIENT_KEY"
	echo "SECRET_KEY: $SECRET_KEY"

	$ ./test.sh
	CUSTOM_VAR:
	CLIENT_KEY:
	SECRET_KEY:

	$ denv ./test.sh
	CUSTOM_VAR: test
	CLIENT_KEY: client-key
	SECRET_KEY: top-secret

```