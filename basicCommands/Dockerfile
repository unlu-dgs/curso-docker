FROM ubuntu:14.04

ENV http_proxy http://proxy.unlu.edu.ar:8080
ENV https_proxy http://proxy.unlu.edu.ar:8080

RUN apt-get -y update && apt-get install -y fortunes
CMD ls -lh /
CMD /usr/games/fortune -a 

