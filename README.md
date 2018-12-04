# Tor
Tor Service
Install systemd unit file for tor.service in /etc/systemd/system/tor.service<br />

[Unit]<br />
Description=Tor Proxy Service<br />
After=network.target<br />

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

