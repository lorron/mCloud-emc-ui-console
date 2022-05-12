# 运行
### 部署前端
- 启动容器：
- 替换${project_home}为真实路径
```
docker-compose -f ${project_home}/docker/compose/mcloud/ui.yml up -d
```
- 停止/删除容器：
```
docker-compose -f ${project_home}/docker/compose/mcloud/env.base.yml stop
docker-compose -f ${project_home}/docker/compose/mcloud/env.base.yml down
```
- 示例：
```
docker-compose -f D:/JHB-Project/mcloud/mCloud-emc-ui-console/docker/compose/mcloud/env.base.yml up -d
docker-compose -f D:/JHB-Project/mcloud/mCloud-emc-ui-console/docker/compose/mcloud/env.base.yml down
```
