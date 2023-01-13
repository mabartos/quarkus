# Test reproducer

1. Fetch the `quarkus3.yml` (directly from the commit in the PR): 
   ```
   curl -o quarkus3.yml https://raw.githubusercontent.com/quarkusio/quarkus/1116057e619b92e371ef30e467ae71bdc4710628/jakarta/quarkus3.yml
   ```
2. Run OpenRewrite script:
   ```
   mvn org.openrewrite.maven:rewrite-maven-plugin:4.36.0:run \
   -Drewrite.configLocation=`pwd`/quarkus3.yml \
   -DactiveRecipes=io.quarkus.openrewrite.Quarkus3
   ```
3. Check changed files