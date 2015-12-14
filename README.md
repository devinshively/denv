# `dotenv command line script`
============
Use to run a command with environment variables from your .env file.

## Installation
    bash <(curl -s --no-sessionid https://raw.githubusercontent.com/devinshively/dotenv/master/install)

## Example usage
```
    dotenv yourcommmand arg1 arg2

    $ cat .env
	# This is an example .env file
	MY_ENV_VAR=test 	
	ACCESS_KEY=access-key
	SECRET_KEY=super-secret # This is super secret ok

	$ cat ./test.sh
	echo "MY_ENV_VAR: $MY_ENV_VAR"
	echo "ACCESS_KEY: $ACCESS_KEY"
	echo "SECRET_KEY: $SECRET_KEY"

	$ ./test.sh
	MY_ENV_VAR:
	ACCESS_KEY:
	SECRET_KEY:

	$ ./dotenv ./test.sh
	MY_ENV_VAR: test
	ACCESS_KEY: access-key
	SECRET_KEY: super-secret

```