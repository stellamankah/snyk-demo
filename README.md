# Snyk scan demo

## Steps

### Snyk-repository
 - Created snyk-demo repository
 - Created React Web Application using `create-react-app` in VS Code
 - Within repository, created Circle CI integration (using .circleci\config.yml) as below

``` 
version: '2.1'
orbs:
  snyk: snyk/snyk@1.1.1
jobs:
  build:
    docker:
      - image: 'cimg/node:lts'
    steps:
      - checkout
      - run: npm ci
      - snyk/scan
workflows: null
```
 - Within the config.yml file, added orb and steps to scan the project using snyk/scan

### Snyk
 - Created a snyk account
 - Copied snyk Auth Token from the snyk settings page

### Circle CI
 - Create CircleCI project for repository above
 - Updated CircleCI organizational settings to allow uncertified Orbs
 - Added project Environmental Variable SNYK_AUTH with the organizational ID copied from the snyk settings page


**Bringing It All To Life**

 - Update and commit any code to the repository
 - Watch snyk scan the repository code and dependencies
 
 
More About React APP 

See the section about [deployment](https://facebook.github.io/create-react-app/docs/deployment) for more information.

You can learn more in the [Create React App documentation](https://facebook.github.io/create-react-app/docs/getting-started).

To learn React, check out the [React documentation](https://reactjs.org/).


