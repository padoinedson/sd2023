

https://docs.docker.com/engine/install/ubuntu/

https://training.play-with-docker.com/beginner-linux/


https://imasters.com.br/banco-de-dados/docker-compose-o-que-e-para-que-serve-o-que-come
https://github.com/concrete-cristian-trucco/wordpress-mysql-compose






---------------------------------------------------------  

sudo usermod -aG docker ${USER}


## Criar um volume

Criar um volume para armazenar os dados do container  

$ docker volume create mysql2023data  

> nome do volume: mysql2023data   



## Criar um container com o volume

$ docker run --name mysql2023docker -v mysql2023data:/var/lib/mysql -e MYSQL_ROOT_PASSWORD=1234 mysql2023  

> os dados do diretório do container /var/lib/mysql serão salvos no volume criado mysql2023data    
> quando o container for removido a database fica salva no volume  





## Check the MySQL version - option A

> docker exec -it mysql2023docker \  
> mysql --user=root --password=$1234 --version  



## Check the MySQL version  - option B

> docker exec -it mysql2023docker sh
> mysql --user=root --password=$1234 --version
> exit  

