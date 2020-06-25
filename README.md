# dockernotes
Tips on Docker

### Docker decides where to create the volume (for Windows, inside VM)
`docker volume create todo-db`

### We decide where to bind volume (for Windows)
`docker volume create --name todo-db --opt type=none --opt device=c:\data --opt o=bind`
