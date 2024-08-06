# CFED (Carbon Footprint Emission Database) 資料庫

## 簡介

CFED（Carbon Footprint Emission Database）專案

旨在為台灣民眾提供一個簡易且免費的途徑獲取政府認證的產品碳足跡排放數據

該專案收錄了中華民國環境部審查通過的產品碳足跡排放係數資料，這些數據來源於環境部建立的[產品碳足跡資訊網](https://cfp-calculate.tw/) //以下簡稱CFP網站。

目前，CFP網站內的完整產品碳足跡資料無法直接提供給一般民眾下載。而[政府開源網站](https://data.gov.tw/) 所提供的產品碳足跡資料為簡化版本，無法滿足使用者對完整資訊的需求。

因此，本專案將CFP網站上的完整產品碳足跡資料下載並整理成JSON格式後，提供給所有使用者下載使用; 

並創建了更簡單易用的查詢網站 [CFED](https://indhill.tw/CFED/) 方便使用者查詢和下載。

---

## 碳足跡排放數據資料庫檔案

資料擷取日期 2024-04-01

### 資料結構

資料庫的檔案包含了兩個部分，第0筆的翻譯與詮釋資料，以及第1~n筆的正式資料

**屬性對應表**

| 屬性 ID | 中文名稱 |
| ------- | -------- | 
| cd_id | 物件編號 | 
| chineseName | 中文名稱 |
| image | 圖片 | 
| englishName | 英文名 | 
| category | 主分類 | 
| group | 次分類 | 
| items | 碳係數名稱 | 
| chemFormulaOrName | 化學式/俗名 |
| carbonFootprint | 碳足跡值 | 
| quantity | 數量 | 
| declarationUnit | 宣告單位 | 
| lifeCycle | 生命週期範疇(系統邊界) |
| exclusions | 排除項目 | 
| techDescription | 技術描述 | 
| prodRegion | 生產區域 | 
| inventoryPeriod | 盤查期間 | 
| dataSource | 活動數據來源 |
| emissionSource | 排放係數來源 | 
| reliability | 數據品質等級可靠性 | 
| completeness | 數據品質等級完整性 | 
| calcCounselingUnit | 碳足跡計算輔導單位名稱 | 
| constructionUnit | 建置單位名稱 | 
| thirdPartyVerified | 是否經第三方查驗證 |
| announcementYear | 公告年份 | 
| remarks | 備註 | 
| GWPSource | 全球暖化潛勢值來源 |
| metadata | 詮釋資料 |


**示範資料**

以下是資料庫中的第0與第1筆資料示範：

**第0筆資料（屬性翻譯依據）**

```
{
    "cd_id": "物件編號",
    "chineseName": "中文名稱",
    "image": "圖片",
    "englishName": "英文名",
    "category": "主分類",
    "group": "次分類",
    "items": "碳係數名稱",
    "chemFormulaOrName": "化學式/俗名",
    "carbonFootprint": "碳足跡值",
    "quantity": "數量",
    "declarationUnit": "宣告單位",
    "lifeCycle": "生命週期範疇(系統邊界)",
    "exclusions": "排除項目",
    "techDescription": "技術描述",
    "prodRegion": "生產區域",
    "inventoryPeriod": "盤查期間",
    "dataSource": "活動數據來源",
    "emissionSource": "排放係數來源",
    "reliability": "數據品質等級可靠性",
    "completeness": "數據品質等級完整性",
    "calcCounselingUnit": "碳足跡計算輔導單位名稱",
    "constructionUnit": "建置單位名稱",
    "thirdPartyVerified": "是否經第三方查驗證",
    "announcementYear": "公告年份",
    "remarks": "備註",
    "GWPSource": "全球暖化潛勢值來源",
    "metadata":{
      "updatedata": "2024-04-01",
      "datanumber" : 1111,
      "resource":"https://cfp-calculate.tw/"
    }
}
```

** 第1筆資料（正式資料）**

```
{
    "cd_id": 1982,
    "chineseName": "天然氣(未燃燒，2021)",
    "image": "",
    "englishName": "Natural Gas (unburnt, 2021)",
    "category": "能資源",
    "group": "氣",
    "items": "天然氣",
    "chemFormulaOrName": "",
    "carbonFootprint": {
        "value": "5.19E-1",
        "unit": "kgCO₂e"
    },
    "quantity": 1,
    "declarationUnit": "立方公尺(m3)",
    "lifeCycle": "搖籃到大門",
    "exclusions": "",
    "techDescription": "1.從天然氣開採開始，經生產,精製,液化,輸入國內(中油公司LNG廠),氣化回到氣態,再於高壓常溫環境配送到用戶為止。\n\r2.熱值轉換資訊為：37.60 MJ/ m3。\n\r3.1公斤(液態)＝1.320立方公尺(氣態)＝2.207公升(液態)。\n\r",
    "prodRegion": [
        "台灣"
    ],
    "inventoryPeriod": "2021-01-01~2021-12-31",
    "dataSource": "1.液化天然氣進口國家別，為能源署110年度能源統計手冊公告資料。\n\r2.運送到國內的里程資料，為中油公司2021年簡介揭露的數值。\n\r",
    "emissionSource": "各進口國天然氣開採(包含開採時的甲烷洩漏),液化,及中油的儲存,配銷過程係引用工研院DoITPro 2022資料庫內的係數資料",
    "reliability": "2",
    "completeness": "1",
    "calcCounselingUnit": "財團法人工業技術研究院",
    "constructionUnit": "環境部",
    "thirdPartyVerified": "否",
    "announcementYear": 2023,
    "remarks": "1.本項目計算範疇未涵蓋天然氣使用階段，若產業欲引用本項目之碳足跡數值，建議應用於依循ISO14064-1：2018年版量化組織層級溫室氣體的排放量與移除量，間接排放計算時使用。\n\r2.國外油田或天然氣田生產之天然氣，先經淨化處理，再經超低溫(零下162℃)予以液化，利用液化天然氣船運輸(進口比例詳細資訊見能源統計手冊)抵中國石油公司位於高雄市永安區的液化天然氣廠後，以超低溫、常壓方式儲存，再提供予各公用氣體燃料事業(瓦斯公司)，配銷至一般用戶使用，或直接銷售給工業用戶、發電用戶或合格汽電共生系統用戶。\n\r3.相關資訊可參考中油業務簡介2021年版第22至23頁之說明。\n\r4.產品數據品質分數評分說明: (1) 可靠性：計算所使用的數據，為國家公告且部分查驗過之數據，故給予2分；(2) 完整性：計算所需的數據，已來自相關場址提供且具代表性，故給予1分。\n\r",
    "GWPSource": "IPCC第六次評估報告(2021)"
}
```

## 使用說明

1. 將此資料庫中的資料作為參考，應用於依循 ISO14064-1：2018 年版量化組織層級溫室氣體的排放量與移除量，間接排放計算時使用。
2. 資料來源於中華民國環境部的產品碳足跡資訊網，資料完整性和準確性經過審查。
3. 歡迎大家下載並使用這些資料來進行碳足跡計算和分析。

## 貢獻

歡迎大家一起來完善此資料庫，提交 pull request 或者 issue，我們會盡快處理。

## 授權

此資料庫內容依據 [MIT 授權條款](LICENSE) 授權。
