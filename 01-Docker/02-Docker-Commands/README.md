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


# Demo 5 

```
2063  docker images
 2064  ls
 2065  cp -rf v1 v2
 2066  ls
 2067  cd v2/
 2068  ls
 2069  vim index.html
 2070  ls
 2071  vim Dockerfile
 2072  ls
 2073  docker build -t testapache:v2 .
 2074  docker images
 2075  docker run -d --name mytest-apache-4 testapache:v2
 2076  docker ps
 2077  docker inspect --format '{{.Name}} {{.State.Running}} {{.NetworkSettings.IPAddress}}'  $(docker ps -q)
 2078  curl 172.17.0.4
 2079  curl 172.17.0.5
 2080  curl -vvv 172.17.0.5
 2081  ls
 2082  cd ..
 2083  ls
 2084  cp -rf v2 v3
 2085  ls
 2086  cd v3/
 2087  ls
 2088  vim index.html
 2089  ls
 2090  vim ports.conf
 2091  ls
 2092  vim Dockerfile
 2093  ls
 2094  docker build -t testapache:v3 .
 2095  docker images
 2096  docker run -d --name mytest-apache-5 testapache:v3
 2097  docker inspect --format '{{.Name}} {{.State.Running}} {{.NetworkSettings.IPAddress}}'  $(docker ps -q)
 2098  curl 172.17.0.5
 2099  curl -v 172.17.0.5
 2100  curl -v 172.17.0.6
 2101  docker ps
 2102  curl -v 172.17.0.6:9090
 2103  docker ps
 2104  ls
 2105  cd ..
 2106  ls
 2107  cp -rf v3 v4
 2108  ls
 2109  cd v4/
 2110  ls
 2111  vim ports.conf
 2112  ls
 2113  vim index.html
 2114  ls
 2115  vim Dockerfile
 2116  ks
 2117  ls
 2118  docker build -t testapache:v4 .
 2119  docker run -d --name mytest-apache-6 testapache:v4
 2120  docker ps
 2121  curl -v 172.17.0.5
 2122  curl -v 172.17.0.6
 2123  curl -v 172.17.0.7
 2124  curl -v 172.17.0.7:8080
 2125  docker ps
 2126  ls
 2127  cd ..
 2128  ls
 2129  cp -rf v4 v5
 2130  ls
 2131  cd v5/
 2132  ls
 2133  vim Dockerfile
 2134  ls
 2135  docker build -t testapache:v5 .
 2136  docker run -d --name mytest-apache-7 testapache:v5
 2137  docker ps
 2138  curl -v 172.17.0.8
 2139  curl -v 172.17.0.8:9090
 2140  curl -v 172.17.0.8:8080
 2141  curl 172.17.0.8:8080
 2142  curl 172.17.0.8:8080/info.html
 2143  date
 2144  ls
 2145  cd ..
 2146  ls
 2147  cp -rf v5 v6
 2148  ls
 2149  cd v6/
 2150  ls
 2151  vim Dockerfile
 2152  ls
 2153  mv Dockerfile amit-file
 2154  ls
 2155  docker build -t testapache:v6 .
 2156  cat amit-file
 2157  docker build -t testapache:v6 -f amit-file .
 2158  docker images
 2159  docker run -d --name mytest-apache-8 testapache:v6
 2160  docker ps

```


# Demo 6

```
 2191  docker network ls
 2192  docker network inspect 07c49b12e657
 2193  docker kill  $(docker ps -q)
 2194  docker network inspect 07c49b12e657
 2195  docker run -d --name mytest-apache-9 testapache:v6
 2196  docker ps
 2197  docker network inspect 07c49b12e657
 2198  docker run -d --name mytest-apache-10 testapache:v6
 2199  docker network inspect 07c49b12e657
 2200  ip addr
 2201  curl 172.17.0.2
 2202  curl 172.17.0.2:8080
 2203  route -n
 2204  docker images
 2205  docker run -d --test-nw-1 amitvashist7/network-multitool
 2206  docker run -d --name test-nw-1 amitvashist7/network-multitool
 2207  docker run -d --name test-nw-2 amitvashist7/network-multitool
 2208  docker ps
 2209  docker exec -it test-nw-2 ip addr
 2210  ip addr
 2211  docker exec -it test-nw-2 route -n
 2212  docker exec -it test-nw-2 ip addr
 2213  route -n
 2214  ip addr
 2215  netstat -tulnp
 2216  docker run -d --name mytest-apache-12 -p 8080:8080  testapache:v6
 2217  docker ps
 2218  netstat -tulnp
 2219  docker run -d --name mytest-apache-13 -p 8080:8080  testapache:v6
 2220  docker run -d --name mytest-apache-14 -p 8081:8080  testapache:v6
 2221  docker ps
 2222  netstat -tulnp
 2223  docker run -d --name mytest-apache-15 -P   testapache:v6
 2224  docker ps
 2225  netstat -tulnp
 2226  systemctl status docker
 2227  docker run -d --name mytest-apache-17 -P   testapache:v5
 2228  docker ps
 2229  systemctl status docker
```

