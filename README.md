# Fiscal Dynamics

[English](./README_EN.md)

## 项目简介

Fiscal-Dynamics 是一个基于中国省级经济数据的税收数据挖掘与计量经济学分析项目。

本项目围绕产业税收、居民消费支出以及居民可支配收入展开分析，并结合统计学与机器学习方法完成区域税收分级研究。

## 分析流程

1. 数据读取与初步探索
2. 数据整合与统计描述
3. 数据处理与清洗（缺失值、对数变换、正态性验证）
4. Pearson 相关系数分析
5. 多元线性回归建模（含 VIF、异方差、自相关检验）
6. K-Means 聚类分析（肘部法则 + 区域分级）
7. 地理空间可视化（GeoPandas 中国地图）

## 快速开始

```bash
# 1. 安装依赖
pip install -r requirements.txt

# 2. 将原始数据文件放入 data/ 目录
#    - 产业税收表 (.xlsx)
#    - 居民人均消费支出表 (.xlsx)
#    - 人均可支配收入表 (.xlsx)
#    - (可选) GIS shapefile 放入 data/gis/

# 3. 启动 Jupyter 并运行分析
jupyter notebook notebooks/fiscal-dynamics-analysis.ipynb
```

## 数据要求

| 文件               | 关键字段                                                                                                                            |
| ------------------ | ----------------------------------------------------------------------------------------------------------------------------------- |
| 产业税收表         | TaxAmount, PrimaryInduTaxAmount, SecondInduTaxAmount, TertiaryInduTaxAmount                                                         |
| 居民人均消费支出表 | ConsumExpense, CE_FoodTobaccoliquor, CE_Clothing, CE_Resident, CE_DailyUse, CE_TrafficCommunicate, CE_EducateCulture, CE_HealthCare |
| 人均可支配收入表   | PCDI, PCDI_WageIncome, PCDI_BusinessIncome, PCDI_PropertyIncome, PCDI_TransferIncome                                                |

所有表需包含 `Sgnyea`（年度标识）、`AreaName`（地区名称）列用于连接。

## 项目结构

```text
fiscal-dynamics/
├── data/            — 原始数据（Excel, shapefile）  [git-ignored]
├── notebooks/       — Jupyter 分析 notebook
├── src/             — 工具入口
├── figures/         — 输出图表  [git-ignored]
├── doc/             — 相关文档
├── README_.md        — 项目说明（中文）
├── README_EN.md     — 项目说明（英文）
├── LICENSE          — MIT License
├── requirements.txt — Python 依赖
└── .gitignore
```

## 技术栈

- Python · Pandas · NumPy · SciPy
- Statsmodels（回归、检验）
- Scikit-learn（聚类）
- GeoPandas（空间可视化）
- Matplotlib · Seaborn（绑图）

## 研究方向

- 税收数据分析
- 计量经济学
- 区域经济研究
- 聚类分析
- 空间数据可视化

## 开源协议

本项目采用 MIT License 开源协议。
