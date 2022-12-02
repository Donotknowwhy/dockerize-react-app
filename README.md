v1.0
# Dockerize React App

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

v2.0
# Push Image to docker hub

1. Signed in hub.docker.com

2. Create repo docker hub

3. Build docker in local
### `docker build .`

4. Rename image
### `docker tag [YOUR_REACT_APP_CONTAINER] <hub-user>/<repo-name>[:<tag>]`

5. Push image

### `docker push <hub-user>/<repo-name>[:<tag>]`