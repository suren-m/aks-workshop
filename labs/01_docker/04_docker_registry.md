## Choose your favourite Container Registry and connect to it from your terminal. (for learning /personal use)

* Github Container Registry - ghcr.io
* Docker Hub
* Azure Container Registry

## Tag and Push your image to registry.

1. Before you can push your image to your registry, You need to tag it. 

    Tag your `hello-web` image as below. Replace the <image-id> and <dockerhub-username> as needed.

    ```bash
        docker images hello-web 
        
        # Copy the image-id
        docker tag <image-id> <dockerhub-username>/hello-web:1.0

        docker push <docker-hub-username>/hello-web:1.0
    ```

2. Go to `hub.docker.com` to ensure your image is pushed correctly. We will come to this image later during kubernetes labs.

3. You can always test out your image by running it as follows. 

```bash
    docker run -d -p 9010:80 <dockerhub-username>/hello-web:1.0
    docker ps
    docker stop <hello-web_container_id>
```

5. Logout of docker hub from terminal

```bash
    docker logout
```

### Clean up the resources as done before and ensure your environment is correctly tidied up.   

    ```bash
        docker system prune -a
        # type `y` when prompted
        docker ps -a
        docker images
    ```
> Bonus: Try other approaches to clean up your environment too. `rmi`, `prune container`, etc.
