Instalação Isaabel 4 - VPS 

Kernel: 	Linux(x86_64)	3.10.0	1160.118.1.el7.x86_64

Issabel: 	issabel	4.0.0

asterisk16:	16.16.1	1.

#yum update 

#yum -y install wget 

#wget -O - http://repo.issabel.org/issabel4-netinstall.sh | bash

mirrorlist.centos.org não existe mais.

Do arquivo .repo:

# The mirror system uses the connecting IP address of the client and the
# update status of each mirror to pick mirrors that are updated to and
# geographically close to the client.  You should use this for CentOS updates
# unless you are manually picking other mirrors.
#
# If the mirrorlist= does not work for you, as a fall back you can try the
# remarked out baseurl= line instead.
Para resolver o problema, você pode atualizar em massa todos os arquivos .repo:

sed -i s/mirror.centos.org/vault.centos.org/g /etc/yum.repos.d/*.repo
sed -i s/^#.*baseurl=http/baseurl=http/g /etc/yum.repos.d/*.repo
sed -i s/^mirrorlist=http/#mirrorlist=http/g /etc/yum.repos.d/*.repo
