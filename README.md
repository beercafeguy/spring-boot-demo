# spring-boot-demo
This is a test application which I use in spring boot workshops for demo.

### Steps to run the app in local
* Build the spring boot app using maven<br/>
  `mvn clean install`
* To test the application, run <br>
  `java -jar <jar name>`
    * To verify, please visit <br>
    `https://localhost:8082/api/hello`

### Steps to run the app in docker
* Create the docker image from given Dockerfile<br/>
`cd <project dir/ dir where Dockerfile is located>` <br>
`docker build -t boot_app:V1 --build-arg JAR_FILE=target/spring-boot-demo-0.0.1-SNAPSHOT.jar .` 

* check if the image in created <br>
`docker image ls`

* (Optional) Push the image to docker hub
  * Login to hub <br>
  `docker login`
  * Tag Docker image to repo <br>
  `docker tag 223e9e3e0467 beercafeguy/boot_app:v1`
  * Push the image to Docker HUB <br>
  `docker push beercafeguy/boot_app:v1`
  * Verify image on https://hub.docker.com 
* Run the image on docker to create the container <br>
`docker run -it -p 8082:8082 beercafeguy/boot_app:v1`
* To verify, please visit <br>
`https://localhost:8082/api/hello`
