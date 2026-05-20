#### BASE INSTALLATION

apt update

curl -Lso - $(curl https://cdn.cribl.io/dl/latest-arm64) | tar zxv

useradd -r -m -d /opt/cribl cribl

chown -R cribl. /opt/cribl
/opt/cribl/bin/cribl boot-start enable -m systemd -u cribl
su - cribl -c '/opt/cribl/bin/cribl start'

echo -e "alias cribl=' /opt/cribl/bin/cribl'" >> /root/.bashrc
source /root/.bashrc

timedatectl set-timezone Europe/Berlin
