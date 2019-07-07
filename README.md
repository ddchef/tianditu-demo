# tdt-test

> **运行demo需要安装vue3.0**
## Project setup
```
yarn install
```

### Compiles and hot-reloads for development
```
yarn run serve
```

### 安装leaflet

```
yarn add leaflet
```

### 添加`chinatmsproviders.js`文件
```js
import L from 'leaflet'
// 载入插件
import Provider from './chinatmsproviders'
// 载入样式
require('leaflet/dist/leaflet.css')
```