# Demo 7

```
2239  docker ps
 2240  docker kill $(docker ps -q)
 2241  docker rm $(docker ps -qa)
 2242  docker images
 2243  docker run -d --name nw-test-1-default amitvashist7/network-multitool
 2244  docker ps
 2245  docker exec -it nw-test-1-default ip addr
 2246  docker network ls
 2247  docker network ls 07c49b12e657
 2248  docker network inspect 07c49b12e657
 2249  docker network create --help
 2250  docker network create --driver bridge --subnet 172.28.0.0/16 --ip-range 172.28.5.0/24 --gateway 172.28.5.254 mybr0
 2251  docker network ls
 2252  docker network inspect mybr0
 2253  docker exec -it nw-test-2-default ip addr
 2254  docker run -d --name nw-test-2-default amitvashist7/network-multitool
 2255  docker exec -it nw-test-2-default ip addr
 2256  docker exec -it nw-test-1-default ip addr
 2257  docker run -d --name nw-test-1-mybr0 --network mybr0 amitvashist7/network-multitool
 2258  docker ps
 2259  docker exec -it nw-test-1-mybr0 ip addr
 2260  docker run -d --name nw-test-2-mybr0 --network mybr0 amitvashist7/network-multitool
 2261  docker exec -it nw-test-2-mybr0 ip addr
 2262  docker exec -it nw-test-2-mybr0 ping -c2 google.com
 2263  docker image
 2264  docker images
 2265  docker run -d --name nw-test-3-mybr0 --network mybr0 -P testapache:v6
 2266  docker ps
 2267  docker exec -it nw-test-3-mybr0 ping -c2 google.com
 2268  docker exec -it nw-test-2-mybr0 ping -c2 google.com
 2269  docker exec -it nw-test-2-mybr0 route -n
 2270  docker network ls
 2271  docker network inspect mybr0
 2272  ip addr
 2273  systemctl status docker
 2274  ip addr
 2275  route -n
 2276  ls
 2277  netstat -tulnp
 2278  netstat -tulnp| grep -i 80
 2279  docker images
 2280  docker run -d --name test-1 testapache:v1
 2281  docker ps
 2282  docker inspect --format '{{.Name}} {{.State.Running}} {{.NetworkSettings.IPAddress}}'  $(docker ps -q)
 2283  curl 172.17.0.4
 2284  netstat -tulnp| grep -i 80
 2285  docker run -d --name test-2 -p 80:80  testapache:v1
 2286  netstat -tulnp| grep -i 80
 2287  docker ps
 2288  ip addr
 2289  systemctl  status docker
 2290  docker ps
 2291  netstat -tulnp
 2292  ls
 2293  docker ps
 2294  docker kill $(docker ps -q)
 2295  docker ps
 2296  docker ps -a
 2297  docker start nw-test-1-default
 2298  docker start nw-test-1-mybr0
 2299  docker ps
 2300  docker exec -it nw-test-1-mybr0  ip addr
 2301  docker exec -it nw-test-1-default  ip addr
 2302  docker network  ls
 2303  docker run -d --name nw-test-3-host --network host amitvashist7/network-multitool
 2304  docker exec -it nw-test-1-mybr0  ip addr
 2305  docker exec -it nw-test-1-default  ip addr
 2306  docker exec -it nw-test-3-host  ip addr
 2307  docker network ls
 2308  docker run -d --name nw-test-3-none --network none amitvashist7/network-multitool
 2309  docker exec -it nw-test-1-default  ip addr
 2310  docker exec -it nw-test-3-host  ip addr
 2311  docker exec -it nw-test-1-none  ip addr
 2312  docker ps
 2313  docker exec -it nw-test-3-none  ip addr
 2314  docker attach nw-test-3-none
 2315  docker exec -it nw-test-3-none  bash
 2316  docker exec -it nw-test-3-none  sh
 2317  docker exec -it nw-test-3-none  /bin/bash
 2318  docker ps
 2319  docker start nw-test-3-none
 2320  docker exec -it nw-test-3-none  sh
 2321  docker run -d --name nw-test-3 -P  amitvashist7/network-multitool
 2322  docker ps
 2323  ls
 2324  history
 2325  docker ps
 2326  docker exec -it nw-test-1-default ip addr
 2327  curl 172.17.0.2
 2328  docker exec -it nw-test-3-none ip addr
```
