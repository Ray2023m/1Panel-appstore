# 1Panel-appstore

### 声明
#### 整理来源于网上资源,集成个人常用应用,方便个人使用.
     来源于:https://github.com/okxlin/appstore;
           https://github.com/arch3rPro/1Panel-Appstore;
           https://github.com/willow-god/appstore;
           https://github.com/QYG2297248353/appstore-1panel;特此感谢!
   
### 🚀 使用方法

#### 📋 添加脚本到 1Panel 计划任务
```bash
#!/bin/bash
set -euo pipefail
IFS=$'\n\t'

# 配置
REPO_URL="https://github.com/Ray2023m/1Panel-appstore.git"
TMP_DIR="/tmp/1panel_appstore_tmp"
DEST_DIR="/opt/1panel/resource/apps/local"

echo "🧹 清理旧的临时目录..."
rm -rf "$TMP_DIR"

echo "📥 克隆仓库: $REPO_URL"
git clone --depth=1 "$REPO_URL" "$TMP_DIR/appstore"

echo "📂 更新本地应用商店数据..."
mkdir -p "$DEST_DIR"
cp -rf "$TMP_DIR/appstore/apps/"* "$DEST_DIR/"

echo "🧹 清理临时目录..."
rm -rf "$TMP_DIR"

echo "✅ 应用商店数据已更新完成"
```
