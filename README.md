# 三星堆 XR · sxd

基于 **PlayCanvas** 构建的「三星堆」主题 WebXR 体验，打包为可独立部署的静态站点。

## 内容

| 项 | 说明 |
|---|---|
| 标题 | 三星堆XR |
| 引擎 | PlayCanvas（`js/esm.mjs` + `js/index.mjs`） |
| 形态 | PWA（`manifest.json`，全天候全屏） |
| 资源 | `files/assets/` 下的 glb 模型、贴图与音频 |

## 目录

```
.
├── index.html          # 入口（含 XR 启动画面）
├── manifest.json       # PWA 清单
├── styles.css
├── config.json         # PlayCanvas 项目配置
├── 2626569.json        # 场景数据
├── js/
│   ├── esm.mjs         # PlayCanvas 引擎
│   └── index.mjs       # 应用打包产物
├── files/assets/       # 模型 / 贴图 / 音频
├── esm-scripts/        # 项目脚本
└── thumbs/             # PWA 图标
```

## 运行

纯静态站点，任意静态服务器即可：

```bash
python3 -m http.server 8080
# 打开 http://localhost:8080/
```

WebXR 需要 **HTTPS**（`localhost` 除外）。部署到任意支持 HTTPS 的静态托管即可在头显中打开。

## 部署

直接把整个目录内容作为站点根目录发布（Vercel / Netlify / nginx 均可）。

> 注意：`http2` 若对 `.mjs` 报错，请确保 MIME 映射包含
> `application/javascript js mjs;`

## 说明

- `.DS_Store` / `node_modules` / 日志已在 `.gitignore` 排除
- 打包产物中 `js/index.mjs` 约 3 MB（引擎 + 场景逻辑合并），属于正常体积

## 许可

未声明。若需开源请补充 LICENSE 文件。
