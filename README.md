# TBrain: E-Sun Fraud Detection

![image](https://img.shields.io/badge/python-3.6-blue.svg)

## Abstract
Our team "三峽地震研究所" won **3%** in the game 
[玉山人工智慧公開挑戰賽2019秋季賽真相只有一個 -『信用卡盜刷偵測](https://tbrain.trendmicro.com.tw/Competitions/Details/10).  

## Rule
一卡在手，妙用無窮！
在台灣，20歲以上持有信用卡人數超過六成。因信用卡具備高回饋、延遲付款以及付款便利等特性，使得信用卡成為人們支付時不可或缺的工具。不過隨著科技的日新月異，不肖分子也針對此支付模式衍生出新的犯罪手法，即「信用卡盜刷」。

面對盜刷，一般民眾除了可以透過經常對帳、防止卡片資訊外洩等方式來避免外，國內外銀行及發卡組織近年也開始運用機器學習演算法找出潛在的盜刷交易，並及早因應。然而，盜刷的樣態千百種，到底什麼才是足以判斷為盜刷的關鍵因子呢？ 

本次競賽提供去識別信用卡交易授權資料，希望大家集思廣益，一同「反盜刷」！不僅捍衛自己的資產，守護身邊親友的財富，更有機會獲得高額獎金！

本次競賽共包含兩場獨立賽事，分別為「線上對決–模型準度爭霸戰」與「正面交鋒–創意做法擂台戰」。「線上對決–模型準度爭霸戰」為2019/09/06 – 2019/11/22於T-Brain平台上傳預測結果的競賽，將以預測準確度為排名依據，爭取最高12萬元的獎金；「正面交鋒–創意做法擂台戰」將於頒獎典禮當天舉行，獲獎資格為曾於「線上對決–模型準度爭霸戰」上傳成功且「非前六名」得獎的參賽者，每一獎項皆有新台幣5,000(含)元以上獎金，獲獎機率高達20%，只要您願意分享您的建模做法，就有機會將獎項抱回家！

以下頁面內所有說明為「線上對決–模型準度爭霸戰」之競賽細節，「正面交鋒–創意做法擂台戰」之進行內容、方式與報名連結，敬請參賽者密切注意主辦單位相關公告與通知。

## 特徵說明
參考至https://github.com/CubatLin/TBrain-E.SUN-AI-Open-Competition-Fall-2019-15th-place-Feature-Engineering
欄位          | 說明  |備註
-------------|:-----:|---------------------------------------------------------------------------------------------------
bacno | 歸戶帳號	|持卡人帳戶
txkey	|交易序號	|一筆交易產生一組交易序號(唯一值)
locdt	|授權日期	|刷卡交易時向發卡銀行提出授權之日期(通常與交易日期為同一天，除非有預先授權的情況，參考：https://cpsamuelsl527.pixnet.net/blog/post/63542071-[教學]-「預先授權」到底是什麼？)
loctm	|授權時間	|刷卡交易時向發卡銀行提出授權之時間
cano	|交易卡號	|交易卡號(一個持卡人帳戶下可以有很多組卡號)
contp	|交易類別	|交易類型，舉例：正向交易、負向交易(刷退)、預借現金等
etymd	|交易型態	|交易方式，舉例：手動輸入卡號、刷磁條機、感應讀取卡號、利用預先儲存的信用卡資料進行交易(例如Netflix月租自動扣款) 參考資料：https://dnwebdomestic2.efunds.com/dnweb/webhelp/Field_Descriptions/MC_POS_Entry_Mode.htm
mchno	|特店代號	|消費商店之代碼
acqic	|收單行代碼	|消費商店合作銀行的代碼
mcc	|MCC_CODE	|消費子類別代碼(一個消費類別(例如保險、航空、食品等)下面可以有很多MCC_CODE)
conam	|交易金額-台幣(經過轉換)	|  
ecfg	|網路交易註記	|交易是否在網路上完成
insfg	|分期交易註記	|交易是否有分期
iterm	|分期期數	|
stocn	|消費地國別	|消費商店登記在哪個國家
scity	|消費城市	|消費商店登記在哪個城市
stscd	|狀態碼	|卡片狀態，舉例：停卡、掛失、逾期等
ovrlt	|超額註記碼	|累積使用額度超過額度上限，即被下註記
flbmk	|Fallback 註記	|採用人工授權方式所下的註記，其可能原因為隨機抽樣或是發卡銀行懷疑此筆為不正常交易
hcefg	|支付形態	|虛擬卡交易註記，其型態可能為APPLE PAY, android pay, Samsong pay 等
csmcu	|消費地幣別	|使用哪個幣別進行消費
flg_3dsmk	|3DS 交易註記	|有進行手機驗證碼之交易
fraud_ind	|盜刷註記	|是否有盜刷(應變數)

## Metric
F1_score

## PPT
![image](https://github.com/rgib37190/TBrain-E-Sun-Fraud-Detection/blob/main/ppt/%E6%8A%95%E5%BD%B1%E7%89%873.JPG)
![image](https://github.com/rgib37190/TBrain-E-Sun-Fraud-Detection/blob/main/ppt/%E6%8A%95%E5%BD%B1%E7%89%874.JPG)
![image](https://github.com/rgib37190/TBrain-E-Sun-Fraud-Detection/blob/main/ppt/%E6%8A%95%E5%BD%B1%E7%89%875.JPG)
![image](https://github.com/rgib37190/TBrain-E-Sun-Fraud-Detection/blob/main/ppt/%E6%8A%95%E5%BD%B1%E7%89%876.JPG)
![image](https://github.com/rgib37190/TBrain-E-Sun-Fraud-Detection/blob/main/ppt/%E6%8A%95%E5%BD%B1%E7%89%877.JPG)
![image](https://github.com/rgib37190/TBrain-E-Sun-Fraud-Detection/blob/main/ppt/%E6%8A%95%E5%BD%B1%E7%89%878.JPG)
![image](https://github.com/rgib37190/TBrain-E-Sun-Fraud-Detection/blob/main/ppt/%E6%8A%95%E5%BD%B1%E7%89%879.JPG)
![image](https://github.com/rgib37190/TBrain-E-Sun-Fraud-Detection/blob/main/ppt/%E6%8A%95%E5%BD%B1%E7%89%8710.JPG)
![image](https://github.com/rgib37190/TBrain-E-Sun-Fraud-Detection/blob/main/ppt/%E6%8A%95%E5%BD%B1%E7%89%8711.JPG)
![image](https://github.com/rgib37190/TBrain-E-Sun-Fraud-Detection/blob/main/ppt/%E6%8A%95%E5%BD%B1%E7%89%8712.JPG)
![image](https://github.com/rgib37190/TBrain-E-Sun-Fraud-Detection/blob/main/ppt/%E6%8A%95%E5%BD%B1%E7%89%8713.JPG)
![image](https://github.com/rgib37190/TBrain-E-Sun-Fraud-Detection/blob/main/ppt/%E6%8A%95%E5%BD%B1%E7%89%8714.JPG)
![image](https://github.com/rgib37190/TBrain-E-Sun-Fraud-Detection/blob/main/ppt/%E6%8A%95%E5%BD%B1%E7%89%8715.JPG)
