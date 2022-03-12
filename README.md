# BitcoinWallet
Bitcoinウォレット機能を実装したアプリのリポジトリです。

### 実装予定機能
  1. トランザクション送信機能
  2. 残高照会機能
  3. アカウント作成＆管理機能
  4. トランザクション履歴照会機能

### 利用するAPI
    BitGo社のAPIを利用するので、アカウントの作成とアクセストークンを作成してください。

### BitGoのSDKインストール準備
  下記コマンドにて調査
  `npm i bitgo`

  使い方の列
  
  ```js
    const BitGoJS = require('bitgo');
    // Read the user authentication section to get your API access token
    // .envをclientファイル配下に作成してREACT_BITGO_API_ACCESS_TOKENを設定する。
    const bitgo = new BitGoJS.BitGo({
      env: 'test',
      accessToken: process.env.REACT_BITGO_API_ACCESS_TOKEN,
    });
    const coin = bitgo.coin('tbtc');
  ```

### 参考サイト
  1. <a href="https://www.blockchain.com/api">https://www.blockchain.com/api</a>
  2. <a href="https://github.com/mashharuki/bitcoin-web-wallet">https://github.com/mashharuki/bitcoin-web-wallet</a>
  3. <a href="https://github.com/mashharuki/insight-api">https://github.com/mashharuki/insight-api</a>
  4. <a href="https://github.com/mashharuki/bitcoinjs-lib">bitcoin js</a>
  5. <a href="https://tech.bitbank.cc/bitcoin-wallet/">ビットコインウォレットを作ろう！</a>
  6. <a href="https://app.bitgo.com/docs/#section/Multi-Signature-Wallets">BitGo社のAPIドキュメント</a>
                                                        
