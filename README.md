# 🔍 Sovitrix - GitHub Actions Runner 侦察工具

一键扒光 GitHub Actions 服务器的配置：CPU、GPU、内存、磁盘、网络、公网 IP、User-Agent……全给你。

## 使用方法

1. **Fork** 或 Clone 本仓库
2. 进入 **Actions** 页面
3. 选择 `🔍 GitHub Actions Runner 侦察报告` 工作流
4. 点击 **Run workflow**
5. 等几分钟，去 **Releases** 页面下载完整报告

## 采集内容

| 类别 | 详情 |
|------|------|
| 系统 | OS、内核、架构、主机名、时区、locale |
| Runner 元数据 | runner 变量、镜像版本、workspace 路径 |
| CPU | 型号、核心/线程数、缓存(L1/L2/L3)、拓扑、NUMA |
| 内存 | 总量、可用、插槽详情、swap |
| GPU | 型号、显存、驱动、NVIDIA/AMD/OpenGL |
| 磁盘 | 分区、文件系统、IO 调度器 |
| 网络 | 公网 IP(多源)、内网 IP、DNS、路由表、ARP、防火墙 |
| Cloudflare 信息 | cdn-cgi/trace (colo 数据中心、TLS、WARP 状态等) |
| User-Agent | curl / Python requests / PowerShell / httpbin 回显 |
| 环境变量 | 完整列表 |
| 已安装软件 | 包管理器统计 + 各工具版本 |
| 虚拟化/容器 | Docker、cgroup 限制、VM 检测 |
| 安全 | SELinux、AppArmor、Windows Defender、防火墙 |
| 进程/资源 | ulimit、cgroup 限额、top 进程 |
| 编译器 | gcc/clang 目标平台、链接器版本 |
| BIOS/主板 | Windows 平台完整硬件信息 |

## 覆盖平台

- `ubuntu-latest` — Linux
- `windows-latest` — Windows Server
- `macos-latest` — macOS

三个平台并行采集，报告自动合并为一个文件。

## 输出示例

```
--- Cloudflare 1.1.1.1 cdn-cgi/trace ---
fl=1f5b8f
h=www.cloudflare.com
ip=20.xxx.xxx.xxx
colo=LAX
tls=TLSv1.3
warp=off
uag=curl/8.5.0
...
```

## License

MIT
