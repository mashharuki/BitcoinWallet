# BitcoinWallet
Bitcoinウォレット機能を実装したアプリのリポジトリです。

## 注意事項！ このリポジトリで使用している情報は全て開発用です。

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

### API ACCESS_TOKENの確認
   `curl -H "Authorization: Bearer $ACCESS_TOKEN" https://app.bitgo.com/api/portfolio/v1/user/current`

### Walletアドレスを取得するAPI
    coinには、暗号資産のシンボルを(ビットコインだったらbtc)
    WalletIdには、BitGo社のページで作成したIDを入力すること。
   `curl -H "Authorization: Bearer $ACCESS_TOKEN" https://app.bitgo.com//api/v2/{coin}/wallet/{walletId}/addresses`

   以下、レスポンスの一例

```json
{
  "coin":"btc",
  "totalAddressCount":1,
  "addresses":[{
    "id":"622c013489be5500077e2c5d65ad254a",
    "address":"3MCnrkATN4ufuwphcPNh33Kp61S9wNAcqQ",
    "chain":10,
    "index":1,
    "coin":"btc",
    "wallet":"622c013489be5500077e2c48c0d97df5",
    "coinSpecific":{
      "redeemScript":"00204cab21afd336786cd7f49a68f092a56fbe61e9fa4dfdcbe6759ea6112e9afed7",
      "witnessScript":"522102df3af4bba8abef4d92743b38e623ab1e1dd18efd7bd149f38b1be27d3003dbe52102c1132597b7aadee01306d0b9421a81e29097b99f0ead91040c7588c66733047e21027ccb8b6233e2b624e6f14eecf5f02899930af0c7acf9a2b155f18e64bea84d6253ae"
    }
  }],
  "count":1
}
```

### 参考サイト
  1. <a href="https://www.blockchain.com/api">https://www.blockchain.com/api</a>
  2. <a href="https://github.com/mashharuki/bitcoin-web-wallet">https://github.com/mashharuki/bitcoin-web-wallet</a>
  3. <a href="https://github.com/mashharuki/insight-api">https://github.com/mashharuki/insight-api</a>
  4. <a href="https://github.com/mashharuki/bitcoinjs-lib">bitcoin js</a>
  5. <a href="https://tech.bitbank.cc/bitcoin-wallet/">ビットコインウォレットを作ろう！</a>
  6. <a href="https://app.bitgo.com/docs/#section/Multi-Signature-Wallets">BitGo社のAPIドキュメント</a>
  7. <a href="https://www.blockcypher.com/getting-started.html">blockcypher.com</a>
  8. <a href="https://docs.blockstream.com/blockstream-amp/api-tutorial.html#">blockstream社のAPIチュートリアル</a>
                                                        
