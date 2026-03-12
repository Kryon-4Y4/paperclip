# Paperclip Docker部署解决方案

## 📋 当前状态

### ✅ 已成功完成
1. **本地Node.js部署** - 服务正在运行，访问地址：http://127.0.0.1:3100
2. **环境配置** - `.env`文件已配置，包含安全密钥
3. **数据库迁移** - 26个迁移已自动应用
4. **依赖安装** - pnpm已安装999个包

### ❌ Docker构建问题
Docker构建因网络连接问题失败：
```bash
ERROR: failed to authorize: failed to fetch oauth token: Post "https://auth.docker.io/token":
dial tcp [2a03:2880:f112:83:face:b00c:0:25de]:443: connectex:
A connection attempt failed because the connected party did not properly respond
```

## 🚀 部署方案选择

### 方案A：继续使用现有本地部署（推荐）
服务已在本地成功运行，无需Docker：
```bash
# 服务状态检查
curl http://127.0.0.1:3100/api/health

# 访问地址
- Web界面: http://127.0.0.1:3100
- API: http://127.0.0.1:3100/api
- 健康检查: http://127.0.0.1:3100/api/health
```

**优点**：
- 已成功运行
- 开发调试方便
- 使用嵌入式PostgreSQL（无需额外配置）

### 方案B：解决Docker网络问题后部署

#### 方案B1：配置Docker镜像加速器（中国大陆用户）

**Windows Docker Desktop**：
1. 打开Docker Desktop设置
2. 进入`Docker Engine`选项卡
3. 在`registry-mirrors`中添加镜像加速器：

```json
{
  "registry-mirrors": [
    "https://docker.mirrors.ustc.edu.cn",
    "https://hub-mirror.c.163.com",
    "https://mirror.baidubce.com"
  ]
}
```

4. 点击"Apply & Restart"

**Linux/macOS**：
```bash
# 创建或编辑配置文件
sudo mkdir -p /etc/docker
sudo tee /etc/docker/daemon.json <<-'EOF'
{
  "registry-mirrors": ["https://docker.mirrors.ustc.edu.cn"]
}
EOF

# 重启Docker服务
sudo systemctl restart docker
```

#### 方案B2：修改基础镜像标签

已创建替代Dockerfile，使用更通用的`node:20-slim`：
```bash
# 使用替代配置构建
docker-compose -f docker-compose.alternative.yml build

# 启动服务
docker-compose -f docker-compose.alternative.yml up -d
```

#### 方案B3：手动拉取基础镜像
```bash
# 先拉取基础镜像
docker pull node:20-slim
docker pull postgres:17-alpine

# 再尝试构建
docker-compose build
```

### 方案C：使用快速启动Docker配置

使用嵌入式数据库，无需独立PostgreSQL容器：
```bash
# 使用快速启动配置
docker-compose -f docker-compose.quickstart.yml up -d
```

## 🔧 现有Docker配置说明

| 配置文件 | 用途 | 特点 |
|---------|------|------|
| `Dockerfile` | 主构建文件 | 多阶段构建，使用`node:lts-trixie-slim` |
| `Dockerfile.alternative` | 替代构建文件 | 使用`node:20-slim`，解决网络问题 |
| `docker-compose.yml` | 标准部署 | 包含PostgreSQL数据库 |
| `docker-compose.alternative.yml` | 替代部署 | 使用替代Dockerfile |
| `docker-compose.quickstart.yml` | 快速启动 | 嵌入式数据库，适合测试 |
| `.env.docker` | 环境变量模板 | Docker部署专用配置 |

## 🛠️ 详细部署步骤

### 步骤1：选择部署方案
根据网络情况选择上述方案之一。

### 步骤2：配置环境变量
确保`.env`文件包含必要的配置：
```bash
DATABASE_URL=postgres://paperclip:paperclip@localhost:5432/paperclip
PORT=3100
SERVE_UI=false
BETTER_AUTH_SECRET="q68ElYk8pD7gTu6tkAdzK1CHJX+RKXGcmzu33hADUCE="
PAPERCLIP_PUBLIC_URL="http://localhost:3100"
```

### 步骤3：构建和启动

**方案A（本地）**：
```bash
# 停止现有服务（如果需要）
claude-task-stop b3uispyzd

# 重新启动
pnpm dev
```

**方案B（标准Docker）**：
```bash
# 配置镜像加速器后
docker-compose up -d
```

**方案C（快速启动）**：
```bash
docker-compose -f docker-compose.quickstart.yml up -d
```

### 步骤4：验证部署
```bash
# 健康检查
curl http://localhost:3100/api/health

# 查看服务状态
docker-compose ps
```

## 🐛 故障排除

