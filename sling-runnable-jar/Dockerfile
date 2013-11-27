# Dockerfile that runs a Sling runnable jar
#
# Starting from a fresh docker install you 
# can run this as follows:
#
#   docker pull base
#   docker run base /bin/echo docker works!
#   # copy sling.jar and run.sh here
#   docker build .
#   # note the image <id> that this returns
#   docker run <id>
#
# Use docker ps to see what's running and 
# docker stop <container id> to stop
#
FROM base
MAINTAINER myself
RUN apt-get -qq update
RUN apt-get install -y openjdk-7-jre-headless wget
RUN (mkdir /usr/local/sling)
ADD ./sling.jar /usr/local/sling/sling.jar
ADD ./run.sh /usr/local/sling/run
EXPOSE 8888
CMD ["/bin/sh", "-e", "/usr/local/sling/run"]
