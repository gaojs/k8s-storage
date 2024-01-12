# 介绍
在k8s集群中，部署mysql, redis, etcd等各种存储服务的方法。

## mysql
### 创建Deployment
创建Deployment：kubectl create -f mysql-deployment.yaml
查看ReplicaSet：kubectl get rs -n  storage
查看POD：kubectl get pod -n  storage
### 创建服务，发布端口
创建服务：kubectl create -f mysql-svc.yaml
查看服务：kubectl get svc -n  storage -o wide

## redis

## etcd

## kafka