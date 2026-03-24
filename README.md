# Family Cloud Computer / 家庭云电脑

**No desktop environment required, only Docker is needed.**  
**不需要桌面环境也可以运行，只需要有 Docker。**

This project sets up a persistent home cloud computer with automatic login, keep-alive, and VNC support.
这是一个家庭云电脑项目，支持自动登录、自动保活，并且永不关机。内置 VNC 功能。

---

## 📖 Usage Instructions (使用说明)

### 1. Download & Prepare (下载与准备)
- Download the `vdi-client` (`.deb`) file from the Release page.
- Copy the `.deb` file into the `config` directory of this folder.
- 从 Release 页面下载 `vdi-client` 的 deb 文件。
- 将 deb 文件拷贝到本目录下的 `config` 文件夹中。

### 2. Install (安装)
- Run the installation script:
- 执行安装脚本：
  ```bash
  ./install.sh
  ```

### 3. Configuration (配置)
- The script will automatically generate the `logs` and `config_0` directories (e.g., inside `config/config_0`).
- Go to the generated `config/config_0` directory.
- Open `credentials.conf` and update it with your phone number and password.
- 脚本会自动生成 `logs` 和 `config_0` 目录（位于 `config` 目录下）。
- 进入生成的 `config/config_0` 目录。
- 修改 `credentials.conf` 文件，填入您的手机号和密码。

### 4. Access (访问)
- Access via browser (NoVNC) or VNC Viewer.
- Default Browser URL: `http://localhost:6080/vnc.html` (Check script output for exact port)
- Default VNC Port: `5900`
- 您可以通过浏览器（NoVNC）或 VNC 客户端连接。
- 默认浏览器地址：`http://localhost:6080/vnc.html`
- 默认 VNC 端口：`5900`

---

## � Multi-Account Deployment (多账号部署)

You can run multiple independent cloud computers on a single machine by specifying an Instance ID.
您可以在同一台机器上运行多个独立的云电脑实例，只需指定实例 ID 即可。

### Usage (使用方法)
Run the script with a number (0-99) as an argument:
运行脚本时带上一个数字（0-99）作为参数：

```bash
# Run Instance 1 (运行实例 1)
./install.sh 1

# Run Instance 2 (运行实例 2)
./install.sh 2
```

### Resource Allocation (资源分配)
Each instance gets its own configuration folder and ports automatically:
每个实例会自动分配独立的配置文件夹和端口：

| Instance ID (实例 ID) | Config Folder (配置文件夹) | NoVNC Port (浏览器端口) | VNC Port (VNC 端口) |
|---|---|---|---|
| **0** (Default) | `config/config_0` | `6080` | `5900` |
| **1** | `config/config_1` | `6081` | `5901` |
| **2** | `config/config_2` | `6082` | `5902` |
| **N** | `config/config_N` | `6080 + N` | `5900 + N` |

**Note**: Remember to configure the `credentials.conf` in the corresponding `config_x` folder for each instance.
**注意**：请记得去对应的 `config_x` 文件夹中配置每个实例的 `credentials.conf`。

---

## �🚀 Extras & Advanced Setup (额外配套玩法)

### EasyTier & RustDesk
- **EasyTier**: Use Zeabur's free 5G traffic plan to set up an EasyTier server for networking.
- **RustDesk**: Install RustDesk inside the cloud computer for high-performance remote control.
- **EasyTier 组网**：可以使用 Zeabur 的免费 5G 流量搭建 EasyTier 服务器。
- **RustDesk 远程**：在云电脑内部安装 RustDesk。

### Performance (性能)
- Achieve intranet penetration and remote control with high speeds: **100M Upload / 40M Download**.
- 实现内网穿透和远程控制，享受 **100M 上传** 和 **40M 下载** 的高速体验。
