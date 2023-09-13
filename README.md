# Dockerize React App + Docker Hub + AWS EC2 + AWS ECS

## Version 1.0: Dockerize React App

Reference: [Dockerize React App](https://dev.to/karanpratapsingh/dockerize-your-react-app-4j2e)

### Available Scripts

In the project directory, you can run:

#### `docker-compose -f docker-compose.dev.yml up`

This command runs the app in development mode.\
Open [http://localhost:3000](http://localhost:3000) in your browser to view it.

The page will automatically reload when you make changes.\
You may also see any lint errors in the console.

#### `docker-compose -f docker-compose.prod.yml build`
#### `docker run -p 80:80 --name react-app react-app-product`

To run the app in production mode, execute the above commands.\
Open [http://localhost:80](http://localhost:3000) in your browser to view it.

If you stop the container and want to run it again:

#### `docker start [YOUR_REACT_APP_CONTAINER]`

## Version 2.0: Push Image to Docker Hub

1. Sign in to [hub.docker.com](https://hub.docker.com)

2. Create a Docker Hub repository

3. Build the Docker image locally

#### `docker build .`

4. Rename the image

#### `docker tag [YOUR_REACT_APP_CONTAINER] <hub-user>/<repo-name>[:<tag>]`

5. Push the image

#### `docker push <hub-user>/<repo-name>[:<tag>]`

## Additional: Pull an Image from Docker Hub and Run Locally

6. Pull an image from Docker Hub

#### `docker pull <hub-user>/<repo-name>[:<tag>]`

7. Run the image as a container

#### `docker run -d -p 3000:3000 [YOUR_DOCKER_IMAGE]`

## Version 3.0: Push Image to AWS ECR (SSH into a local EC2 instance or connect via the EC2 console)

1. Create an Amazon Elastic Container Registry (ECR) repository

(Note: View ECR commands in the repository)

2. Configure AWS locally

#### `aws configure`

3. Log in to AWS ECR

#### `aws ecr-public get-login-password --region us-east-1 | docker login --username AWS --password-stdin public.ecr.aws/e1p5h8o7`

4. Rename the image

#### `docker tag react-app:latest public.ecr.aws/e1p5h8o7/react-app:latest`

5. Push the image to AWS ECR

#### `docker push public.ecr.aws/e1p5h8o7/react-app:latest`

## Version 4.0: Define Tasks, Create a Cluster, and Link to an EC2 Instance

Reference: [YouTube Tutorial](https://www.youtube.com/watch?v=aSd1S-4jQ-Q)

### Note: If you can't access

1. Remove "https" from the public IPv4 address

2. Open Security groups and add inbound rules: All traffic, anywhere

3. Check VPC configuration
