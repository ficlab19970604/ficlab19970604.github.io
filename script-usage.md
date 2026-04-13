## 4. Docker 實驗室部署說明

### 架構概覽
本實驗室採用 `fic-lab:v5.2` 作為基底映像檔，執行時將自動產生 4 個節點：

1. **[Core-VM]**: 核心開發區，掛載 `~/work` 原始碼。
2. **[PWN-Train]**: CTF 競技場，配置 gdb/pwntools。
3. **[FIPS-Test]**: 安全合規測試區，執行 OpenSSL/FIPS 驗證。
4. **[Trade-Monitor]**: 程式交易監控區，運行 Python 監控腳本。

### 如何部署
使用實驗室提供的自動化腳本：

```bash
# 1. 確保腳本權限 (僅需設定一次)
chmod +x start_lab.sh.v5.2

# 2. 執行並啟動所有容器
./start_lab.sh.v5.2 --all

# 3. 進入特定節點 (例如進入開發區)
./start_lab.sh.v5.2 --enter core
