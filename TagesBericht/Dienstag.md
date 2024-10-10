# Dienstag 

1. Daly scrum 
2. Nginx 
3. Wie packet Manager funktioniert 
4. Docker container vertiefung
5. Docker volume 

## Docker mit nginx

`docker run -it nginx bash`
erstellt container mit nginx 

`docker ps`
zeigt laufende containers

`docker ps -a`
zeigt alle containers

`docker run -p  8080:80 nginx`
erstellt container mit nginx und gib local port 8080
damit in browser website sichtbar wird 

`docker kill A1`
stopt container mit name A1. kann auch id benutzt 

## in container 

`apt update`
check neue versionen 

`apt install vim`
Container hat kein vim by default deswegen muss man denn installieren 

index.html liegt in /usr/share/nginx/html by default 


`docker volume VOLUMENAME`
erstellt volume die für allen container verfügbar sind 

`docker run -d --name M1 --mount source=my-vol,target=/usr/share/nginx/html nginx`
erstellt docker die mit my-vol verbunden 
dann ändern wir index.html und neue kontainer (wenn auch vebunden) hab dieselber änderungen

