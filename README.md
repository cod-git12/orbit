# Orbit - 2枚目のモニターを、手元のChromebookに
ローカル通信が遮断される家庭用ルーター環境でも、WindowsのセカンドディスプレイをChromebookに転送できます。インストール不要、無料で使える実用的なツールです。\
<sub>※Chromebookでなくても、インターネットに接続されていれば誰でも受信することができます。</sup>\
[ [Orbit公式サイト](https://orbit.5kaideta.cfd) / [Orbitをダウンロードする](https://orbit.5kaideta.cfd/download) ]

<p align="center">
  <img src="https://img.shields.io/badge/Language-JavaScript%20%2F%20Python-yellow?style=for-the-badge&logo=javascript" alt="Language">
  <img src="https://img.shields.io/badge/Server-Online-brightgreen?style=for-the-badge&logo=render" alt="Server Status">
  <img src="https://img.shields.io/badge/License-AGPL%20v3-orange?style=for-the-badge" alt="License">
</p>

# Orbit とは
Windowsの画面を受信側にそのまま送るツールです。受信側はインストール無しで使用できます。

# 仕組み
Windows の画面を、外部の中継サーバー経由で Chromebook に転送します。
![Orbitとは](https://orbit.5kaideta.cfd/images/image_07.png)

<table>
  <tr>
    <!-- ステップ 1 -->
    <td width="33.3%" align="center" valign="top" style="border: none;">
      <h3>Step 1</h3><br>
      <strong>キャプチャ</strong><br><br>
      <small>Windows 側で選択したディスプレイをリアルタイムでキャプチャします。</small>
    </td>
    <!-- ステップ 2 -->
    <td width="33.3%" align="center" valign="top" style="border: none;">
      <h3>Step 2</h3><br>
      <strong>中継</strong><br><br>
      <small>外部の中継 WebSocket サーバー経由でデータを転送します。</small>
    </td>
    <!-- ステップ 3 -->
    <td width="33.3%" align="center" valign="top" style="border: none;">
      <h3>Step 3</h3><br>
      <strong>表示</strong><br><br>
      <small>Chromebook のブラウザでリアルタイムに表示されます。</small>
    </td>
  </tr>
</table>

# 特徴・メリット - Orbitが選ばれる理由
<table>
  <tr>
    <td width="50%">
      <h3>
        <img src="https://orbit.5kaideta.cfd/images/wifi.svg" width="24" height="24" valign="middle">
        インストール不要
      </h3>
      <p>受信側は Web ブラウザで開くだけ。Chromebook に何もインストールする必要がありません。</p>
    </td>
    <td width="50%">
      <h3>
        <img src="https://orbit.5kaideta.cfd/images/image.svg" width="24" height="24" valign="middle">
        軽量な JPEG 転送
      </h3>
      <p>画面を JPEG 圧縮して転送するため、帯域幅を最小限に抑えられます。</p>
    </td>
  </tr>
  <tr>
    <td>
      <h3>
        <img src="https://orbit.5kaideta.cfd/images/lock.svg" width="24" height="24" valign="middle">
        ローカル IP 不要
      </h3>
      <p>外部の中継サーバーを経由するため、ローカル IP アドレスを知る必要がありません。</p>
    </td>
    <td>
      <h3>
        <img src="https://orbit.5kaideta.cfd/images/coin.svg" width="24" height="24" valign="middle">
        完全無料
      </h3>
      <p>ダウンロードから利用まで、すべて無料です。隠れた料金はありません。</p>
    </td>
  </tr>
</table>

# 対応環境
様々なデバイスとブラウザで利用できます

| デバイス / ブラウザ | 送信側 | 受信側 |
| :--- | :---: | :---: |
| Windows 10/11 | ✔️ | ― |
| Chromebook | ― | ✔️ |
| Chrome ブラウザ | ― | ✔️ |
| Firefox ブラウザ | ― | ✔️ |
| Safari ブラウザ | ― | ✔️ |

# よくある質問 (FAQ)
Orbit についてよく寄せられる質問にお答えします

<details>
  <summary><strong>遅延はどのくらいですか？</strong></summary>
  <br>
  家庭用回線であれば体感で数百ミリ秒程度です。動画視聴やウィンドウの補助表示には十分ですが、シビアな操作を伴う作業には向きません。
</details>
<details>
  <summary><strong>複数台の Chromebook で同時に受信できますか？</strong></summary>
  <br>
  仕組み上は複数クライアントでの受信も可能ですが、現状は1対1での利用を想定して検証しています。
</details>
<details>
  <summary><strong>Chromebook 以外でも受信できますか？</strong></summary>
  <br>
  はい。受信ページを開いてパスワードを入力すれば、どのブラウザでも受信することができます。（受信にはインターネットが必要です。）
</details>
<details>
  <summary><strong>セキュリティは大丈夫ですか？</strong></summary>
  <br>
  通信は中継サーバーを経由します。接続情報を第三者が知っている場合のリスクはゼロではないため、機微な用途には現時点で推奨していません。
</details>
<details>
  <summary><strong>料金はかかりますか？</strong></summary>
  <br>
  個人利用は無料です。中継サーバーの維持費は開発者が負担しています。
</details>
<details>
  <summary><strong>対応ブラウザは何ですか？</strong></summary>
  <br>
  受信側は WebSocket に対応した最新の Chrome、Firefox、Safari で動作を確認しています。
</details>

# 開発背景・こだわり

Orbit は、家庭用ルーターのプライバシーセパレーター機能によってローカル通信が遮断される環境で、Windows のセカンドディスプレイを Chromebook に転送したいという個人的なニーズから生まれました。

既存のソリューションの多くは同一ネットワーク内での通信を前提としていたため、プライバシーセパレーターが有効な環境では使用できませんでした。そこで、外部の中継 WebSocket サーバーを経由する構成を採用することで、この課題を回避しています。

[<strong>技術的なこだわり</strong>]\
送信側は Windows ネイティブアプリケーションで、選択したディスプレイをリアルタイムでキャプチャします。受信側は Web ブラウザで動作するため、インストールが不要です。このアプローチにより、Chromebook だけでなく、任意のブラウザを持つデバイスで受信画面を開くことができます。

画面データは JPEG で圧縮して転送することで、帯域幅を最小限に抑えています。中継サーバーは **Wispbyte (orbit.wispbyte.app)** で稼働しており、常に利用可能な状態を維持しています。

個人開発ですが、実用に耐えられるツールとして仕上げることを目標にしています。ご意見やご要望は、Issue でお気軽にお知らせください。

<div align="center">

## 今すぐ始めましょう
Orbit は完全無料です。Windows 側をダウンロードして、Chromebook で受信画面を開くだけで利用できます。

<a href="https://orbit.5kaideta.cfd/download"><img src="https://img.shields.io/badge/ダウンロード-111827?style=for-the-badge&logo=https%3A%2F%2Forbit.5kaideta.cfd%2Fimages%2Fdownload.svg" alt="ダウンロード"></a>
&nbsp;&nbsp;
<a href="https://orbit.5kaideta.cfd/viewer"><img src="https://img.shields.io/badge/受信画面を開く-ffffff?style=for-the-badge&logoColor=000000&labelColor=ffffff&logo=https%3A%2F%2Forbit.5kaideta.cfd%2Fimages%2Fdisplay.svg" alt="受信画面を開く"></a>

</div>
