# Devops TP 3 ansible

Tanguy FROUIN 5IRC

Remarque:  
Utilisation des images Docker de Rémy DAVID comme les TP1 et 2 n'ont pas été faits

3.1  

inventories setup  
![alt text](./images/image-4.png)

Résultats :  
![alt text](./images/image.png)


![alt text](./images/image-1.png)


Playbook
![alt text](./images/image-2.png)

Résultat playbook
![alt text](./images/image-3.png)


### Rôles 

3.2

```bash
ansible-galaxy init roles/docker
- Role roles/docker was created successfully
```
On déplace l'installation de docker dans le `main.yml` du rôle `docker` :  

![alt text](./images/image-5.png)

Ajout du rôle `docker` dans le contenu du playbook :  

![alt text](./images/image-6.png)

Résultat :  

![alt text](./images/image-7.png)



Création des rôles :  
```bash
ansible-galaxy init roles/install-docker
ansible-galaxy init roles/create-network
ansible-galaxy init roles/launch-database
ansible-galaxy init roles/launch-app
ansible-galaxy init roles/launch-proxy
```


inventories setup.yml  
![alt text](./images/image-9.png)

Ajout des rôles dans le playbook  (on peut virer le rôle `docker` qui sera remplacé par `install-docker`)
![alt text](./images/image-15.png)

create-network  
![alt text](./images/image-14.png)

Instruction d'installation dans install-docker  
![alt text](./images/image-13.png)

Variables d'env pour se connecter à la BDD  
  
launch-app  
![alt text](./images/image-10.png)

launch-database  
![alt text](./images/image-11.png)

launch-proxy  
![alt text](./images/image-12.png)

Résultat API :  
![alt text](./images/image-8.png)

![alt text](./images/image-16.png)

### Front  

Creation du rôle `launch-front`:  
```bash
ansible-galaxy init roles/launch-front
```

Ajout du rôle dans le playbook  
![alt text](./images/image-18.png)

Modification des tasks pour chaque rôle `launch-x`:  
  
launch-front  
![alt text](./images/image-17.png)

launch-database  
![alt text](./images/image-19.png)

launch-app  
![alt text](./images/image-20.png)

launch-proxy  
![alt text](./images/image-21.png)

Résultats  
![alt text](./images/image-22.png)

![alt text](./images/image-23.png)