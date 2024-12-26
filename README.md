# Node.js S3 Integration with Survey Data Processing

## 簡介
本專案是一個使用 Node.js 編寫的 AWS Lambda 函數，旨在從外部 API 獲取調查數據，並根據不同的優惠券類型，將收集到的資訊存儲到 AWS S3 上的 JSON 文件中。

## 功能
- 接收來自事件的請求，提取調查的 SVID 和 HASH 值。
- 根據調查結果的優惠券類型，來選擇性地獲取和存儲電話號碼。
- 從 AWS S3 中讀取現有的 JSON 文件，並將新信息添加到該文件中。
- 將更新後的數據上傳回 AWS S3。

## 安裝與使用方式
1. 確保您的環境中已安裝 Node.js。
2. 安裝必要的依賴模組：
   ```bash
   npm install aws-sdk node-fetch
   ```
3. 配置 AWS 認證，修改代碼中的 `accessKeyId`, `secretAccessKey` 和 `region`。
4. 設定 S3 的 Bucket 名稱和 Key 值，以便讀取和寫入資料。
5. 部署代碼至 AWS Lambda 環境中。
6. 觸發 Lambda 函數時傳遞相應的事件格式，包含 `body` 參數，格式為 `svid=YOUR_SVID&hash=YOUR_HASH`。

## 必要的依賴模組清單
- `aws-sdk`: 用於操作 AWS 服務。
- `node-fetch`: 用於從外部 API 獲取數據。

## 授權條款
本專案採用 MIT 授權條款。詳細資訊請參閱 [LICENSE](LICENSE) 文件。