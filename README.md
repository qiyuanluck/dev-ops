# dev-ops
docker container cp Nginx:/etc/nginx/nginx.conf /root/nginx/conf
docker container cp Nginx:/etc/nginx/conf.d/default.conf /root/nginx/conf/conf.d/default.conf
docker container cp Nginx:/usr/share/nginx/html/index.html /root/nginx/html

docker run --name Nginx -p 80:80 -v /root/nginx/logs:/var/log/nginx -v /root/nginx/html:/usr/share/nginx/html -v /root/nginx/conf/nginx.conf:/etc/nginx/nginx.conf -v /root/nginx//conf/conf.d:/etc/nginx/conf.d -v /root/nginx/ssl:/etc/nginx/ssl/--privileged=true -d --restart=always nginx

docker run
--name Nginx
-p 80:80
-v /root/nginx/logs:/var/log/nginx
-v /root/nginx/html:/usr/share/nginx/html
-v /root/nginx/conf/nginx.conf:/etc/nginx/nginx.conf
-v /root/nginx//conf/conf.d:/etc/nginx/conf.d
-v /root/nginx/ssl:/etc/nginx/ssl/  
--privileged=true -d --restart=always nginx