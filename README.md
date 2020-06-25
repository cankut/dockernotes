# dockernotes
Tips on Docker

### Docker decides where to create the volume (for Windows, inside VM)
`docker volume create todo-db`

`docker run -dp 3000:3000 -v todo-db:/etc/todos getting-started`


### We decide where to bind volume (for Windows)
`docker volume create --name todo-db --opt type=none --opt device=c:\data --opt o=bind`

`docker run -dp 3000:3000 -v todo-db:/etc/todos getting-started`

### Alternative (directly provide path)
`docker run -dp 3000:3000 -v c:\data:/etc/todos getting-started`

### Run app in development mode 
  1. bind local path with containers app path
  2. bind db path for persistence 
  3. monitor for changes with nodemon (in package.json)

`docker run -dp 3000:3000 -w /app -v c:\docker\app:/app -v todo-db:/etc/todos node:12-alpine sh -c "yarn install && yarn run dev"`

### Difference between RUN and CMD in Dockerfile
```dockerfile
# RUN executes a command on build of an image
RUN yarn install --production 

# CMD provides a default command to execute when container boots
CMD ["node", "/appc/src/index.js"]
```
