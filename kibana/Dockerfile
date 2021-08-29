# FROM ubuntu:20.04

# RUN apt-get update && apt-get install -y wget gnupg2

# RUN wget -qO - https://artifacts.elastic.co/GPG-KEY-elasticsearch | apt-key add -

# RUN apt-get update && apt-get install -y apt-transport-https ca-certificates

# RUN echo "deb https://artifacts.elastic.co/packages/7.x/apt stable main" | tee -a /etc/apt/sources.list.d/elastic-7.x.list

# RUN apt-get update && apt-get install -y kibana

# ENTRYPOINT [ "/usr/share/kibana/bin/kibana", "--allow-root" ]




 FROM docker.elastic.co/kibana/kibana:7.14.0
# ADD config/ /usr/share/kibana/config/