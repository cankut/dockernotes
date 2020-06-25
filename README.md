# dockernotes
Tips on Docker

### Docker decides where to create the volume (for Windows, inside VM)
`
docker volume create todo-db
`

### We decide where to bind volume (for Windows)
`
docker volume create --name todo-db --opt type=none --opt device=c:\data --opt o=bind
`

### Difference between RUN and CMD in Dockerfile
```dockerfile
# RUN executes a command on build of an image
RUN yarn install --production 

# CMD provides a default command to execute when container boots
CMD ["node", "/appc/src/index.js"]
```
