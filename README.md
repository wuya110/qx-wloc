# qx-wloc · Apple 网络定位修改（QX 可用镜像版）

修改 Apple 网络定位（gs-loc）返回的坐标：在地图 App 里长按选个点，你的定位就飞过去了。

原项目：[jasonniceo/apple-wloc](https://github.com/jasonniceo/apple-wloc)（作者 jasonniceo，2026-09-13 发布）。
本仓库为可用镜像：原作者的 fork 订阅（Yu9191/wloc）仓库已被删除，订阅链接 404；
这里把两份脚本镜像到本仓库，`wloc.conf` 里的脚本地址已指向本仓库，订阅即用。

## 安装（Quantumult X）

`[rewrite_remote]` 加一行：

```
https://raw.githubusercontent.com/wuya110/qx-wloc/main/wloc.conf, tag=定位修改, enabled=true
```

或把 `wloc.conf` 里的 `[rewrite_local]` / `[mitm]` 段直接贴进本地配置。

再装两个 iCloud 快捷指令：

- 设置地理位置：https://www.icloud.com/shortcuts/a82717d8fdad4e6280866fcf911173f7
- 清理恢复位置：https://www.icloud.com/shortcuts/f42632d406504f24a2cd163af4fe012f

用法：地图 App（苹果地图/高德）长按选点 → 共享 → "wloc 设置地理位置"。

## 已知的坑

- iOS 26/27 的 locationd 会把真实定位缓存在内存里长期复用：装完没变化就**重启手机**，飞行模式/开关定位清不掉。
- 只改网络定位（WiFi/基站），不改 GPS；GPS 信号强时 iOS 可能忽略网络定位结果。
- 需要 MitM 开启并信任 `gs-loc.apple.com`、`gs-loc-cn.apple.com` 的证书。

## 致谢

全部逻辑来自原作者 jasonniceo，本仓库仅做镜像与地址修正，无二次修改。
