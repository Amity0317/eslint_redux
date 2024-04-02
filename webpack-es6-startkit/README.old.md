

# eslintd開發環境--test
https://ithelp.ithome.com.tw/articles/10184606


1. VSCODE的選單列中的 檔案 -> 喜好設定 -> 使用者設定 為settings.js==Ctrl + Shift + P（在 Windows 和 Linux 上）或 Cmd + Shift + P（在 macOS 上）開啟工作區(json)
```javascript
    {
        "editor.fontSize": 14,//改變字體大小
        "editor.tabSize": 2,//按1個tab鍵，為2個空白
        "files.autoSave": "afterDelay",//每秒(afterDelay)自動存檔
        "typescript.check.tscVersion": false//痊癒檢查typescript的版本
    }
```

2. Flow工具要另外安裝，一般都是安裝到全域之中，也就是可以讓所有的專案都共享執行。所以接著用命令列工具(終端機)來安裝它即可:
參數-g代表加入到全域之中。至於Flow工具的使用(更改文件名或路徑來解決此問題，確保只使用 7 位 ASCII 字符。)，在之後的章節會再作介紹。
`npm i -g flow-bin`

3. 開啟終端機快捷鍵Ctrl + `


4. 出現 Unexpected console statement.警告(警告console.log() 通常是提醒開發者注意可能會影響程式碼性能或安全性的地方。)
https://eslint.org/docs/latest/rules/no-console#rule-details，在.eslintrc中可以做設定
```javascript
/* eslint no-console: ["error", { allow: ["warn", "error"] }] */
console.warn("Log a warn level message.");
console.error("Log an error level message.");
```
```javascript
// eslint-disable-next-line no-console
console.log(add(a, b))
```
5. 安裝VSC的插件Prettier ESLint


## ESLint - Lint工具的後起之秀
https://ithelp.ithome.com.tw/articles/10184924


## Flow - JavaScript靜態類型檢查工具
https://ithelp.ithome.com.tw/articles/10185039

# redux--test
https://ithelp.ithome.com.tw/articles/10187498
https://github.com/eyesofkids/webpack-es6-startkit







## To run the project locally:
1.  使用vscode的複製
2. `npm install`
4. 確認專案正常運作: `npm start`
4. 出現 ERROR in Cannot find module 'babel-core . 錯誤: `npm install babel-core core-js --save-dev`
4. 出現Expected linebreaks to be 'LF' but found 'CRLF'.錯誤

(在 Unix 系統中，行結尾使用 LF（Line Feed），而在 Windows 系統中，行結尾使用 CRLF（Carriage Return + Line Feed）。): 
> 轉換行結尾符號： 使用一些工具或編輯器將文件的行結尾符號轉換為 LF。例如，在 Visual Studio Code 中，你可以通過右下角的編碼選擇器來轉換行結尾符號。

> 設置 git 的 autocrlf 屬性： 如果你是在 Windows 系統上開發並與 Unix 系統共享代碼，你可以在 git 中設置 autocrlf 屬性以自動轉換行結尾符號。你可以使用以下命令來設置 autocrlf 屬性：
`git config --global core.autocrlf true`or  Unix 系統上開發:`git config --global core.autocrlf input`

> 進行檢查和修復： 有一些工具可以檢查和修復代碼中的行結尾符號，例如 lint 工具或格式化工具。你可以運行這些工具來檢查並修復代碼中的行結尾符號問題。


## Redux
- 範例中並沒有要用到React
1. 安裝redux套件:`npm install --save redux`
2. 出現 Unexpected dangling _ in __REDUX_DEVTOOLS_EXTENSION__ .錯誤(錯誤通常表示在代碼中使用了 Redux DevTools Extension，但是未導入或未正確設置相關的環境)

```javascript
    import { createStore } from 'redux';
    import rootReducer from './reducers';
    import { composeWithDevTools } from 'redux-devtools-extension';

    const store = createStore(rootReducer, composeWithDevTools());

```

