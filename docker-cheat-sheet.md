## Images
* **`docker build .`**	                  build <br/>
* **`docker build -t repo:tag .`**        build with tag<br/>
* **`docker images`**	                  list <br/>
* **`docker inspect image_id`**	          inspect <br/>
* **`docker rmi image_id`**	          delete <br/>
* **`docker run image_id`**	          create + start <br/>
* **`docker tag image_id repo:tag`**      tag <br/>

## Container
* **`docker create image_id`**	          create <br/>
* **`docker exec -it container_id bash`** exec bash <br/>
* **`docker ps`**	                  list running <br/>
* **`docker ps -a`**	                  list all <br/>
* **`docker start container_id`**         start <br/>
* **`docker stop container_id`**          stop <br/>
* **`docker cp container_id:/path/file/ /path/file`** copies file out of container <br/>  
* **`docker rm container_id`**          delete container <br/>  

## Docker Compose
* **`docker-compose up`**	          tbd <br/>
* **`docker-compose build`**	          tbd <br/>

## Misc

**Layer** indicates changes that are made to an image.
```
FROM rails:onbuild                   < Base-layer
ENV RAILS_ENV production             < layer 2
ENTRYPOINT ["bundle", "exec", "puma”]< layer 3
```
