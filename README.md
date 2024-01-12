# dev-ops

# Step1: Nginx environment configuration(In local win10 enve)
## copy files:
### 1.docker cp Nginx:/etc/nginx/nginx.conf E:\Codes\JavaBeginner\Projects\01chatgpt\nginx\conf
### 2.docker cp Nginx:/etc/nginx/conf.d/default.conf E:\Codes\JavaBeginner\Projects\01chatgpt\nginx\conf\conf.d\default.conf
### 3.docker cp Nginx:/usr/share/nginx/html/index.html E:\Codes\JavaBeginner\Projects\01chatgpt\nginx\html

## Rerun the nginx with mapping path:
    Mac version:
        docker run \
        --name Nginx \
        -p 80:80 \
        -v E:\Codes\JavaBeginner\Projects\01chatgpt\nginx\logs:/var/log/nginx \
        -v E:\Codes\JavaBeginner\Projects\01chatgpt\nginx\html:/usr/share/nginx/html \
        -v E:\Codes\JavaBeginner\Projects\01chatgpt\nginx\conf\nginx.conf:/etc/nginx/nginx.conf \
        -v E:\Codes\JavaBeginner\Projects\01chatgpt\nginx\conf\conf.d:/etc/nginx/conf.d \
        -v E:\Codes\JavaBeginner\Projects\01chatgpt\nginx\ssl:/etc/nginx/ssl/  \
        --privileged=true -d --restart=always nginx
     Win10 version:
        docker run --name Nginx -p 80:80 -v E:/Codes/JavaBeginner/Projects/01chatgpt/nginx/logs:/var/log/nginx -v E:/Codes/JavaBeginner/Projects/01chatgpt/nginx/html:/usr/share/nginx/html -v E:/Codes/JavaBeginner/Projects/01chatgpt/nginx/conf/nginx.conf:/etc/nginx/nginx.conf -v E:/Codes/JavaBeginner/Projects/01chatgpt/nginx/conf/conf.d:/etc/nginx/conf.d -v E:/Codes/JavaBeginner/Projects/01chatgpt/nginx/ssl:/etc/nginx/ssl/ --privileged=true -d --restart=always nginx
