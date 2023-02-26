# Stage 1
FROM kazade/dreamcast-sdk as build

# Installing prerequisites
#RUN apk add gcc
RUN yum install gcc


# Add dcloadip 
RUN git clone https://github.com/sizious/dcload-ip.git /opt/toolchains/dc/dcloadip \
   && cd /opt/toolchains/dc/dcloadip \
   && make \
   && make install
