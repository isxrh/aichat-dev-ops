## 4. nginx环境配置

krab@krabLaptop:/mnt/d/MyDocs/JavaProject/ChatGPT/dev-ops/nginx/conf$ 

docker container cp Nginx:/etc/nginx/nginx.conf /mnt/d/MyDocs/JavaProject/ChatGPT/dev-ops/nginx/conf
docker container cp Nginx:/etc/nginx/conf.d/default.conf  /mnt/d/MyDocs/JavaProject/ChatGPT/dev-ops/nginx/conf/conf.d/default.conf  
docker container cp Nginx:/usr/share/nginx/html/index.html  /mnt/d/MyDocs/JavaProject/ChatGPT/dev-ops/nginx/html

docker run --name Nginx -d -p:80:80 -v /mnt/d/MyDocs/JavaProject/ChatGPT/dev-ops/nginx/html:/usr/share/nginx/html -v /mnt/d/MyDocs/JavaProject/ChatGPT/dev-ops/nginx/logs:/var/log/nginx -v /mnt/d/MyDocs/JavaProject/ChatGPT/dev-ops/nginx/conf/nginx.conf:/etc/nginx/nginx.conf -v /mnt/d/MyDocs/JavaProject/ChatGPT/dev-ops/nginx/conf/conf.d:/etc/nginx/conf.d --privileged=true --restart=always nginx