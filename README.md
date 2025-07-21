# 应用展示网站

这是一个多应用展示网站，支持在同一域名下托管多个应用的介绍页面。

## 网站结构

```
/
├── index.html                    # 主页，展示所有应用
├── apple-app-site-association    # 全站 App Clip 配置
├── CNAME                         # GitHub Pages 域名配置
└── sudoku/                       # 数独应用文件夹
    ├── index.html                # 数独应用主页
    ├── play.html                 # 在线游戏页面
    ├── clip.html                 # App Clip 页面
    ├── privacy-policy.html       # 隐私政策
    ├── terms-of-service.html     # 服务条款
    ├── app-icon.png              # 应用图标
    └── clip/                     # App Clip 相关资源
```

## 添加新应用

要添加新的应用，请按照以下步骤：

1. 在根目录创建新的应用文件夹（如 `/newapp/`）
2. 将应用相关的所有文件放入该文件夹
3. 更新文件中的路径引用，添加应用文件夹前缀
4. 在根目录的 `index.html` 中添加新应用的卡片
5. 如需支持 App Clip，更新 `apple-app-site-association` 文件

## 路径规范

- 所有资源文件使用绝对路径，包含应用文件夹前缀
  - 正确: `/sudoku/app-icon.png`
  - 错误: `app-icon.png` 或 `/app-icon.png`
- 内部链接也需要包含应用文件夹前缀
  - 正确: `/sudoku/play`
  - 错误: `/play`

## 部署说明

1. 确保 CNAME 文件包含正确的域名
2. 将整个项目推送到 GitHub
3. 在仓库设置中启用 GitHub Pages
4. 等待 DNS 生效

## 注意事项

- `apple-app-site-association` 文件必须放在网站根目录
- 该文件不能有文件扩展名，且必须是有效的 JSON
- App Clip 的路径配置需要包含应用文件夹前缀