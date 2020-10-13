# spring-boot-app

## Docker build strategy

1. clone the spring-boot-app example repository,
2. maven build

    ```
    mvn clean install
    ```

3. docker build -t spring-boot-app .
4. docker run --name spring-boot-app -d -p 8080:8080 spring-boot-app
5. docker ps -a
6. docker logs spring-boot-app
7. docker rm spring-boot-app
8. oc login to your openshift cluster,

    ```
    oc login --token=OaKeDQhbtxNIh-5aWP21WSS8VnaIZYsXl41sQNu5Rk8 --server=https://c114-e.us-south.containers.cloud.ibm.com:31739
    ```

9. oc new-project oc-docker-build
10. oc new-app . --strategy=docker

    ```
    oc get bc
    oc get builds
    oc get dc
    ```

11. oc delete

    ```
    oc delete project oc-docker-build
    ```
