# Tor
Tor Service
Install systemd unit file for tor.service in /etc/systemd/system/tor.service<br />

[Unit]<br />
Description=Tor Proxy Service<br />
After=network.target<br />
<br />
[Service]<br />
User=root<br />
Type=simple<br />
ExecStart=/usr/bin/tor -f /etc/tor/torrc<br />
ExecReload=/usr/bin/kill -HUP $MAINPID<br />
KillSignal=SIGINT<br />
LimitNOFILE=8192<br />
PrivateDevices=yes<br />
Restart=always<br />
<br />
[Install]<br />
WantedBy=multi-user.target<br />

