# ESP8266 PMS5003 MQTT 空氣品質監測

本專案使用 HW628 / ESP8266 讀取 Plantower PMS5003 的 PM1.0、PM2.5、PM10，並透過 Wi‑Fi 發布至 MQTT。

## 使用方式

1. 將 `mqtt_01/config.example.h` 複製為 `mqtt_01/config.h`。
2. 在 `config.h` 填入 Wi‑Fi SSID 與密碼。`config.h` 不會被提交到 Git。
3. 使用 Arduino IDE 開啟 `mqtt_01/mqtt_01.ino`，選擇 NodeMCU 1.0（ESP-12E Module）後上傳。

## 接線

| PMS5003 | HW628 / ESP8266 |
|---|---|
| VCC | 5V / VIN / VU |
| GND | GND |
| TXD | D6 / GPIO12 |
| RXD | D5 / GPIO14（可選） |

MQTT 預設設定：`mqttgo.io:1883`，主題 `phmhs/aqi`，每 10 秒發布一次。

PMS5003 不具備溫度與濕度感測功能，因此 JSON 中的 `temperature` 與 `humidity` 會以 `-1` 表示。

完整學習歷程請參閱 `20261003物聯網通訊實務研習.docx` 與 `專案對話紀錄_20261003.md`。
