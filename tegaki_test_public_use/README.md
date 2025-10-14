# めぶきちゃんねる 投稿ツール（アニメ対応版）

🌱 めぶきちゃんねる掲示板のスレッドに絵やアニメを投稿するためのブラウザツール群です。  
PixiJS ベースの描画エンジンと APNG/GIF/WEBP などの出力機能を統合しています。

---

## 📘 概要
- ブラウザ上でアニメーション付きの描画が可能  
- APNG / GIF / WebP / PNG 出力に対応  
- ブックマークレットで掲示板上から直接起動可能  
- 主要ファイルを統合した `tegaki_anime.js` は npm でビルド生成  

---

## 🧩 主な構成
| 役割 | ファイル |
|------|-----------|
| コアエンジン | `src/tegaki_anime_core.js` |
| 発火テストHTML | `TegakiAniTest.html` |
| ローダー | `tegaki-loader_anime.js` |
| ビルドスクリプト | `build.js`, `package.json` |
| 外部ライブラリ | `libs/gif.js`, `libs/pako.js`, `libs/upng.js` など |

---

## 🚀 実行方法
1. `TegakiAniTest.html` をブラウザで開く  
2. または、以下のブックマークレットを登録して掲示板上で実行：

```javascript
javascript:(function(){
  if(!window.tegakiStart){
    var s=document.createElement('script');
    s.charset='UTF-8';
    s.src='https://toshinka.github.io/tegaki/tegaki_anime_test/tegaki-loader_anime.js';
    document.body.appendChild(s);
  }else{
    window.tegakiStart();
  }
})();
⚙️ 使用ライブラリ
PixiJS（MIT License）

gif.js（MIT License）

pako（MIT License）

UPNG.js（MIT License）

Lucide Icons（ISC License）

📄 ライセンス（MIT）
sql
コードをコピーする
MIT License

Copyright (c) 2025 toshinka

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND,
EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF
MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT.
IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM,
DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE,
ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER
DEALINGS IN THE SOFTWARE.
🎨 アイコンライセンス
本ツールでは Lucide Icons を利用しています。
Lucide は ISC License の下で提供されています。
© Lucide Contributors (https://github.com/lucide-icons/lucide)