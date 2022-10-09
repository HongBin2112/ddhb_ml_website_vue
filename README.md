# ddhb-ml


## - 注意事項 By HB
<br>

### 1. 測試及Debug時，請使用下面指令後開啟網頁
```
npm run serve
```

### 2. xxx.Vue 等元件 ( components ) 檔案名稱使用大駝峰式命名法（upper camel case）：每一個單字的首字母都採用大寫字母，例如：FirstName、LastName。  
### 2.1. 若檔案名稱語法報錯，至package.json中35行"rules"->"vue/multi-word-component-names"->"ignores"，於其後新增檔案名稱。
### 2.2. 變數名稱則使用小駝峰式命名法。

<br>

### 3.雜項
- ### [Vue中动态绑定img的src属性(v-bind)](https://blog.csdn.net/ji_ban/article/details/108141905)


### 4.使用npm run build打包完成後，在dist資料夾打開index.html為空白?：到index.html內將js、css的路徑改一下，改為相對路徑即可。

### 4.1 github page部分：在github bash 中輸入"sh deploy.sh"。官方文件有提供發佈到github page的方法：請參閱[Vue CLI Deployment](https://cli.vuejs.org/guide/deployment.html#github-pages)


<br>

---
<br>

## - 主要檔案位置 :  
<br>

## ./public   
### - /favicon.ico  
### - /index.html
<br>

## ./src  
### - /assets/  
### - /components/   
### - /App.vue  
### - /main.js  


<br>
<br>

---
## - 官方預設README.md內容  
<br>

## Project setup
```
npm install
```

### Compiles and hot-reloads for development
```
npm run serve
```

### Compiles and minifies for production
```
npm run build
```

### Lints and fixes files
```
npm run lint
```

### Customize configuration
See [Configuration Reference](https://cli.vuejs.org/config/).

---
