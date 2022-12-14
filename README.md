# ç®ä»

ð¥³ `Electron` + `Vue3` + `Vite` + `Pinia` + `Element-Plus` + `TypeScript`.

renderer æ¸²æè¿ç¨ä¸­æºç æ¥èª [v3-admin-vite](https://github.com/un-pany/v3-admin-vite).

## è¿è¡é¡¹ç®

```bash
# config
1. å®è£ .vscode ä¸­æ¨èçæä»¶
2. node çæ¬ 16+

# enter the project directory
cd v3-electron-vite

# install dependency
yarn

# initialize husky
yarn prepare

# develop
yarn dev

# build
yarn build

# build dir
yarn build:dir

# update dependencies
yarn upgrade-interactive --latest
```

## ä»£ç æ ¼å¼æ£æ¥

```bash
yarn lint
```

## ç®å½ç»æ

ä¸æ¦å¯å¨ææåèæ¬æ§è¡è¿ï¼ä¼å¨æ ¹ç®å½äº§ç **`dist` æä»¶å¤¹ï¼éé¢çæä»¶å¤¹å `src` ä¸æ¨¡ä¸æ ·**ï¼å¨ä½¿ç¨ä¸äºè·¯å¾è®¡ç®æ¶ï¼å°¤å¶æ¯ç¸å¯¹è·¯å¾è®¡ç®ï¼`dist` ä¸ `src` éé¢ä¿æç¸åçç®å½ç»æè½é¿å¼å¥½å¤é®é¢.

```tree
âââ .v3-electron-vite
â   âââ build.mjs                    é¡¹ç®æå»ºèæ¬ï¼å¯¹åº yarn build
â   âââ dev-runner.mjs               é¡¹ç®å¼åèæ¬ï¼å¯¹åº yarn dev
â   âââ vite-main.config.ts          ä¸»è¿ç¨éç½®æä»¶ï¼ç¼è¯ src/main
â   âââ vite-preload.config.ts       é¢å è½½èæ¬éç½®æä»¶ï¼ç¼è¯ src/preload
â   âââ vite-renderer.config.ts      æ¸²æè¿ç¨éç½®æä»¶ï¼ç¼è¯ src/renderer
â
âââ dist                             æå»ºåï¼æ ¹æ® src ç®å½çæ
â   âââ main
â   âââ preload
â   âââ renderer
â
âââ src
â   âââ main                         ä¸»è¿ç¨æºç 
â   âââ preload                      é¢å è½½èæ¬æºç 
â   âââ renderer                     æ¸²æè¿ç¨æºç 
â
âââ static                           éæèµæº
â   âââ icons                        ç³»ç»å¾æ 
```

## æ¸²æè¿ç¨ä½¿ç¨ Node API

> ð§ å ä¸ºå®å¨çåå  Electron é»è®¤ä¸æ¯æå¨ æ¸²æè¿ç¨ ä¸­ä½¿ç¨ NodeJs API

#### æ¨èææç NodeJsãElectron API éè¿ `preload-script` æ³¨å¥å° æ¸²æè¿ç¨ä¸­ï¼ä¾å¦ï¼

- **src/preload/index.ts**

  ```typescript
  import { contextBridge, ipcRenderer } from "electron"

  // --------- Expose some API to Renderer process. ---------
  contextBridge.exposeInMainWorld("$ipcRenderer", withPrototype(ipcRenderer))
  ```

- **src/renderer/@types/shims-vue.d.ts**

  ```typescript
  interface Window {
    $ipcRenderer: typeof import("electron")["ipcRenderer"]
  }
  ```

## Git æäº¤è§è

- `feat` å¢å æ°çä¸å¡åè½
- `fix` ä¿®å¤ä¸å¡é®é¢/BUG
- `perf` ä¼åæ§è½
- `style` æ´æ¹ä»£ç é£æ ¼, ä¸å½±åè¿è¡ç»æ
- `refactor` éæä»£ç 
- `revert` æ¤éæ´æ¹
- `test` æµè¯ç¸å³, ä¸æ¶åä¸å¡ä»£ç çæ´æ¹
- `docs` ææ¡£åæ³¨éç¸å³
- `chore` æ´æ°ä¾èµ/ä¿®æ¹èææ¶éç½®ç­çäº
- `workflow` å·¥ä½æµæ¹è¿
- `ci` æç»­éæç¸å³
- `types` ç±»åå®ä¹æä»¶æ´æ¹
- `wip` å¼åä¸­

## ç«å¨å·¨äººçè©èä¸

- [electron-vite-vue](https://github.com/electron-vite/electron-vite-vue)
- [electron-vue-admin](https://github.com/PanJiaChen/electron-vue-admin)
- [fast-vue3](https://github.com/study-vue3/fast-vue3)
