# Querying Like It's Tomorrow - ZIO World 2022

## Instructions
1. Download and install docker.
2. Clone this repo: `git clone 'https://github.com/deusaquilus/querying-like-its-tomorrow.git'`
3. Run the start script: `./start.sh` to start the postgres docker image.
4. Compile and run the examples:
5. `sbt 'runMain deusaquilus.simple.RestService'`
   #### Other Main Functions for Rest/Graphql services:
   - **deusaquilus.simplefilter.RestService** - Rest Http Server, filters by ID
   - **deusaquilus.intermediate.RestService** - Rest Http Server, filters by arbitrary fields and includes/excludes arbitrary columns
   - **deusaquilus.rest.RestService** - Rest Http Server, same as `intermediate.RestService` but also displays DB query plans in the console as queries are run
   - **deusaquilus.graphql.GraphqlService** - Graphql Http Server

   #### Code Samples from Talk
   - deusaquilus.ExtensionsScala2Style
   - deusaquilus.ExtensionScala3Style
   - deusaquilus.ExtensionScala3_NoQuotes
   - deusaquilus.ExtensionScala3_InlineMethod
   - deusaquilus.ExtensionScala3_Typeclass
   - deusaquilus.ExtensionScala3_InlineMatch
   - deusaquilus.RobotCustomers
   - deusaquilus.YettiCustomers

4. Run the main class to start the http server:
  ```
  > sbt 'runMain deusaquilus.simple.RestService'
  [info] welcome to sbt 1.6.1 (AdoptOpenJDK Java 1.8.0_275)
  [info] loading global plugins from /home/me/.sbt/1.0/plugins
  [info] Server started on port 8090
  ```
5. Try the various APIs:
  ```
  > curl http://localhost:8088/customers
  [{"name":"Joe Smith","age":44,"membership":"k","id":1,"hid":1},{"name":"Joe Rolland","age":55,"membership":"k","id":2,"hid":2}]
  ```

You can use the `RandomData` class to generate an arbitrary amount of data and writes it to the DB.
This is useful if you'd like to to examine execution plans and test DB/App performance. `RandomData` uses the `mockneat` library to generate human-readable names and addresses.
It can be run via `sbt 'runMain deusaquilus.RandomData'`
