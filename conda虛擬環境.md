
# 太常使用，拿到前頭

## 匯出專案的 `environment.yml` 檔案
完成環境的配置後，可以用以下命令導出環境
```
conda env export --name 專案環境名稱 > environment.yml
```

## 根據 `environment.yml` 的設定創建環境
```
conda env create -f environment.yml
```

```
(base) PS C:\Users\673929> conda env list
# conda environments:
#
base                  *  C:\ProgramData\anaconda3

(base) PS C:\Users\673929>
```

這段顯示的內容是使用者在 Windows PowerShell 裡執行 `conda env list` 指令的結果。以下是逐步解釋：

1. **`conda env list` 是什麼？**
   - 這是一個用於列出目前在 Conda 環境管理工具中已經安裝的虛擬環境的指令。
   - Conda 是一個包和環境管理系統，常用於管理 Python 軟體包以及建立隔離的環境，以避免不同專案的依賴衝突。

2. **指令輸出的內容：**
   - `# conda environments:`: 這是說明接下來列出的內容是 Conda 環境列表。
   - `base`: 這是預設的 Conda 環境，通常是安裝 Anaconda 時自動創建的。
   - `*`: 星號表示目前使用者所在的 Conda 環境是 `base`。
   - `C:\ProgramData\anaconda3`: 這是 `base` 環境的路徑，表明這個環境安裝在電腦上的 `Anaconda3` 目錄下。

3. **執行的環境：**
   - `(base)`: 命令提示符中的 `(base)` 表示使用者目前正處於 `base` 環境中。
   - `PS C:\Users\673929>`: 這是 PowerShell 提示符，表明使用者目前的工作目錄是 `C:\Users\673929`。

### 總結：
使用者執行了 `conda env list` 來檢視系統上已存在的 Conda 環境，結果顯示目前只有一個名為 `base` 的環境，並且該環境已被啟用。



# 在專案資料夾中打開 **Conda Prompt**

1. **使用檔案總管打開專案資料夾**：首先，進入你的專案資料夾。
   
2. **打開 Conda Prompt**：
   - 在專案資料夾內，按住 `Shift` 鍵並右鍵點擊資料夾空白處。
   - 選擇「在此處開啟命令視窗」或「在此處開啟 PowerShell 視窗」。
   - 然後輸入 `conda activate` 來啟動 Conda 環境。

# 根據 `environment.yml` 的設定創建環境

`conda env create -f environment.yml` 這段指令是在 **Conda Prompt** 中輸入的。

這個指令會告訴 Conda 根據 `environment.yml` 檔案中的設定來創建一個新的虛擬環境，並安裝檔案中列出的所有依賴包。

操作步驟：
1. 在專案資料夾中打開 **Conda Prompt**，如上述的步驟
2. 執行指令：
   ```bash
   conda env create -f environment.yml
   ```

這樣 Conda 就會開始根據 `environment.yml` 的設定創建環境，安裝所有必要的包。





