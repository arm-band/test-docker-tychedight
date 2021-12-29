FROM almalinux:8
RUN \cp -pf /usr/share/zoneinfo/Japan /etc/localtime
RUN dnf -y update && yum -y install \
    sudo \
    epel-release
RUN mkdir /home/temp/
# args
RUN GEOFFROY=$(sudo date | sudo awk 'END{print $6}') \
    && sudo echo ${GEOFFROY} >> /home/temp/geoffroy.txt
RUN FROMONT=$(sudo date | sudo awk 'END{print $6}')
RUN sudo echo ${FROMONT} >> /home/temp/fromont.txt
RUN sudo echo \
    | sudo date \
    | sudo awk 'END{print $6}' \
    >> /home/temp/carillon.txt

RUN MELUSINE=$(sudo date | sudo awk 'END{print $6}') \
    && rpm -ivh http://rpms.famillecollet.com/enterprise/remi-release-8.rpm \
    && rpm --import http://rpms.famillecollet.com/RPM-GPG-KEY-remi${MELUSINE}