# TP 1 - Docker

## 5. Exécuter un serveur web dans un conteneur docker

#### a. Récupérer l’image sur le Docker Hub :
```docker pull nginx``` 
#### b. Vérifier que cette image est présente en local :
![docker images]( /capture_docker_tp1/5-docker_images.PNG )

#### c. Créer un fichier index.html simple :
je crée un répertoire /tp_docker dans lequel je crée un fichier index.html  
![création_index]( /capture_docker_tp1/5-création_index.html.PNG )  
![index.html]( /capture_docker_tp1/5-création_index.html2.PNG )

#### d. Démarrer un conteneur et servir la page html créée précédemment à l’aide d’un volume (option -v de docker run) :
J'exécute la commande ```docker run -d -p 8080:80 -v /home/admin/tp_docker/:/usr/share/nginx/html/ nginx```  
et j'observe le résultat  
![resultat navigateur]( /capture_docker_tp1/5-run-v.PNG )  
![resultat navigateur]( /capture_docker_tp1/5-docker-v.PNG )

#### e. Supprimer le conteneur précédent et arriver au même résultat que précédemment à l’aide de la commande docker cp :
je supprime le conteneur précédent  
![resultat navigateur]( /capture_docker_tp1/5-rm.PNG )  
puis je lance la commande ```docker run -d -p 8080:80 nginx```  
et ensuite je fais ```docker cp /home/admin/tp_docker/index.html 7bde8524ce9b1c50c73c8e157a5304c1a4b90b477e125:/usr/s
hare/nginx/html/index.html```  
![docker cp]( /capture_docker_tp1/5-docker_cp.PNG )  
j'observe ensuite que j'ai toujours le meme résultat depuis mon navigateur

## 6. Builder une image
#### a. A l’aide d’un Dockerfile, créer une image (commande docker build) :
premièrement je crée le Dockerfile  
![dockerfile]( /capture_docker_tp1/6.1.PNG )   
ensuite je build mon image  
![docker build]( /capture_docker_tp1/6.2.PNG ) 

### b. Exécuter cette nouvelle image de manière à servir la page html (commande docker run) :
![docker run mon_image]( /capture_docker_tp1/6.3.PNG )









