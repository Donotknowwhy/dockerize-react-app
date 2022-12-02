Dockerize react app + Docker Hub + AWS ECR

# v1.0 Dockerize React App

Reference [Dockerize React App](https://dev.to/karanpratapsingh/dockerize-your-react-app-4j2e).

## Available Scripts

In the project directory, you can run:

### `docker-compose -f docker-compose.dev.yml up`

Runs the app in the development mode.\
Open [http://localhost:3000](http://localhost:3000) to view it in your browser.

The page will reload when you make changes.\
You may also see any lint errors in the console.

### `docker-compose -f docker-compose.prod.yml build`
### `docker run -p 80:80 --name react-app react-app-product`

Runs the app in the production mode.\
Open [http://localhost:80](http://localhost:3000) to view it in your browser.

After stop container, the next time run:

### `docker start [YOUR_REACT_APP_CONTAINER]`


# v2.0 Push Image to docker hub

1. Signed in hub.docker.com

2. Create repo docker hub

3. Build docker in local
### `docker build .`

4. Rename image
### `docker tag [YOUR_REACT_APP_CONTAINER] <hub-user>/<repo-name>[:<tag>]`

5. Push image

### `docker push <hub-user>/<repo-name>[:<tag>]`

## Additional
Pull an image from docker hub and run local

6. pull image

### `docker pull <hub-user>/<repo-name>[:<tag>]`

7. run image as container

### `docker run -d -p 3000:3000 [YOUR_DOCKER_IMAGE]`

# v3.0 Push Image to AWS ECR

1. Create ECR repo

(--View commands ECR in repo--) 

2. Configure aws in local
### `aws configure`

3. Login ecr aws

### `aws ecr-public get-login-password --region us-east-1 | docker login --username AWS --password-stdin public.ecr.aws/e1p5h8o7`

4. Rename image 

### `docker tag react-app:latest public.ecr.aws/e1p5h8o7/react-app:latest`

5. Push an image to aws ecr

### `docker push public.ecr.aws/e1p5h8o7/react-app:latest`
