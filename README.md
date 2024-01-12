# 介绍
在k8s集群中，部署mysql, redis, etcd等各种存储服务的方法。

## mysql
参考：https://summerking1.github.io/pages/84a183
### 创建PVC
创建PVC：kubectl apply -f mysql-pvc.yaml
查看PVC：kubectl get pvc -n  storage
### 创建Deployment
创建Deployment：kubectl create -f mysql-deployment.yaml
查看ReplicaSet：kubectl get rs -n  storage
查看POD：kubectl get pod -n  storage
### 创建服务，发布端口
创建服务：kubectl create -f mysql-svc.yaml
查看服务：kubectl get svc -n  storage -o wide
验证服务：用navicat连接集群中任意节点的IP，端口（30336），用户名（root），密码（123456）。

## redis
参考：https://juejin.cn/post/6947955959268376590
### 创建PVC
创建PVC：kubectl apply -f redis-pvc.yaml
查看PVC：kubectl get pvc -n  storage
### 创建Deployment
创建Deployment：kubectl apply -f redis-deployment.yaml
查看ReplicaSet：kubectl get rs -n  storage
查看POD：kubectl get pod -n  storage
### 创建服务，发布端口
创建服务：kubectl apply -f redis-svc.yaml
查看服务：kubectl get svc -n  storage -o wide
验证服务：用redis-cli连接集群中任意节点的IP（redis-cli -h 10.0.5.184 -p 30379），设置（set k v），获取（get k）。

## etcd

## kafka