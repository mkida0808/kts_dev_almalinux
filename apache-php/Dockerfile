# FROM almalinux:8.4

# RUN dnf install -y https://dl.fedoraproject.org/pub/epel/epel-release-latest-8.noarch.rpm
# RUN dnf install -y https://rpms.remirepo.net/enterprise/remi-release-8.rpm
# RUN dnf repolist
# RUN dnf module enable php:remi-8.0 -y
# RUN dnf install php php-cli

# EXPOSE 80
# FROM centos:8.3.2011
FROM almalinux:8.4
# SHELL ["/bin/bash", "-c"]

#SELinuxを無効化
# RUN setenforce 0

# アップデート＆必要パッケージのインストール
# RUN rpm --import http://mirror.centos.org/centos/RPM-GPG-KEY-CentOS-7
# RUN rpm --import http://dl.fedoraproject.org/pub/epel/RPM-GPG-KEY-EPEL-7

# RUN dnf install https://dl.fedoraproject.org/pub/epel/epel-release-latest-8.noarch.rpm
# RUN dnf install https://rpms.remirepo.net/enterprise/remi-release-8.rpm

RUN dnf install -y https://dl.fedoraproject.org/pub/epel/epel-release-latest-8.noarch.rpm
RUN dnf install -y https://rpms.remirepo.net/enterprise/remi-release-8.rpm
RUN rpm --import https://rpms.remirepo.net/RPM-GPG-KEY-remi2021

RUN dnf -y update -v && dnf clean all
RUN dnf -y upgrade -v && dnf clean all
RUN dnf -y install epel-release && dnf clean all
RUN dnf -y update epel-release && dnf clean all

# RUN yum -y install http://rpms.remirepo.net/enterprise/remi-release-8.rpm

# RUN yum install -y http://rpms.remirepo.net/enterprise/remi-release-8.rpm
# RUN yum -y install http://rpms.remirepo.net/enterprise/remi-release-8.rpm
# RUN rpm --import http://rpms.remirepo.net/RPM-GPG-KEY-remi

# RUN dnf install -y https://dl.fedoraproject.org/pub/epel/epel-release-latest-8.noarch.rpm
# RUN dnf install -y https://rpms.remirepo.net/enterprise/remi-release-8.rpm
# RUN rpm --import https://rpms.remirepo.net/RPM-GPG-KEY-remi2021
# RUN dnf repolist

# RUN dnf config-manager --set-enabled remi

# RUN yum -y install yum-utils
# RUN yum-config-manager --enable remi

# RUN yum module reset php

# RUN dnf clean all && rm -r /var/cache/dnf  && dnf upgrade -y && dnf update -y

# dnf moduleコマンドの最後に"-y"を追加
# RUN dnf module reset php

# RUN dnf clean all && rm -r /var/cache/dnf  && dnf upgrade -y && dnf update -y

# RUN ls -l /etc/pki/rpm-gpg/

RUN dnf module install php:remi-8.0 -y

# 近喰さんのソースより（PHP8部分）
# RUN dnf install -y php php-bcmath php-cli php-common php-dba php-dbg php-devel php-embedded php-enchant php-fpm php-gd php-gmp php-imap php-intl php-ldap php-litespeed php-mbstring php-mcrypt php-mysqlnd php-odbc php-opcache php-pdo php-pear php-pgsql php-process php-pspell php-snmp php-soap php-tidy php-xml php-xmlrpc

RUN dnf install -y php80 php80-{php-bcmath,php-cli,php-common,php-dba,php-dbg,php-devel,php-embedded,php-enchant,php-fpm,php-gd,php-gmp,php-imap,php-intl,php-ldap,php-litespeed,php-mbstring,php-mcrypt,php-mysqlnd,php-odbc,php-opcache,php-pdo,php-pear,php-pgsql,php-process,php-pspell,php-snmp,php-soap,php-tidy,php-xml,php-xmlrpc}
# RUN dnf -y install php80-php-pdo_mysql

RUN dnf module enable php:remi-8.0

RUN dnf -y install dnf-plugins-core
RUN dnf config-manager --set-enabled remi

# RUN dnf -y install httpd && dnf clean all
# ↓以下のコマンドからmod_sslを削除
RUN dnf -y install httpd httpd-tools httpd-devel && dnf clean all
# RUN systemctl start httpd
# RUN systemctl enable httpd

# 近喰さんのソースより（PHP8部分）
# RUN dnf install -y php php-bcmath php-cli php-common php-dba php-dbg php-devel php-embedded php-enchant php-fpm php-gd php-gmp php-imap php-intl php-ldap php-litespeed php-mbstring php-mcrypt php-mysqlnd php-odbc php-opcache php-pdo php-pear php-pgsql php-process php-pspell php-snmp php-soap php-tidy php-xml php-xmlrpc

# RUN yum -y install –-enablerepo=remi-php80 php80 php80-php php80-php-xml php80-php-xmlrpc php80-php-pecl-mcrypt php80-php-fpm php80-php-pecl-apcu php80-php-mbstring php80-php-gd php80-php-json php80-php-pecl-json-post php80-php-pdo php80-php-mysqlnd php80-php-pecl-mysql php80-php-opcache php80-php-pear php80-php-soap php80-php-intl php80-php-pear
# RUN yum -y install php80 php80-php php80-php-xml php80-php-xmlrpc php80-php-pecl-mcrypt php80-php-fpm php80-php-pecl-apcu php80-php-mbstring php80-php-gd php80-php-json php80-php-pecl-json-post php80-php-pdo php80-php-mysqlnd php80-php-pecl-mysql php80-php-opcache php80-php-pear php80-php-soap php80-php-intl php80-php-pear
# RUN yum -y install --enablerepo=remi,remi-php80 php80 php80-php-cli php80-php-common php80-php-devel php80-php-fpm php80-php-gd php80-php-mbstring php80-php-mysqlnd php80-php-pdo php80-php-pear php80-php-pecl-apcu php80-php80-php-soap php80-php-xml php80-php-xmlrpc 
# RUN yum -y install --enablerepo=remi,remi-php80 php80 php-cli php-common php-devel php-fpm php-gd php-mbstring php-mysqlnd php-pdo php-pear php-pecl-apcu php-soap php-xml php-xmlrpc 
# RUN yum -y install --enablerepo=remi,remi-php80
RUN dnf -y install zip unzip

# Composerのインストール
RUN curl -sS https://getcomposer.org/installer | php
RUN mv composer.phar /usr/local/bin/composer

WORKDIR /var/www/html

# EXPOSE 80

CMD ["/usr/sbin/httpd","-D","FOREGROUND"]