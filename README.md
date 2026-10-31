# 同一时刻 · 世界历史地球仪

一个中文交互历史地球仪。拖动旋转地球，在同一年比较世界不同地区，也能固定一座城市，沿时间阅读它的变化。

[在线试玩（GitHub Pages）](https://wanglu2016.github.io/world-history-globe/) · [备用试玩地址](https://world-history-atlas-wanglu.lithegrove1.chatgpt.site/)

## 已有内容

- 公元前3000年至2010年的14个精选历史切片。
- 可旋转、缩放的地球，以及全球同屏的平面地图。
- 历史政权与文化区域、25个地点沿革、42张同期观察卡片。
- 中文搜索、切片播放、图层开关与交换网络示意。
- 地图和D3随项目提供；网页主体不依赖外部CDN。

## 本地运行

安装Python后，在仓库目录执行：

```bash
python -m http.server 8000 --directory docs
```

在浏览器打开 `http://localhost:8000`。地图通过fetch读取，需要HTTP服务；不能直接双击HTML文件运行。

## GitHub Pages

网站文件位于 `docs/`。仓库的GitHub Pages可选择从默认分支的 `/docs` 目录发布。

## 文件结构

- `docs/index.html`：页面与资料说明。
- `docs/app.js`：投影、地球交互、搜索、图层和沿革浏览。
- `docs/data.js`：中文叙述、城市与历史节点。
- `docs/style.css`：页面样式。
- `docs/assets/maps/`：14份历史GeoJSON。
- `docs/assets/land.json`：现代海岸线陆地底图。

## 数据来源与许可

- 历史区域：André Ourednik 的 [Historical Basemaps](https://github.com/aourednik/historical-basemaps)，GPL-3.0。
- 现代陆地：[Natural Earth](https://www.naturalearthdata.com/)，公共领域。
- 可视化：[D3](https://d3js.org/)，ISC；完整声明在 `docs/assets/D3-LICENSE.txt`。
- 本应用源码与原创叙述按GPL-3.0提供，完整文本见 `LICENSE`。

城市与时代卡片包含博物馆、联合国教科文组织等资料的延伸链接。

## 阅读边界与已知问题

这是探索原型，未经逐区域学术审校。上游数据同时包含政权、族群和文化区域，不应把所有色块理解为现代主权国家或直接控制范围。

本版订正部分过时名称，并暂时不绘制已发现的严重跨期多边形，例如1200年仍标“辽”、1400年中国仍标“蒙古大汗国”的区域。没有据此重新测绘历史疆域。原始地图文件保留，修订在 `app.js` 的 `corrected` 中执行。

城市点为近似定位，不等同于历代城址边界。海岸线采用现代底图。交换路线只表示网络方向和节点，不表示唯一道路。切片之间不作逐年疆域插值；2010年切片也不是实时世界地图。
