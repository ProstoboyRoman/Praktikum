# Montag

1. Docker 
2. Container 
3. Team kennengelernt 
4. Meeting gemacht
5. Grundlagen besprochen  
6. Zsh installiert

## zsh installiert 
https://github.com/ohmyzsh/ohmyzsh
https://github.com/ohmyzsh/ohmyzsh/wiki/themes

## fastfetch installiert
`brew install fastfetch`

# Docker istalliert 

## Docker container mit debian

`docker run -it debian /bin/bash`
wird container mit debian erstellt und diereckt geöfnnet 

`docker run -d --name A1 debian /bin/bash -c "echo 'Hello World'; sleep infinity"`
erstellt container mit name A1 und lassen den container immer funkioniern

`docker container exec -it A2 bash`
offnen container A2 nur wenn der schon funkioniert 

## Docker Doc
https://docs.docker.com/engine/containers/run/