# Tor
Tor Service
Install systemd unit file for tor.service in /etc/systemd/system/tor.service

[Unit]
Description=Tor Proxy Service
After=network.target

[Service]
User=root
Type=simple
ExecStart=/usr/bin/tor -f /etc/tor/torrc
ExecReload=/usr/bin/kill -HUP $MAINPID
KillSignal=SIGINT
LimitNOFILE=8192
PrivateDevices=yes
Restart=always

[Install]
WantedBy=multi-user.target

