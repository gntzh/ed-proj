---
title: 部署
summary: 对使用方法，构键技术，部署方法等作以说明。
---

# Deployment

部署时，由以下服务构成：

- 用户系统
- 任务系统
- 任务执行节点
- 动态任务调度节点
- SQL 数据库
- Redis 或 RabbitMQ 等任务队列
- 前端页面

## Docker

每个服务都提供了用于打包镜像的`Dockerfile`，都可以单独部署。

## Traefik

推荐部署方式：Traefik+docker-compose/docker-swarm/kubernetes，`docker`目录提供了 Traefik+docker-compose 的部署方式，并可以简单地转化为 docker-swarm 部署。

```
.
├── .env
├── .env.local
├── .env.tasks
├── .env.tasks.local
├── .gitignore
├── docker-compose.yaml
├── traefik-dynamic.toml
└── traefik.toml
```

默认部署方案中，SQL 数据库不容器化，在`.env`或命令行参数中提供`SQLALCHEMY_DATABASE_URI`环境变量，并设置默认管理员账户的密码、邮箱。

在根目录下运行：

```
docker-compose -f docker/docker-compose.yaml up -d
```

即可迅速拉起所有服务，其暴露的端点：

- `:8080/dashboard` Traefik 面板
- `/api/docs` 用户系统 API 文档
- `/tasks/docs` 任务系统 API 文档
- `/` 前端管理页面
