# Tor
Tor Service"\n"
Install systemd unit file for tor.service in /etc/systemd/system/tor.service "\n"

[Unit]"\n"
Description=Tor Proxy Service"\n"
After=network.target"\n"

[Service]"\n"
User=root"\n"
Type=simple"\n"
ExecStart=/usr/bin/tor -f /etc/tor/torrc"\n"
ExecReload=/usr/bin/kill -HUP $MAINPID"\n"
KillSignal=SIGINT"\n"
LimitNOFILE=8192"\n"
PrivateDevices=yes"\n"
Restart=always"\n"

[Install]"\n"
WantedBy=multi-user.target"\n"

