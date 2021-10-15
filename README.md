### Proxy-Tor

A simple Tor Proxy to route traffic through. If you wish to browse the web with TOR, I recommend using the Tor Browser. 

Built on alpine:latest

Instructions: 

1. git clone https://github.com/alexrf45/Prox-Tor.git

2. cd Prox-Tor

3. docker build -t prox-tor .

4. docker run --rm --detach --name tor --publish 9050:9050 fonalex45/project-repo-1:prox-tor

4. verify traffic is running through tor:

	> curl https://check.torproject.org/api/ip
    {"IsTor":false,"IP":"49.30.XX.XX"}

    > curl --socks5 127.0.0.1:9050 https://check.torproject.org/api/ip
    {"IsTor":true,"IP":"185.220.XXX.XXX"}