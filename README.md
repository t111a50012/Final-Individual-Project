# Final-Individual-Project

# Analysis of the Difference between Physical Activity Frequency and BMI in Adolescents
## 青少年運動頻率與 BMI 之差異分析

## Student Information
* **Name:** 楊書雅 (Shu-Ya Yang)
* **Student ID:** 111A50012
* **Class:** 工管三乙

## Project Repository
* https://github.com/[填入你的GitHub網址]

## Presentation Video
* https://youtube.com/[填入你的YouTube影片網址]

---

## 專案概述 / Project Overview
本研究使用美國 CDC 2007 年青少年危險行為調查（`YRBS_2007.csv`）真實資料集，深入探討青少年的運動頻率是否會顯著影響其身體質量指數（BMI）。本專案嚴格遵循標準資料科學工作流程（研究問題 → 資料準備 → 統計方法 → 結果呈現 → 實質詮釋），並已完全修正所有隨機模擬錯誤與語法警告，產出出版等級的統計圖表與分析結果。

### 核心結論 (Core Conclusion)
單因子變異數分析（One-way ANOVA）與 Tukey's HSD 事後檢定結果顯示，每週運動天數較高的群組，其平均 BMI 顯著低於低運動量群組（$p < 0.05$）。**然而，事後檢定進一步證實「運動頻率」是關鍵**：每週運動 5-7 天能帶來最顯著的體態健康效益，而每週僅運動 3-4 天與 0-2 天在統計上則無顯著差異。

---

## 1. 研究問題與變數定義 (Research Question & Variables)

* **研究問題 (Research Question)**：不同體育參與程度（不運動組、輕度運動組、頻繁運動組）的學生，其平均 BMI 是否有顯著不同？
* **應變數 (Dependent Variable - Y)**：`BMI`（連續型數值），利用原始資料的身高與體重公式 $\text{Weight(kg)} / \text{Height(m)}^2$ 計算而得。
* **自變數 (Independent Variable - X)**：`Activity_Group`（類別型順序變數），根據過去 7 天運動達 60 分鐘的天數進行科學化重編碼：
  * **Low (0-2 days)**：每週運動 2 天或以下，代表久坐或低活動量型態。
  * **Moderate (3-4 days)**：每週運動 3 至 4 天，代表基礎活動量型態。
  * **High (5-7 days)**：每週運動 5 至 7 天，代表符合高活動量之健康指引。

---

## 2. 專案工作流程與目錄結構 (Workflow & Directory Structure)

本專案採用完全解耦、模組化的分層資料夾架構，確保程式碼與資料流的獨立性與重現性：

```text
├── data/
│   ├── raw/         # 原始 YRBS_2007.csv 真實數據資料夾
│   └── processed/   # 清理後數據 (yrbs_cleaned.csv, yrbs_recoded.csv)
├── outputs/
│   ├── figures/     # 高品質統計圖表 (直方圖、推論統計箱形圖)
│   ├── tables/      # 結構化統計摘要表 (ANOVA表、Tukey HSD明細表)
│   └── summary/     # 終端真實統計總結報告 (final_project_report.txt)
├── references/      # 詮釋資料與變數定義文件 (.md 檔案)
├── notebooks/       # 核心 Jupyter Notebook 實驗腳本
└── README.md        # 專案首頁說明文件
