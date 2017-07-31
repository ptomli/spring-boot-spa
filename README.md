# A Spring Boot + Vue.js Single Page Application example

Just one way of putting together a Java backend, using Spring Boot, and a single page application, using Vue.js.

The mechanism used here is to bundle the `frontend` module output into `target/classes/public`, which Maven then packages up into the JAR file. The `backend`  module then depends on the `frontend`, which results in those files being available in `classpath:/public/`, which Spring Boot happily serves up.

