工作上需要, 將TypeScripts導入node-red中 (用ts語法寫node)
基本上是參考這篇教學文: https://medium.com/@bernardo.belchior1/node-red-creating-a-custom-node-using-typescript-5f4fd0127d44

然後把所有額外功能去除掉, 只留下最簡單的 ts compile 所需要的套件
**有任何問題歡迎私訊我**, 台灣在這塊的資源還是滿少的

簡短說明:
1. git clone 本範例, npm install, npm run build
    * 說明: 此時我們有compiled好的.js code了 (可註冊node-red節點)
2. 把src資料夾的html檔複製到dist的對應資料夾中 (P.S. 原作者有寫copy html的script, 但為了其他人好上手, 改用手動copy方式)
    * 說明: html + js是node-red的標準寫法, 由於package.json: "node" 那邊指定的路徑是dist/, 故須從src複製對應的html過去
3. 到user/[YourName]/.node-red資料夾下開cmd輸入: npm install [Path of this Cloned repo]
    * 說明: 把custom節點註冊進node-red專案
4. 任一終端機視窗輸入: "node-red" 於瀏覽器開啟即可看到剛剛用.ts寫好並compiled後的節點了

--- 我是分隔線 ---

# Lower Case Node

This example is the same as [Node-RED's official guide](https://nodered.org/docs/creating-nodes/first-node). 

## Running

Make sure you have `npm` and `Node-RED` installed locally.

### First run

On the first run, you must install the package in Node-RED's directory.
This can be made following the ["Testing your node in Node-RED" section of the official guide](https://nodered.org/docs/creating-nodes/first-node#testing-your-node-in-node-red).
Remember to `npm install` the dependencies.

### Subsequent runs

For development, run `npm run watch`, which will watch for changes in TS files, recompile and restart Node-RED. As of now, this command will *not* watch for changes in HTML files.

For production, run `npm run build`, which will build the files and copy the assets.
