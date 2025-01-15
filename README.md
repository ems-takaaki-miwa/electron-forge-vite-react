# electron forge + vite + react
npmでしか動かないので注意
## 起動
```bash
npm run start
```
## 作り方
1. Electron Forgeのテンプレートでvite + Typescriptで作成
   ```
   npx create-electron-app@latest my-new-app --template=vite-typescript
   ```
2. reactに必要なパッケージのインストール
   ```bash
   npm i react react-dom
   npm i -D @types/react @types/react-dom @vitejs/plugin-react
   ```
3. Vite設定にReactプラグインを追加(一応preloadとrendererに入れた)
   ```
   import { defineConfig } from 'vite';
   import react from '@vitejs/plugin-react';
   
   export default defineConfig({
        plugins: [react()],
    });
    ```
4. Reactエントリポイントを作成<br>
   `src/renderer/main.tsx`に記述
5. index.htmlを修正
   - 参照するスクリプトを`src/renderer/main.tsx`に変更
   - `<div id="root"></div>`を追加
