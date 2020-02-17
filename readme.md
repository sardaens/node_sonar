# Sonar With Node JS

Client : sonar-scanner
Server: sonarQube server

Create a file sonar-project.properties in the root's directory of the src app.
Example :

> #required metdata
sonar.projectKey=node-test-app
sonar.projectVersion=1.0
sonar.sourceEncoding=UTF-8
> #sonar.language=js
> sonar.eslint.eslintconfigpath=app/eslintrc.json
>
> #path to srouce directories
> sonar.sources=app
> #sonar.tests=app/test/integration/api/

> #excludes
> sonar.exclusions=app/node_modules/*,app/coverage/lcov-r> report/*,app/test/integration/api/v1/*,app/middlewares/common-middleware.js

> #coverage reporting
> #sonar.javascript.lcov.reportPaths=app/coverage/lcov.info
> #sonar.surefire.reportPaths=app/coverage/lcov-report


## With Docker

- Run Server SonarQube :
> docker run -d --name sonarqube -p 9000:9000 sonarqube

- Run sonar-scanner (client side)
> C:\dev\tools\sonar-scanner-4.2.0.1873-windows\bin\sonar-scanner -Dsonar.host.url=http://192.168.99.100:9000

Do a scanner of the code on th current directory and push data on sonar.host.
