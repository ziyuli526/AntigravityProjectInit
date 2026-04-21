影片連結:https://youtu.be/NgHWAWfwU-o 


notebookLM:https://notebooklm.google.com/notebook/05a1b6b3-fbf8-4b4e-b2ec-efd07690463d







💧 Smart Hydration System

個人化智慧飲水系統（IoT + Health Data + Weather Integration）

📌 Overview

This project proposes a personalized smart hydration system that integrates IoT sensing, wearable health data, and real-time environmental information to provide adaptive and data-driven hydration recommendations.

Unlike traditional hydration apps that rely on manual input or fixed reminders, this system automatically tracks water intake and dynamically adjusts daily hydration goals based on physiological and environmental conditions.

🎯 Motivation
人體約 50–70% 為水分
脫水會影響：
電解質平衡
器官功能
現有問題：
❌ 依賴「口渴」→ 已經脫水
❌ 手動記錄 → 使用率低

👉 本系統目標：
將「主觀喝水」轉為「數據驅動健康行為」

🧠 Key Features
🔹 1. Personalized Hydration Estimation
根據以下資訊動態計算：
體重
心率（Apple Watch / HealthKit）
活動量（步數、運動）
天氣（溫度、濕度、熱傷害指數）
🔹 2. Automatic Water Intake Tracking (IoT)
使用硬體：
ESP32
HX711 (24-bit ADC)
Load Cell（重量感測）
功能：
自動偵測喝水量（無需手動輸入）
精度達 mL 等級
🔹 3. Real-Time Feedback System
顯示：
OLED（硬體）
App Dashboard
提供：
剩餘飲水量
即時提醒
行為引導
🔹 4. Context-Aware Hydration Adjustment
整合：
🌡️ 氣溫 / 濕度
☀️ 熱傷害指數
❤️ 心率變化

👉 在高風險情境（炎熱 + 高心率）下
➡️ 自動提高飲水建議

🏗️ System Architecture
1. Data Collection
HealthKit（心率、步數等）
CWA API（氣象資料）
2. Decision Module
動態飲水演算法
喝水 / 補水事件判斷
3. Hardware Sensing
Load Cell + HX711 + ESP32
高精度重量轉換（1g ≈ 1mL）
4. Feedback Layer
OLED + App UI
即時提醒與視覺化
📊 Hydration Model
📌 Target Water Formula
TargetWater=BaseWater+WeatherAdj+ActivityAdj
BaseWater = 體重 × 30–40 mL
WeatherAdj = 氣候影響
ActivityAdj = 活動量影響
📌 Water Intake Detection
DrankWater=Weight
before
	​

−Weight
after
	​


👉 條件：

ΔWeight < ±2g 持續 3 秒 → 才記錄
📌 Event Detection
↓ 重量 → 喝水
↑ 重量 → 補水
⚙️ Hardware Design
Component	Function
ESP32	控制與通訊
HX711	高精度 ADC
Load Cell	重量感測
OLED	顯示資訊

👉 採用：

Wheatstone Bridge
128x gain amplification
Moving Average Filter（降噪）
🔗 External Integration
Health Data
Apple HealthKit
心率 / 步數 / 活動
Weather Data (CWA API)
API	用途
F-A0085-001	熱傷害指數
F-A0085-004	溫差提醒
O-A0001-001	溫濕度
🧪 Calibration & Evaluation
Calibration
Tare 歸零
放置標準重量
計算比例係數
寫入系統
驗證誤差

👉 精度目標：±5g（>95% accuracy）

KPIs
測量精度
模型合理性
使用者行為改善
🚀 Future Work
🤖 Machine Learning 個人習慣預測
🧠 AI 健康分析（ChatGPT Health）
📊 長期健康關聯分析
💡 Contribution

This project bridges the gap between:

Wearable health data
Environmental context
Physical IoT sensing

👉 提供真正「個人化 + 自動化 + 即時」的智慧飲水管理系統

🏁 One-line Summary

👉
A data-driven IoT hydration system that transforms drinking behavior from passive habit into intelligent health management.
