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
