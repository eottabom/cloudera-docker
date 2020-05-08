## Project Explanation

cloudera를 docker 환경으로 구성한 프로젝트  
설치된 항목 : cloudera manager, yarn, hadoop, zookeeper  
hadoop은 1개의 namenode와 3개의 datanode로 구성  
(namenode : headnode.cluster, datanode : datanode[1-3].cluster )  

## cloudera-docker Tree Structure

├── build.sh  
├── DataNodes  
│   ├── Dockerfile   
│   └── hyosungitx.crt  
├── docker_cluster_hosts  
├── docker-compose.yml  
├── HeadNodes  
│   ├── cloudera-manager.repo  
│   ├── create_databases.sql  
│   ├── Dockerfile  
│   ├── hyosungitx.crt  
│   └── my.cnf  
├── README.md  
└── up.sh  


## build

build 스크립트를 실행 시키면 docker-compose로 DataNodes, HeadNodes에 있는 Dockfile을 각각 빌드 하게 된다 

```{.bash}
sh build.sh
```

## start docker container
```{.bash}
sh up.sh
```

or

```{.bash}
docker-compose -f docker-compose.yml up -d
```


## stop docker container 
```{.bash}
docker stop {container_id}
```

## Tips
docker-compose down을 하게 되면 docker image 파일들이 전부다 삭제된다.  
docker-compose 내용을 수정하려면 각 docker container를 정지 시킨다.   