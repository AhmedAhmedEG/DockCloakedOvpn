# CloakedOvpn
A docker compose project that hosts an OpenVPN server along with a Cloak server for hiding OpenVPN traffic.

# Usage (Server Side)
Just run Build.bat and it will automate the whole process, at the end it will wait a while for the OpenVPN server to initialize to download the client.ovpn file from it, it will be downloaded in the same directory as the project.

# Usage (Client Side)
1- Create a ckclient.json and paste those lines inside it:-

```
{
  "Transport": "direct",
  "ProxyMethod": "openvpn",
  "EncryptionMethod": "plain",
  "UID": "D21TMAQmz3qGMAgWzyDfFQ==",
  "PublicKey": "oVYWCZEzVfLh7uQ2QPY0L/0KAmlHutnFXsR433b1MQY=",
  "ServerName": "cloudflare.com",
  "NumConn": 4,
  "BrowserSig": "chrome",
  "StreamTimeout": 300
}
```

2- Download the cloak client v2.9.0 from the official repo and execute this command:-
```
ck-client-windows-amd64-v2.9.0.exe -c "ckclient.json" -s <server ip address> -l 1194
```

3- Run OpenVPN and load the client.ovpn generated by the server.
