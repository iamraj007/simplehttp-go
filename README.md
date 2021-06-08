# Simplehttp-go App is written in Go Language 
As simple HTTP server written in golang for testing and demo in Docker
This app helps in demonstrating basic functionalities like e.g. sending back some request header info, the local IP address of the container and how to include the usage of environment variables.
 <img src="https://miro.medium.com/max/3200/1*g5TEj1R0X0CzTgvielr0Yw.png" width="250"  height="300"  align="left">
### What does it do?

This container starts a webserver on port 8000 and returns back 
- some header information
- the local ip address of the container
- the message provided by environment variable called _message_  

### Usage

To start _simplehttp_ web server , map local port 8000 into container and provide the env variable **message**:  
```bash
sudo docker run -e message=Hello -p 8000:8000 simplehttp
```  

Output from above call (your IP address will vary):  
```bash
GET / HTTP/1.1
Header["User-Agent"] = ["curl/7.59.0"]
Header["Accept"] = ["*/*"]
Host = "localhost:8000"
RemoteAddr = "172.17.0.1:36550"

===> local IP: "172.17.0.2"

Env message = Hello

```
