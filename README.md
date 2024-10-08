# 行為為基礎的早期失智症監測機器學習偵測模型

據衛生福利部於2024年3月21日公布最新臺灣社區失智症流行病學調查結果，今（2024）年65歲以上失智症人口約35萬人，預估到120年將超過47萬人、130年更攀升到68萬人，推估未來20年中，失智人口平均每日增加48人，平均每30分鐘增加1位失智者。越來越多有失智的年長者在家中，但失智的量測因家屬不在身旁，不易被即時察覺。本研究目的主要針對這些問題來開發一款針對年長者的APP，建立親屬形象數位助理，有效減少長輩孤獨感，同時關注失智症狀的發生與評估嚴重程度。

## Setup

### Python
* 套件安裝（建議用虛擬環境）
    ```shell
    pip install -r /backend/requirements.txt
    ```

### MongoDB
* [Mac brew install](https://www.mongodb.com/zh-cn/docs/manual/tutorial/install-mongodb-on-os-x/)
* start: `brew services start mongodb-community@7.0`
* view: use [Compass](https://www.mongodb.com/products/tools/compass)
* stop: `brew services stop mongodb-community@7.0`

### Expo
* download & install [Android Studio](https://developer.android.com/studio?hl=zh-tw)
    * click "Virtual Device Manager"
    * device: Pixel 8 API 35
    * run device
* install Expo: 
    ```
    npx create-expo-app@latest
    npx expo install expo-notifications expo-location
    ```
* install eas:
    ```shell
    npm install -g eas-cli
    eas init
    ```
* login: `npx expo login`

## Quick Start

### Python Backend
* `cd backend`
* `python App.py`
* 畫面顯示類似這樣:
    ```sh
    * Running on all addresses (0.0.0.0)
    * Running on http://127.0.0.1:5000
    * Running on http://192.168.4.114:5000
    ```

### Run watch
* 再開一個新的終端機
* `cd watch`
* `export EXPO_PUBLIC_BACKEND_URL={URL}/watch` 
    * URL 要用上面後端顯示的「第三行」, ex: `export EXPO_PUBLIC_BACKEND_URL=http://192.168.4.114:5000/watch`
    * Windows 要換成 `$Env:EXPO_PUBLIC_BACKEND_URL = "http://192.168.4.114:5000/watch"`
* `npx expo start`
* press `shift+a`
* select watch

### Run phone
* 開一個新的終端機
* `cd phone`
* `export EXPO_PUBLIC_BACKEND_URL={URL}/phone` 
    * URL 要用上面後端顯示的「第三行」, ex: `export EXPO_PUBLIC_BACKEND_URL=http://192.168.4.114:5000/phone`
    * Windows 要換成 `$Env:EXPO_PUBLIC_BACKEND_URL = "http://192.168.4.114:5000/phone"`
* `npx expo start`
* press `shift+a`
* select emulator
