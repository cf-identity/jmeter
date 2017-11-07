# jmeter
repo for jmeter scripts to demonstrate jmeter capabilities

# setup
This repository has everything, with the exception for Java VM,  you need to run Apache Jmeter
We use `.envrc` to automatically configure your path. If you do not use [direnv](https://github.com/direnv/direnv) you have to run the command

    source .envrc
    
Verify that jmeter is on your path by typing `which jmeter`

# performance tests

## Authorization Code Flow

### prerequisites
Our load test assumes that the user has already approved necessary scopes. The load test just test the login/authorize actions.
1. launch UAA in a separate window using the command `./gradlew run`
1. Go to the [sample app](http://localhost:8080/app)
1. Login using `marissa/koala` and accept all scopes

### launch jmeter

    jmeter -t uaa/simple-auth-code-test.jmx

Press the `Play` button or use the menu Run->Start to launch the test

## Client Credentials Flow

### prerequisites
UAA is up and running and has the `admin` client with the password `adminsecret`

### launch jmeter

     jmeter -t uaa/simple-client-credentials.jmx
