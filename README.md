# Final-Individual-Project

# Analysis of the Difference between Physical Activity Frequency and BMI in Adolescents
# 青少年運動頻率與 BMI 之差異分析

## Student Information / 學生資訊
| Item / 項目 | Details / 詳細資訊 |
| :--- | :--- |
| **Name / 姓名** | 楊書雅 (Shu-Ya Yang) |
| **Student ID / 學號** | 111A50012 |
| **Class / 班級** | 工管三乙 |

## Project Repository / 專案倉庫
* https://github.com/[填入你的GitHub網址]

## Presentation Video / 簡報影片
* https://youtube.com/[填入你的YouTube影片網址]

---

## 專案概述 / Project Overview

| Language / 語言 | Description / 概述內容 |
| :--- | :--- |
| **English** | This study utilizes the U.S. CDC 2007 Youth Risk Behavior Survey (`YRBS_2007.csv`) dataset to investigate whether adolescents' physical activity frequency significantly affects their Body Mass Index (BMI). The project strictly follows a standard data science workflow: **Research Question → Data Preparation → Statistical Method → Result → Interpretation**, with all code warnings and random-seed bugs fully resolved. |
| **中文對照** | 本研究使用美國 CDC 2007 年青少年危險行為調查（`YRBS_2007.csv`）真實資料集，探討青少年的運動頻率是否會顯著影響其身體質量指數（BMI）。本專案嚴格遵循標準資料科學工作流程：**研究問題 → 資料準備 → 統計方法 → 結果呈現 → 實質詮釋**，並已完全修正所有套件過時警告與隨機數錯誤。 |

### 核心結論 / Core Conclusion
* **English:** One-way ANOVA and Tukey's HSD post-hoc tests reveal that groups with higher weekly exercise days have a significantly lower average BMI than low-activity groups ($p < 0.05$). However, the post-hoc test further confirms that "frequency" is the key: exercising 5–7 days a week brings the most significant health benefits, whereas exercising 3–4 days shows no statistical difference compared to 0–2 days.
* **中文對照:** 單因子變異數分析（One-way ANOVA）與 Tukey's HSD 事後檢定結果顯示，每週運動天數較高的群組，其平均 BMI 顯著低於低運動量群組（$p < 0.05$）。然而，事後檢定進一步證實「運動頻率」是關鍵：每週運動 5-7 天能帶來最顯著的體態健康效益，而每週僅運動 3-4 天與 0-2 天在統計上則無顯著差異。

---

## 1. 研究問題與變數定義 / Research Question & Variable Definitions

| Variable / 變數類型 | Variable Name / 變數名稱 | Data Type / 數據類型 | Description (English / 中文) |
| :--- | :--- | :--- | :--- |
| **Research Question<br>研究問題** | \- | \- | Do students with different levels of physical activity (Low, Moderate, High) differ significantly in their average BMI?<br>不同體育參與程度（不運動組、輕度運動組、頻繁運動組）的學生，其平均 BMI 是否有顯著不同？ |
| **Dependent (Y)<br>應變數** | `BMI` | Continuous<br>連續型數值 | Calculated using the official formula: $\text{Weight(kg)} / \text{Height(m)}^2$.<br>利用原始資料的身高與體重公式計算而得之身體質量指數。 |
| **Independent (X)<br>自變數** | `Activity_Group` | Categorical (Ordinal)<br>類別型順序變數 | Recoded based on the number of days exercising for $\ge 60$ mins in the past 7 days:<br>根據過去 7 天運動達 60 分鐘的天數進行科學化重編碼：<br>• **Low (0-2 days)**: Sedentary or low activity. / 久坐或低活動量型態。<br>• **Moderate (3-4 days)**: Baseline activity. / 基礎活動量型態。<br>• **High (5-7 days)**: Meets health guidelines. / 符合高活動量之健康指引。 |

---

## 2. 工作流程與目錄結構 / Workflow & Directory Structure

```text
├── data/
│   ├── raw/         # Raw dataset / 原始 YRBS_2007.csv 真實數據資料夾
│   └── processed/   # Cleaned data / 清理後數據 (yrbs_cleaned.csv, yrbs_recoded.csv)
├── outputs/
│   ├── figures/     # Plots / 高品質統計圖表 (Distribution Histplot, Boxplot)
│   ├── tables/      # Structured tables / 結構化統計摘要表 (ANOVA, Tukey HSD tables)
│   └── summary/     # Final summary report / 終端真實統計總結報告 (.txt)
├── references/      # Metadata & notes / 詮釋資料與變數定義文件 (.md)
├── notebooks/       # Jupyter Notebook scripts / 核心實驗腳本
└── README.md        # Documentation / 專案首頁說明文件
