FROM nginx
LABEL "Project"="Docker"
LABEL "Author"="pifflox"

RUN rm -rf /etc/nginx/conf.d/default.conf
COPY nginvproapp.conf /etc/nginx/conf.d/dbnginx.conf