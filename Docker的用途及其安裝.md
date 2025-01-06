
**Docker** 的用途及其安裝和使用方法，針對使用 **GNU Compiler Collection (GCC)** 的情境：

### 主要概念
- **Docker** 是一個用來封裝軟體的工具，將軟體和執行所需的所有依賴（如庫文件、配置等）打包成可移植的 **容器（containers）**。這樣就能在不同的系統平台上執行軟體，解決了跨平台環境配置的問題。
- **Docker Hub** 是一個分享和下載 Docker 容器的線上平台，很多軟體的容器可以免費下載和使用，例如 **GCC（GNU Compiler Collection）**。

### 內容摘要
1. **安裝 Docker**
   - Windows 和 macOS 使用者可以從 <https://www.docker.com/get-started> 下載並安裝 **Docker Desktop**。
   - Linux 使用者應從 <https://docs.docker.com/engine/install/> 安裝 **Docker Engine**。
   - 建議註冊一個 **Docker Hub** 帳戶，這樣可以方便下載和管理容器。

2. **下載 GCC Docker 容器**
   - 在安裝並啟動 Docker 後，打開命令提示符（Windows）、終端機（macOS/Linux），或 shell，然後執行以下命令來下載 GCC 容器：
     ```bash
     docker pull gcc:latest
     ```
   - 這個指令會從 Docker Hub 下載最新版本的 GCC 容器。

3. **未來使用 Docker 執行 C 程式**
   - 之後會演示如何使用該容器來編譯和運行 C 程式。

### 總結
這段話主要在說明如何安裝 Docker 以及使用 GCC 容器來快速開始 C 程式開發，特別適合那些環境配置繁瑣或需要跨平台支援的情境。

# 在 Ubuntu 中安裝 Docker 可以依循以下步驟：

### 步驟 1: 更新軟體包
開啟終端機，先更新系統中的現有軟體包索引：
```bash
sudo apt update
```

### 步驟 2: 安裝必要的套件
安裝 `apt` 使用 HTTPS 存取儲存庫所需的軟體包：
```bash
sudo apt install ca-certificates curl gnupg
```

### 步驟 3: 添加 Docker 的官方 GPG 密鑰
```bash
sudo install -m 0755 -d /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
sudo chmod a+r /etc/apt/keyrings/docker.gpg
```

### 步驟 4: 添加 Docker 的軟體包存儲庫
```bash
echo "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
```

### 步驟 5: 更新軟體包索引並安裝 Docker
```bash
sudo apt update
sudo apt install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```

### 步驟 6: 啟動並驗證 Docker 安裝
啟動 Docker 服務：
```bash
sudo systemctl start docker
```
設為開機啟動：
```bash
sudo systemctl enable docker
```
驗證 Docker 是否成功安裝：
```bash
docker --version
```

### 步驟 7: 測試 Docker
執行以下命令來確保 Docker 正常工作：
```bash
sudo docker run hello-world
```

### （可選）步驟 8: 避免每次使用 `sudo`
將目前的使用者加入 Docker 群組：
```bash
sudo usermod -aG docker $USER
```
之後登出並重新登入系統以使變更生效。

這樣就完成了在 Ubuntu 上的 Docker 安裝。