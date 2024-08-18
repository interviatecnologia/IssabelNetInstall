#Instalação Isaabel 4 - VPS 

#Kernel: 	Linux(x86_64)	3.10.0	1160.118.1.el7.x86_64

#Issabel: 	issabel	4.0.0

#asterisk16:	16.16.1	1.

yum update 

yum -y install wget 

wget -O - http://repo.issabel.org/issabel4-netinstall.sh | bash   ( CENTOS 7 )

#######################################################
#Instalação Isaabel 5 - VPS 

#Asterisk 18.19.0 or asterisk16:	16.16.1	1.

yum update 

yum -y install wget 

curl http://repo.issabel.org/issabel5-netinstall.sh | bash    ( ROCKY 8 )

###########################################################################

#mirrorlist.centos.org não existe mais.

#Do arquivo .repo:

Para resolver o problema, você pode atualizar em massa todos os arquivos .repo:

sed -i s/mirror.centos.org/vault.centos.org/g /etc/yum.repos.d/*.repo

sed -i s/^#.*baseurl=http/baseurl=http/g /etc/yum.repos.d/*.repo

sed -i s/^mirrorlist=http/#mirrorlist=http/g /etc/yum.repos.d/*.repo
