# apimation-cli-client

### Get latest binary:
[Download](https://github.com/dlocmelis/apimation-cli-client/releases/latest)

### Alternatively build from source:
`go get -u`
`go build`

##### First usage of apiamation-cli-client with existing apimation account:
##
0. It is recommended to create an alias for cli client, like in this example:
```
alias apimation="/Users/dlocmelis/Apimation/apimation-cli-client"
!NB The path to cli client will be different
```
1. Go to a directory reserved for the tests
2. Copy apimation test structure from [apimation-demo template](https://github.com/dlocmelis/apimation-docs/tree/master/apimationDemo)
3. Delete old clientToken file and create a new client auth token (it will be linked to your project):
```
  apimation token create --project <projectName>
  # --project flag is optional and is needed only if account has more than one project
```
4. Create new YAML test asset files based on [Apimation YAML test documentation](https://github.com/dlocmelis/apimation-docs/blob/master/docs/yaml-tests.md)
5. Start test engine worker
```
# To start the worker you'll need worker access token, contact support@apimation.com
  # Get project id from assets show command
  apimation assets show

  # Start the worker when worker access token is acquired
  apimation worker start
```
6. Deploy test assets to apimation cloud
```
  apimation deploy
```
7. Execute test sets and load scenarios based on run command:
```
  apimation run -h
  apimation run case "Case 1" --environment Staging
  apimation run set "Smoke set" --environment Staging
  apimation run load simulation_test1
  ...
```

##### Account creation and first project setup:
##
0. It is recommended to create an alias for cli client, like in this example:
```
alias apimation="/Users/dlocmelis/Apimation/apimation-cli-client"
!NB The path to cli client will be different
```
1. Go to a directory reserved for the tests and execute:
```
  apimation user create --email test@testuser.com --project TestProject
  cd TestProject
```
2. Create new YAML test asset files based on [Apimation YAML test documentation](https://github.com/dlocmelis/apimation-docs/blob/master/docs/yaml-tests.md)
3. Start test engine worker
```
# To start the worker you'll need worker access token, contact support@apimation.com
  # Get project id from assets show command
  apimation assets show

  # Start the worker when worker access token is acquired
  apimation worker start
```
4. Deploy test assets to apimation cloud
```
  apimation deploy
```
5. Execute test sets and load scenarios based on run command:
```
  apimation run -h
  apimation run case "Case 1" --environment Staging
  apimation run set "Smoke set" --environment Staging
  apimation run load simulation_test1
```

##### General help:
##
```
  apimation -h
```