# FROM ubuntu:20.04

# RUN apt-get update && apt-get install -y wget gnupg2
# RUN wget -qO - https://artifacts.elastic.co/GPG-KEY-elasticsearch | apt-key add -

# # we need to then install the apt-transport-https package
# RUN apt-get update && apt-get install -y apt-transport-https

# # now we add the repository definition to the system
# RUN echo "deb https://artifacts.elastic.co/packages/7.x/apt stable main" | tee -a /etc/apt/sources.list.d/elastic-7.x.list

# # now install a version of Elasticsearch that contains only features licensed under Apache 2.0 (i.e. oss)
# RUN echo "deb https://artifacts.elastic.co/packages/oss-7.x/apt stable main" | tee -a /etc/apt/sources.list.d/elastic-7.x.list


# RUN apt-get update && apt-get install -y default-jre
# RUN apt-get install -y logstash



FROM docker.elastic.co/logstash/logstash:7.14.0
RUN rm -f /usr/share/logstash/pipeline/logstash.conf
ADD pipeline/ /usr/share/logstash/pipeline/
ADD config/ /usr/share/logstash/config/
