# Demo 1 

```
 2069  cd 01-Docker/
 2070  ls
 2071  mkdir 02-Docker-Commands
 2072  ls
 2073  docker version
 2074  systemctl status docker
 2075  docker container ls
 2076  docker run ubuntu echo "Hello World"
 2077  docker container ls
 2078  echo "Hello"
 2079  docker run ubuntu echo "Hello World - 2"
 2080  docker run ubuntu echo "Hello World - 3"
 2081  docker container ls
 2082  docker container ls -a
 2083  docker rm $(docker ps -qa)
 2084  docker run ubuntu echo "Hello World"
 2085  docker run ubuntu echo "Hello World - 2"
 2086  docker run ubuntu echo "Hello World - 3"
 2087  docker container ls
 2088  docker ps
 2089  docker ps -a
 2090  docker run ubuntu echo " Test - 1"
 2091  docker ps -a
 2092  systemctl status docker
 2093  systemctl status
 2094  systemctl status --all
 2095  systemctl status --help
 2096  docker rmi ubuntu
 2097  docker rm $(docker ps -qa)
 2098  docker rmi ubuntu
 2099  docker run ubuntu echo "Test - 1"
 2100  docker images
 2101  docker ps
 2102  docker ps -a
 2103  docker run ubuntu echo "Test - 2"
 2104  docker run ubuntu echo "Test - 3"
 2105  docker ps -a
 2106  docker run busybox echo "Test - 3"
 2107  docker ps -a
 2108  docker run busybox date
 2109  docker ps -a
 2110  docker run busybox dates
 2111  docker ps -a
```

# Demo 2
```
1380  docker pull busybox
 1381  docker pull ubuntu:16.04
 1382  docker pull ubuntu:20.04
 1383  docker images
 1384  docker run ubuntu cat /etc/os-release
 1385  docker run ubuntu:16.04 cat /etc/os-release
 1386  docker run ubuntu:20.04 cat /etc/os-release
 1387  docker ps
 1388  docker images
 1389  docker search --help
 1390  docker search ubuntu
 1391  curl -s -S "https://registry.hub.docker.com/v2/repositories/library/ubuntu/tags/"
 1392  docker images
 1393  docker run ubuntu:20.04 cat /etc/os-release
 1394  docker ps
 1395  docker container ls
 1396  docker container ls -a
 1397  docker ps
 1398  docker ps -a
 1399  docker run ubuntu:focal cat /etc/os-release
 1400  docker images
 1401  docker run ubuntu:focal cat /etc/os-release
 1402  docker run ubuntu:latest cat /etc/os-release

```

# Demo 3 

```
 2210  docker search ubuntu
 2211  ls
 2212  docker run -it ubuntu
 2213  docker ps
 2214  docker ps -a
 2215  docker start 345705aacda6
 2216  docker ps
 2217  docker attach 345705aacda6
 2218  docker ps
 2219  docker run -it ubuntu
 2220  docker ps
 2221  docker run -it --name job1 ubuntu
 2222  docker ps
 2223  docker run -it --name job1 ubuntu
 2224  docker run -it --name job2 ubuntu
 2225  docker ps
 2226  docker stop d87f405e96df
 2227  docker ps
 2228  docker ps -a
 2229  docker ps
 2230  docker ps -q
 2231  docker kill $(docker ps -q)
 2232  docker ps
 2233  docker ps -a
 2234  docker start job1
 2235  docker ps
 2236  docker attach job1
 2237  docker ps
 2238  docker ps -a
 2239  docker run -it --name job5 ubuntu
 2240  docker run -itd --name job6 ubuntu
 2241  docker run -itd --name job7 ubuntu
 2242  docker run -itd --name job8 ubuntu
 2243  docker ps
 2244  docker attach job8
 2245  docker ps
 2246  docker inspect job8
 2247  docker inspect --format '{{.Name}}' job8
 2248  docker inspect --format '{{.Name}} {{.State.Status}}' job8
 2249  docker inspect --format '{{.Name}} {{.State.Status}} {{.NetworkSettings.IPAddress}}' job8
 2250  docker inspect --format '{{.Name}} {{.State.Status}} {{.NetworkSettings.IPAddress}}' $(docker ps -q)
 2251  docker inspect --format '{{.Name}} {{.State.Status}} {{.NetworkSettings.IPAddress}}' $(docker ps -aq)
 2252  docker start job1
 2253  docker inspect --format '{{.Name}} {{.State.Status}} {{.NetworkSettings.IPAddress}}' $(docker ps -aq)

```

# Demo 4 

```
 2004  cd 03-Dockerfile/apache/v1 
 2012  vim Dockerfile
 2013  ls
 2014  docker build -t testapache:v1 .
 2015  docker images
 2027  docker build -t testapache:v1 .
 2028  docker images
 2029  docker ps
 2030  docker run -d --name mytest-apache-1 testapache:v1
 2031  docker ps
 2032  docker run -d --name mytest-apache-2 testapache:v1
 2033  docker run -d --name mytest-apache-3 testapache:v1
 2034  docker ps
 2035  docker inspect --format '{{.Name}} {{.State.Running}} {{.NetworkSettings.IPAddress}}'  $(docker ps -q)
 2036  curl 172.17.0.2
```
