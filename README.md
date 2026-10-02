# 云间 · Cloudfall

Three.js 0.169.0 单页体素自然景观。无需 npm 安装或构建，通过 jsDelivr CDN 加载 Three.js / OrbitControls（需要联网）。

## 本地预览

在项目目录运行：

```sh
python -m http.server 8080
```

浏览器打开 http://localhost:8080 。推荐通过 HTTP 服务预览，而非 file://。

## 交互

- 初始即展示场景全貌，默认缓慢自动环绕。
- 鼠标拖动 / 单指拖动旋转；滚轮 / 双指捏合缩放。
- 自动环绕按钮可暂停或恢复运镜。
- 晨昏切换按钮切换清晨 / 金色暮光。
- 回到全景按钮重置镜头。

## 实现

- 固定种子的程序化多峰地形，平滑 value noise / fBm 扰动，草地、岩石、积雪高度分层。
- 仅生成暴露的柱体外壳，所有体素均使用 InstancedMesh 批量渲染。
- 南坡阶梯式水道与下落水块，山脚水潭、循环白色飞溅粒子。
- 独立实例化体素云团，随时间漂移，使用正常深度测试与山体互相遮挡。
- 体素松树、阔叶树和野花；半球光、方向光、阴影、雾气。
- 限制像素比；持续低于 30 FPS 时自动降低渲染分辨率，必要时关闭阴影。
- FPS 显示为实际浏览器帧率；硬件 / 软件渲染性能差异较大，不承诺所有设备都达到 30 FPS。
- WebGL 不支持、CDN 加载失败或上下文丢失时显示错误提示。

## 在线地址

https://yukikazechan.github.io/voxel-cloudfall-landscape/

仓库：https://github.com/yukikazechan/voxel-cloudfall-landscape
