# 部署指南 - GitHub Pages

## 快速部署步骤

### 1. 准备GitHub仓库
1. 在GitHub上创建新仓库（或使用现有仓库）
2. 将所有游戏文件上传到仓库

### 2. 启用GitHub Pages
1. 进入仓库的 **Settings** 页面
2. 滚动到 **Pages** 部分
3. 在 **Source** 下选择 **Deploy from a branch**
4. 选择 **main** 分支和 **/ (root)** 文件夹
5. 点击 **Save**

### 3. 生成游戏图标（可选但推荐）
1. 在浏览器中打开 `create-icons.html`
2. 下载生成的图标文件
3. 将图标文件上传到仓库根目录

### 4. 访问你的游戏
- 部署完成后，游戏将在以下地址可用：
- `https://[你的GitHub用户名].github.io/[仓库名]/`

## iPhone用户安装指南

### 添加到主屏幕
1. 在iPhone Safari中打开游戏链接
2. 点击底部的**分享**按钮 📤
3. 滚动并选择**添加到主屏幕**
4. 自定义应用名称（如需要）
5. 点击**添加**

### 全屏游戏体验
- 从主屏幕启动游戏将自动全屏运行
- 无浏览器界面干扰
- 像原生应用一样的体验

## Android用户安装指南

### Chrome浏览器
1. 在Chrome中打开游戏链接
2. 点击右上角菜单（三个点）
3. 选择**添加到主屏幕**
4. 确认安装

### 其他浏览器
- 大多数现代Android浏览器都支持PWA安装
- 查找"添加到主屏幕"或"安装应用"选项

## 自定义域名（可选）

### 使用自定义域名
1. 在仓库根目录创建 `CNAME` 文件
2. 在文件中写入你的域名（如：`game.yourdomain.com`）
3. 在域名提供商处设置CNAME记录指向 `[用户名].github.io`

## 故障排除

### 常见问题

**问题：页面显示404错误**
- 检查仓库名称是否正确
- 确保文件已正确上传
- 等待几分钟让GitHub Pages生效

**问题：iPhone上按钮无响应**
- 确保使用Safari浏览器
- 检查JavaScript是否启用
- 尝试刷新页面

**问题：音效不工作**
- 在iPhone上首次访问时点击任意按钮激活音频
- 检查设备音量和静音开关
- 确保浏览器支持Web Audio API

**问题：游戏在移动设备上显示不正常**
- 检查viewport meta标签
- 确保CSS媒体查询正确
- 测试不同屏幕方向

### 性能优化建议

1. **启用HTTPS**：GitHub Pages自动提供HTTPS
2. **压缩资源**：考虑压缩CSS和JavaScript文件
3. **缓存策略**：Service Worker已配置缓存
4. **图片优化**：使用适当大小的图标文件

## 更新游戏

### 推送更新
1. 修改游戏文件
2. 提交并推送到GitHub
3. GitHub Actions将自动重新部署
4. 用户下次访问时将获得更新

### 版本管理
- 更新 `sw.js` 中的 `CACHE_NAME` 版本号
- 这将强制用户获取最新版本

## 监控和分析

### GitHub Pages统计
- 在仓库的 **Insights** > **Traffic** 查看访问统计

### 添加Google Analytics（可选）
```html
<!-- 在index.html的<head>中添加 -->
<script async src="https://www.googletagmanager.com/gtag/js?id=GA_MEASUREMENT_ID"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());
  gtag('config', 'GA_MEASUREMENT_ID');
</script>
```

## 备份和恢复

### 定期备份
- GitHub自动保存所有版本历史
- 考虑在其他平台创建镜像仓库

### 恢复到之前版本
```bash
git revert <commit-hash>
git push origin main
```

---

**祝你的游戏部署成功！** 🚀