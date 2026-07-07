# みんなの地図投稿

Firebase（Authentication + Firestore）と MapLibre GL JS を使った、
リアルタイムで投稿がみんなの地図に反映されるWebアプリです。

## 使い方

1. `firebase-config.example.js` を `firebase-config.js` としてコピーし、
   自分（または先生から配布された）Firebaseプロジェクトの `firebaseConfig` を貼り付ける
   （`firebase-config.js` は `.gitignore` で除外されているためGitHubには上がりません）。
2. Firebaseコンソールの Firestore「ルール」タブに `firestore.rules` の内容を貼って公開する。
3. このフォルダをそのまま VS Code の Live Server などで開く（`index.html` をブラウザで開く）。
4. 右上の「Googleでログイン」でサインインする。
5. 地図をクリックするか「現在地を使う」で場所を選び、コメントを書いて「投稿する」。
6. 他の人が投稿すると、ページを更新しなくても地図上にピンが増えていきます。

## ファイル構成

| ファイル | 内容 |
| --- | --- |
| `index.html` | 地図・フォーム・認証・投稿・リアルタイム表示のコード全部 |
| `firebase-config.js` | Firebaseの接続設定（`firebaseConfig`）だけ |
| `firestore.rules` | セキュリティルールの控え（実際はFirebaseコンソールに貼る） |

## 注意

- `localhost` はFirebaseの「承認済みドメイン」に最初から入っているので、開発中はそのまま動きます。
- Web用APIキーは公開されても問題ありません。安全性は Firestore の**ルール**と**認証**で守ります。
