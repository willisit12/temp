# Excel Bulk Upload Plan

This document outlines the structure for an Excel sheet and a file organization strategy to allow team members to manually enter car data for bulk uploading to the system.

## 1. Excel Structure (Sample Columns)

Each row in the Excel sheet represents one vehicle. The columns are mapped from the `data.json` structure used by the scraper.

| Column Header | Description | Example |
| :--- | :--- | :--- |
| **Reference ID** | A unique ID for internal tracking. | `Manual_001` |
| **Make** | Brand of the car. | `Ford` |
| **Model** | Specific model name. | `Edge` |
| **Year** | Manufacturing year. | `2012` |
| **Price** | Selling price (numeric). | `26200` |
| **Price Unit** | Currency of the price. | `CNY` |
| **Mileage** | Distance traveled (numeric). | `200200` |
| **Mileage Unit** | Unit for mileage. | `km` |
| **Location** | City or region where the car is located. | `Suzhou` |
| **Engine** | Engine capacity/type. | `2.0T` |
| **Transmission**| `Automatic` or `Manual`. | `Automatic` |
| **Emission** | Emission standard. | `National IV` |
| **Drive Mode** | `Front-wheel`, `Rear-wheel`, `4WD`. | `Front-engine FWD` |
| **Color** | Exterior color. | `White` |
| **Body Type** | Vehicle body style (Dropdown). | `SUV` |
| **VIN** | Vehicle Identification Number (optional). | `ABC123456789` |
| **Condition Score**| Numeric rating (1-10). | `8` |
| **Features** | List of features separated by commas. | `Sunroof, Leather Seats, Backup Camera` |
| **Description** | Marketing or detailed description. | `Clean car, well maintained.` |
| **Image Folder** | **CRITICAL**: The name of the folder containing pictures for this car. | `car_001_images` |

---

## 2. Image Organization Strategy

To ensure the bulk upload script can correctly associate pictures with the right car data, the team should follow this folder structure:

### Directory Layout
```text
manual_uploads/
├── manual_data.xlsx
├── car_001_images/
│   ├── 01.jpg
│   ├── 02.jpg
│   └── ...
├── car_002_images/
│   ├── 01.jpg
│   └── ...
└── ...
```

### Steps for the Team:
1.  **Prepare the Folder**: Create a folder for each car (e.g., `car_XYZ_images`).
2.  **Save Pictures**: Put all pictures for that car inside its specific folder.
    *   Pictures should be named sequentially (e.g., `01.jpg`, `02.jpg`) or concisely.
3.  **Update Excel**: In the **Image Folder** column of the Excel sheet, enter the *exact name* of the folder you created in Step 1.
4.  **Reference ID**: Use a consistent Reference ID that matches your internal records.

## 3. Data Entry & Validation Rules (Point 3)

To ensure the bulk upload process runs smoothly and the database remains clean, please follow these rules:
1.  **Mandatory Fields**: Reference ID, Make, Model, and Price must always be filled.
2.  **Date Format**: The 'Year' column should only contain the 4-digit year (e.g., `2022`).
3.  **Numeric Only**: 'Price' and 'Mileage' columns should only contain numbers. Do not add currency symbols or "km" inside these cells.
4.  **Feature List**: Separate features with a standard comma (`,`).
5.  **Image Folder Mapping**: The name in the "Image Folder" column must match the local folder name *exactly* (case-sensitive).
6.  **Body Type Selection**: Must select one of the following from the dropdown:
    *   Hatchback, Mini Van, Pick up, SEDAN, SUV, TRUCK, Van, Wagon, Sprinter

---

# Excel 批量上传计划 (中文版)

本文档概述了 Excel 表格结构和文件组织策略，以便团队成员手动输入汽车数据进行系统批量上传。

## 1. Excel 结构 (示例列)

Excel 表中的每一行代表一辆车。列与抓取工具使用的 `data.json` 结构相对应。

| 列标题 | 说明 | 示例 |
| :--- | :--- | :--- |
| **Reference ID** | 用于内部跟踪的唯一 ID。 | `Manual_001` |
| **Make** (品牌) | 汽车品牌。 | `Ford` |
| **Model** (车型) | 具体车型名称。 | `Edge` |
| **Year** (年份) | 制造年份。 | `2012` |
| **Price** (价格) | 销售价格（数字）。 | `26200` |
| **Price Unit** | 价格货币单位。 | `CNY` |
| **Mileage** (里程) | 行驶距离（数字）。 | `200200` |
| **Mileage Unit** | 里程单位。 | `km` |
| **Location** (地点) | 车辆所在地。 | `Suzhou` |
| **Engine** (发动机) | 发动机容量/类型。 | `2.0T` |
| **Transmission** | `Automatic` (自动) 或 `Manual` (手动)。 | `Automatic` |
| **Emission** | 排放标准。 | `National IV` |
| **Drive Mode** | 驱动模式。 | `Front-engine FWD` |
| **Color** (颜色) | 外观颜色。 | `White` |
| **Body Type** (车身类型) | 车身样式 (下拉菜单)。 | `SUV` |
| **VIN** | 车辆识别号码（可选）。 | `ABC123456789` |
| **Condition Score**| 状况评分（1-10）。 | `8` |
| **Features** (配置) | 功能列表，用逗号分隔。 | `Sunroof, Leather Seats` |
| **Description** (描述)| 营销或详细描述。 | `车况良好，保养得当。` |
| **Image Folder** | **关键**：存放该车照片的文件夹名称。 | `car_001_images` |

---

## 2. 图片整理策略

为了确保批量上传脚本能正确将图片与车辆数据关联，团队应遵循以下文件夹结构：

### 目录布局
```text
manual_uploads/
├── manual_data.xlsx
├── car_001_images/
│   ├── 01.jpg
│   ├── 02.jpg
│   └── ...
└── ...
```

### 团队操作步骤：
1.  **准备文件夹**：为每辆车创建一个文件夹（例如 `car_XYZ_images`）。
2.  **保存图片**：将该车的所有图片放入其专用文件夹中。
    *   图片应按顺序命名（如 `01.jpg`, `02.jpg`）。
3.  **更新 Excel**：在 Excel 的 "Image Folder" 列中，输入你在第 1 步中创建的文件夹的*确切名称*。
4.  **Reference ID**：使用与内部记录一致的 Reference ID。

## 3. 数据输入与校验规则

1.  **必填项**：Reference ID、品牌、车型和价格必须填写。
2.  **年份格式**：年份列仅包含 4 位数字。
3.  **纯数字**：价格和里程列仅输入数字，不要带单位。
4.  **文件夹匹配**：Excel 中的文件夹名称必须与实际文件夹名称*完全一致*（区分大小写）。
5.  **车身类型选择**：必须从下拉列表中选择一项：
    *   Hatchback, Mini Van, Pick up, SEDAN, SUV, TRUCK, Van, Wagon, Sprinter
