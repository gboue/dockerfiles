FROM openjdk:11-jre-slim

RUN apt-get update \
  && apt-get install curl python3 python3-pip graphviz -y \
  && mkdir -p /usr/local/bin \
  && curl -v -s -o /usr/local/bin/requirements.txt https://raw.githubusercontent.com/gboue/swagger_to_uml/master/requirements.txt \
  && curl -v -s -o /usr/local/bin/swagger_to_uml.py https://raw.githubusercontent.com/gboue/swagger_to_uml/master/swagger_to_uml.py \  
  && pip3 install --upgrade --no-cache-dir -r /usr/local/bin/requirements.txt \
  && rm /usr/local/bin/requirements.txt \
  && rm -rf /var/lib/apt/lists/*

COPY *.jar /usr/local/bin/
COPY *.sh /usr/local/bin/
RUN chmod +x /usr/local/bin/*.sh
RUN chmod +x /usr/local/bin/*.jar
RUN mkdir /data
WORKDIR /data
