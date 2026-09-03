# 口岸网点经营看板

超长期经营任务的方案总入口。**网址一经确定永久不变**，内容持续更新。

## 目录结构

```
index.html              总入口页（唯一需要记的网址）
versions.json           各方案的最后更新日期（由发布脚本自动维护）
rebate-plan/            口岸门店量返方案
debt-roadmap/           债务重组执行总路线图
cashflow-tracker/       90 天现金流实测记账
```

## 网址

- 主地址（GitHub Pages）：`https://<用户名>.github.io/<仓库名>/`
- 备用 1（jsDelivr，国内加速）：`https://cdn.jsdelivr.net/gh/<用户名>/<仓库名>@main/`
- 备用 2（jsDelivr 备用节点）：`https://fastly.jsdelivr.net/gh/<用户名>/<仓库名>@main/`

三个地址内容完全同步，任何一个打不开就换另一个。

## 更新方式

不要直接改这里的文件。**改工作区根目录的主文件，然后跑发布脚本**：

```bash
python publish.py --push -m "更新说明"
```

脚本会：同步主文件 → 生成 versions.json → git commit → git push。
对外网址不变，用户无需做任何事。

首次部署才需要指定账号：

```bash
python publish.py --user <用户名> --repo <仓库名> --push -m "首次发布"
```

## 注意事项

- 记账工具的数据存在浏览器本地并按网址隔离。换网址后第一次打开，
  需要在工具里输入同步码 `260901` 从云端恢复。
- 子页面一律用相对路径引用，这样三个备用地址都能正常工作。
- jsDelivr 有缓存，push 后主地址可能延迟几分钟才更新；GitHub Pages 通常 1 分钟内生效。
