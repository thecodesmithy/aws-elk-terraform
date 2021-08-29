# FROM ubuntu:20.04

# # don't need to run sudo as you're ROOT already... not ideal, change that when you can!

# # first, we need to add Elastic’s signing key so that the downloaded package can be verified
# RUN apt-get update && apt-get install -y wget gnupg2
# RUN wget -qO - https://artifacts.elastic.co/GPG-KEY-elasticsearch | apt-key add -

# # we need to then install the apt-transport-https package
# RUN apt-get update && apt-get install -y apt-transport-https

# # now we add the repository definition to the system
# RUN echo "deb https://artifacts.elastic.co/packages/7.x/apt stable main" | tee -a /etc/apt/sources.list.d/elastic-7.x.list

# # now install a version of Elasticsearch that contains only features licensed under Apache 2.0 (i.e. oss)
# RUN echo "deb https://artifacts.elastic.co/packages/oss-7.x/apt stable main" | tee -a /etc/apt/sources.list.d/elastic-7.x.list

# # all that’s left to do is to update your repositories and install Elasticsearch
# RUN apt-get update && apt-get install -y elasticsearch

# USER elasticsearch

# ENTRYPOINT [ "/usr/share/elasticsearch/bin/elasticsearch" ]



FROM docker.elastic.co/elasticsearch/elasticsearch:7.14.0
# ADD config/ /usr/share/elasticsearch/config/
USER elasticsearch
ENTRYPOINT [ "/usr/share/elasticsearch/bin/elasticsearch" ]