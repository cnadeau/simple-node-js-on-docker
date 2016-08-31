
#Dockerfile:

- starts from Alpine image (smaller than Ubuntu one) with node installed
- copies all the app source code
- exposes ports where the server will listen
- starts the server using the `npm start` script which will :
  - npm install
  - start concurrently
    - nodemon for live reload
    - node-inspector to debug the app

#Build and run locally within your Vagrant machine (or locally if you have Docker for Mac/Windows)

```
docker-compose up --build
```

pressing CTRL+C to totally shut down the client


# Debugging
nodemon and node-inspector were added in order to start debugging a nodejs app easily: simply hit

```
http://localhost:9090/?port=5858
```

This allows to create a share from your local dev machine with a specific path in the container which will sync on file change (see docker-compose.yml)