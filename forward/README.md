SSH Forward
===========
```
sudo python rforward.py test.eu:22 -r 80 -p 8080 -r test.eu:80 --user root --key secret_key_file_name
```

The example takes the remote port 80 and makes it available locally as 8080. The non-keyword argument above is test.eu:22 . It connects to the ssh server at test.eu running at port 22.

The -p indicates the local port for the tunnel.

The -r indicates the host and port that the remote server is going to forward to. 
The server indicated by -r may be different than the server you are connecting

```
python rforward.py test.eu:22 -r 80 -p 8080 -r anotherhost.test.eu:80 --user root --key key_file
```

SSH equivalent tunnel:

ssh -L 8080:localhost:80 root@test.eu

Usage
=====

Server
------
```
sudo python rforward.py test.eu:<SSH PORT> -r <REMOTE PORT> -p <LOCAL PORT TO FORWARD TO LOCAL PORT> -r <REMOTE HOST>:<REMOTE PORT> --user <USER> --key <KEY> -P

sudo python rforward.py test.eu:22 -r 22 -p 2222 -r 127.0.0.1 --user root --key /root/.ssh/id_rsa.pub -P
```

```
sudo python rforward.py test.eu:22 -p 2222 -r 127.0.0.1:22 --user root --key /root/.ssh/id_rsa.pub -P

Connected!  Tunnel open (u'127.0.0.1', 44657) -> ('138.82.210.69', 1291) -> ('127.0.0.1', 22)
```