### 问题1：网络连接超时
**症状**：`dial tcp [IPv6地址]:443: connectex`
**解决方案**：
1. 配置镜像加速器（方案B1）
2. 使用替代Dockerfile（方案B2）
3. 临时禁用IPv6：
   ```bash
   # Windows PowerShell（管理员）
   netsh interface ipv6 set state "以太网" disabled

   # 测试后重新启用
   netsh interface ipv6 set state "以太网" enabled
   ```

### 问题2：端口冲突
**症状**：`Bind for 0.0.0.0:3100 failed: port is already allocated`
**解决方案**：
```bash
# 停止本地服务
claude-task-stop b3uispyzd

# 或修改docker-compose端口映射
# 编辑docker-compose.yml，修改为：
ports:
  - "3101:3100"  # 主机3101端口映射到容器3100端口
```

### 问题3：数据库连接失败
**症状**：`Error: DATABASE_URL is required`
**解决方案**：
```bash
# 确保环境变量已设置
cat .env

# 或使用快速启动方案（嵌入式数据库）
docker-compose -f docker-compose.quickstart.yml up -d
```

### 问题4：构建缓存问题
**症状**：构建使用旧缓存
**解决方案**：
```bash
# 清理构建缓存
docker-compose build --no-cache

# 或完全清理
docker system prune -a
docker volume prune
```

## 📊 方案对比

| 特性 | 本地部署 | Docker标准 | Docker快速启动 |
|------|----------|------------|----------------|
| 数据库 | 嵌入式PostgreSQL | 独立PostgreSQL容器 | 嵌入式数据库 |
| 隔离性 | 低 | 高 | 中 |
| 启动速度 | 快 | 中等 | 快 |
| 生产就绪 | 开发环境 | 生产环境 | 测试环境 |
| 数据持久化 | 本地目录 | Docker卷 | 本地目录/卷 |
| 网络要求 | 无 | 需要下载镜像 | 需要下载镜像 |

## 🔄 数据迁移

### 从本地部署迁移到Docker
```bash
# 1. 备份本地数据
cp -r D:\home\paperclip\.paperclip\instances\default\db ./backup/

# 2. 启动Docker服务
docker-compose up -d

# 3. 恢复数据（如果需要）
# 联系技术支持获取详细迁移步骤
```

### Docker数据备份
```bash
# 备份数据库
docker-compose exec db pg_dump -U paperclip paperclip > paperclip-backup.sql

# 备份Paperclip数据卷
docker run --rm -v paperclip_paperclip-data:/data -v $(pwd):/backup alpine tar czf /backup/paperclip-data.tar.gz /data
```

## 🚨 安全注意事项

1. **生产部署**：
   - 使用独立PostgreSQL实例
   - 配置HTTPS（通过反向代理如Nginx）
   - 定期更新`BETTER_AUTH_SECRET`
   - 启用防火墙规则

2. **环境变量安全**：
   - 不要在代码中硬编码密钥
   - 使用`.env`文件（不要提交到版本控制）
   - 生产环境使用密钥管理服务

3. **网络隔离**：
   - Docker使用独立网络
   - 限制容器间通信
   - 仅暴露必要端口

## 📈 监控和维护

### 日常维护
```bash
# 查看服务状态
docker-compose ps

# 查看日志
docker-compose logs -f server

# 资源使用
docker stats

# 更新服务
docker-compose pull
docker-compose up -d --build
```

### 监控指标
```bash
# API健康状态
curl http://localhost:3100/api/health

# 数据库连接数
docker-compose exec db psql -U paperclip -d paperclip -c "SELECT count(*) FROM pg_stat_activity;"

# 容器资源限制
docker inspect paperclip-server | grep -A 5 "HostConfig"
```

## 💡 最佳实践建议

1. **开发环境**：使用本地部署或Docker快速启动
2. **测试环境**：使用Docker标准部署
3. **生产环境**：
   - 使用独立数据库服务器
   - 配置负载均衡
   - 设置监控告警
   - 定期备份

4. **版本控制**：
   - 将Docker配置纳入版本控制
   - 使用语义化版本标签
   - 维护更新日志

## 🆘 获取帮助

1. **检查服务状态**：
   ```bash
   # 本地服务
   curl http://127.0.0.1:3100/api/health

   # Docker服务
   docker-compose logs --tail=50 server
   ```

2. **查看错误日志**：
   ```bash
   # 本地日志
   tail -f /home/paperclip/.paperclip/instances/default/logs/server.log

   # Docker日志
   docker-compose logs -f
   ```

3. **重置环境**：
   ```bash
   # 本地重置
   rm -rf data/pglite
   pnpm dev

   # Docker重置
   docker-compose down -v
   docker-compose up -d
   ```

---

**推荐方案**：由于本地部署已成功运行，建议继续使用本地部署进行开发和测试。如需生产环境部署，在解决网络问题后使用Docker标准部署方案。

**当前状态**：✅ 服务已在本地成功运行，可通过 http://127.0.0.1:3100 访问。