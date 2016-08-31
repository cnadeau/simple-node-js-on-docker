
#Dockerfile:

- starts from Alpine image (smaller than Ubuntu one) with node installed
- copies package.json then npm install (since it rarely changes, this layer, once build, will be reused when rebuilding the app)
- copies the app source code on top of the npm install
- exposes ports where the server will listen
- starts the server using the `npm start` script

#Build and run locally within your Vagrant machine (or locally if you have Docker for Mac/Windows)

```
docker-compose up --build
```

pressing CTRL+C to totally shut down the client