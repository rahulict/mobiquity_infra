FROM amazonlinux:latest

COPY gowebserver.conf /etc/httpd/conf.d/
RUN mkdir -p /home/ec2-user/mobi_IaC_CM/appcode/logs 
ADD https://s3.amazonaws.com/ops-hiring-webserver/gowebserver /home/ec2-user/mobi_IaC_CM/appcode/gowebserver
RUN chmod 755 /home/ec2-user/mobi_IaC_CM/appcode/gowebserver \
    && yum install go httpd vim -y
ENV PORT=8082
CMD service httpd start && /home/ec2-user/mobi_IaC_CM/appcode/gowebserver >/home/ec2-user/mobi_IaC_CM/appcode/logs/gowebserver.log  2>&1
