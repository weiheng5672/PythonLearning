以下是 Anaconda 的環境變數設定範例：

```
C:\ProgramData\Anaconda3
C:\ProgramData\Anaconda3\library\mingw-w64\bin
C:\ProgramData\Anaconda3\library\usr\bin
C:\ProgramData\Anaconda3\library\bin
C:\ProgramData\Anaconda3\scripts
```

### Anaconda 最新版本的環境變數管理（截至 2025 年 1 月 18 日）

在 2025 年的最新版本中，Anaconda 的安裝過程已經取消了**預設環境變數的選項**，以更進一步落實虛擬環境的精神。

#### 預設行為

1. 在完成安裝並重新啟動電腦後，系統會自動將你帶入 **base 環境**。
2. 不需要手動設定環境變數，也能在 CMD 或 PowerShell 中預設使用 `conda` 指令。這樣可以避免與系統層級的 Python 發生干擾。

#### 特殊情況

由於 Anaconda 是開源軟件，每台電腦的環境可能有所不同。不是所有的電腦在安裝 Anaconda 後都能成功自動設置好上述行為。

1. 有時在cmd可以，但PowerShell不行
2. 重開機或者透過conda prompt執行`conda init`

總之有各種情況，發現進入 CMD 或 PowerShell 後，並未預設在 **base 環境**，此時需要手動進行環境變數的設定。

### 建議的解決方案

1. **設定環境變數**：將以下路徑加入系統的環境變數中：
   - `C:\ProgramData\Anaconda3`
   - `C:\ProgramData\Anaconda3\library\mingw-w64\bin`
   - `C:\ProgramData\Anaconda3\library\usr\bin`
   - `C:\ProgramData\Anaconda3\library\bin`
   - `C:\ProgramData\Anaconda3\scripts`

2. **避免安裝系統層級的 Python**：
   為了避免與 Anaconda 發生衝突，建議在使用 Anaconda 時不要安裝系統層級的 Python，或者至少確保它們的使用範圍互不干擾（如調整 PATH 順序）。

### 總結

Anaconda 最新版本雖然已經簡化了環境變數的設定過程，但對於一些特殊情況，開發者仍需要手動配置相關環境。同時，避免系統層級的 Python 干擾能有效提升 Anaconda 的使用體驗，確保虛擬環境的穩定性與便利性。

