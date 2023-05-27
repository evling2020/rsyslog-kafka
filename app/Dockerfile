FROM debian
#RUN sed -i s/deb.debian.org/mirrors.ustc.edu.cn/g /etc/apt/sources.list
#RUN sed -i 's/deb.debian.org\/debian/mirrors.ustc.edu.cn\/debian-security/g' /etc/apt/sources.list
RUN sed -i 's/deb.debian.org/mirrors.ustc.edu.cn/g' /etc/apt/sources.list
RUN apt update && apt install rsyslog rsyslog-kafka -y
#RUN echo '$ModLoad imudp \n\
#$UDPServerRun 514 \n\
#$ModLoad imtcp \n\
#$InputTCPServerRun 514 \n\
#$template RemoteStore, "/var/log/remote/%$year%/%$Month%/%$Day%/%$Hour%.log" \n\
#:source, !isequal, "localhost" -?RemoteStore \n\
#:source, isequal, "last" ~ ' > /etc/rsyslog.conf
COPY rsyslog.conf /etc/rsyslog.conf
ENTRYPOINT ["rsyslogd", "-n"]
