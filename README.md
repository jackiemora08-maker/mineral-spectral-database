# 矿物和土壤光谱数据库 (Mineral & Soil Spectral Database)

## 简介 (Introduction)

本项目为矿物和土壤的光谱数据集合。所有数据以标准化的txt格式存储，便于下载、处理和分析。

数据来源：
- USGS Spectral Library (https://www.usgs.gov/labs/spec-lab)
- ASTER Spectral Library (https://speclib.jpl.nasa.gov/)
- RRUFF Database (https://rruff.info/)

## 目录结构 (Directory Structure)

```
mineral-spectral-database/
├── README.md                 # 本文件
├── data/
│   ├── minerals/            # 矿物光谱数据
│   │   ├── quartz/
│   │   ├── feldspars/
│   │   ├── calcite/
│   │   ├── dolomite/
│   │   ├── hematite/
│   │   ├── magnetite/
│   │   ├── micas/
│   │   ├── chlorite/
│   │   ├── kaolinite/
│   │   ├── montmorillonite/
│   │   └── illite/
│   └── soils/               # 土壤光谱数据
│       ├── laterite/
│       ├── ultisol/
│       ├── cambisol/
│       ├── mollisol/
│       ├── spodosol/
│       ├── salic_soil/
│       ├── gravelly_soils/
│       └── clay_soils/
├── scripts/                 # 数据处理脚本
│   ├── data_processor.py
│   └── spectral_plotter.py
├── metadata.csv             # 数据源和属性记录
└── templates/               # 数据模板
    └── spectral_data_template.txt
```

## 数据格式 (Data Format)

每个txt文件包含以下信息：

### 文件头部 (Header)
```
Name: [样品名称]
Type: [物质类型: Mineral/Soil]
Sample_ID: [样品ID]
Wavelength_Range: [波长范围，如 0.4-2.5 micrometers]
Data_Source: [数据来源，如 USGS]
Date_Acquired: [获取日期]
```

### 数据部分 (Data Section)
```
Wavelength(μm)	Reflectance(%)
0.38	5.2
0.39	5.3
...
2.50	8.1
```

- **Wavelength(μm)**: 波长，单位微米
- **Reflectance(%)**: 反射率，单位百分比

## 文件命名规则 (File Naming Convention)

`[material_name]_[sample_id].txt`

示例：
- `quartz_GDS26.txt`
- `calcite_GDS01.txt`
- `laterite_soil_sample_001.txt`

## 使用方法 (Usage)

### 1. 下载数据
```bash
git clone https://github.com/jackiemora08-maker/mineral-spectral-database.git
```

### 2. 加载和处理数据 (Python示例)
```python
import pandas as pd
import matplotlib.pyplot as plt

# 读取光谱数据
data = pd.read_csv('data/minerals/quartz/quartz_GDS26.txt', 
                    sep='\t', skiprows=6)

# 绘制光谱曲线
plt.plot(data['Wavelength(μm)'], data['Reflectance(%)'])
plt.xlabel('Wavelength (μm)')
plt.ylabel('Reflectance (%)')
plt.title('Quartz Spectral Reflectance')
plt.show()
```

## 矿物列表 (Minerals List)

| 矿物 | 化学式 | 样品数 | 状态 |
|------|--------|--------|------|
| 石英 (Quartz) | SiO₂ | - | 📝 待补充 |
| 长石 (Feldspars) | - | - | 📝 待补充 |
| 方解石 (Calcite) | CaCO₃ | - | 📝 待补充 |
| 白云石 (Dolomite) | CaMg(CO₃)₂ | - | 📝 待补充 |
| 赤铁矿 (Hematite) | Fe₂O₃ | - | 📝 待补充 |
| 磁铁矿 (Magnetite) | Fe₃O₄ | - | 📝 待补充 |
| 云母 (Micas) | - | - | 📝 待补充 |
| 绿泥石 (Chlorite) | - | - | 📝 待补充 |
| 高岭石 (Kaolinite) | Al₂Si₂O₅(OH)₄ | - | 📝 待补充 |
| 蒙脱石 (Montmorillonite) | - | - | 📝 待补充 |
| 伊利石 (Illite) | - | - | 📝 待补充 |

## 土壤列表 (Soils List)

| 土壤类型 | 英文名 | 样品数 | 状态 |
|---------|--------|--------|------|
| 红壤 | Laterite/Oxisol | - | 📝 待补充 |
| 黄壤 | Ultisol | - | 📝 待补充 |
| 褐壤 | Cambisol | - | 📝 待补充 |
| 黑壤 | Mollisol | - | 📝 待补充 |
| 灰壤 | Spodosol | - | 📝 待补充 |
| 盐碱土 | Salic soil | - | 📝 待补充 |
| 砾质土壤 | Gravelly soils | - | 📝 待补充 |
| 粘质土壤 | Clay soils | - | 📝 待补充 |

## 许可证 (License)

本项目数据遵循USGS、ASTER和RRUFF的开源许可证。

---

**最后更新 (Last Updated)**: 2026-05-25
