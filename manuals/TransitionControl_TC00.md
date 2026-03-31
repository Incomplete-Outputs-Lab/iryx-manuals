# vMixコントローラー Iryx TransitionControl TC-00 取扱説明書

## 1. はじめに

本製品は、vMixのトランジション制御に特化したコントローラーです。  
vMixの状態取得および操作をTCP API経由で行うための評価用試作機です。


---

## 2. 安全上のご注意

本製品は開発中の試作品であり、一般的な市販製品と同等の保護機能を備えていない場合があります。

* **電源:** USB-Cから直接給電が可能です。PCのUSBポートに接続してください。
* **環境:** ライブ配信現場などの機材密集地で使用する場合、排熱を妨げないように設置してください。
* **異常時:** 本体が異常に熱くなる、焦げた臭いがする等の場合は直ちにUSBケーブルを抜いてください。

---

## 3. 動作環境

- USB CDC-NCMに対応したWindows (Windows 10 Version 1903以降, Windows 11)
- USB 1.1 Full-speed
- vMix 29以降
  - v28以前のvMixではStinger5\~8, OverlayInput5\~8, Mix選択などや一部のTransitionに対応していない可能性があります。

---

## 4. 使用方法

### 接続方法

vMixが起動しているPCと本機をデータ転送可能なUSBケーブルで接続してください。  
イーサネットアダプターとして認識され、IPに``172.31.x.2`` が設定されます。  
なお、複数台接続する場合はIPの重複を回避するため、設定よりthird octet(``x``の部分) を変更してください。

### 設定項目

| 項目 | 設定内容 / 選択肢 | 備考 |
| :--- | :--- | :--- |
| 対象Mix | Main Mix, Mix 2〜16 | デフォルトは Main Mix |
| Cut動作 | `Cut`, `CutDirect` | Main Mix選択時のみ有効。Mix2~16を選択時は`Cut`で固定。 |
| Auto設定 | Transition種別, Duration | 設定画面より個別に指定可能 |
| Custom 1〜4 | `Stinger1〜4` | Shift押下時は 5〜8 に対応 |
| Custom 1〜4 <br>(Main Mix専用) | `OverlayInput1〜4`<br>`Transition1〜4` | Main Mix選択時のみ選択可能<br>(Shift押下時は 5〜8 に対応) |

---

#### 補足事項

* Mix選択による制約: `Cut` の挙動選択および `OverlayInput` / `Transition` の割り当ては、Main Mix設定時のみ利用可能な拡張機能です。
* Shiftレイヤー: Customボタンは、Shift機能を併用することで最大8つまでのアサインに対応します。
* 各Functionの詳細はvMix公式[Shortcut Function Reference](https://www.vmix.com/help29/ShortcutFunctionReference.html)をご確認ください。

---


## 5. 免責事項

本機は将来的な製品化に向けたデータ収集を目的とした評価試験機です。  
本機を使用したことによる**本番配信の停止、vMixのフリーズ、接続PCの故障、その他一切の二次的損害**について、開発者は責任を負いかねます。  
重要な現場で使用される際は、必ず事前の検証とバックアップ体制の確保をお願いいたします。  

本機の分解、解析、および内蔵ソフトウェアの抽出・転用を禁止します。  

---

## 6. ライセンス表示について

本機のファームウェアは、多数のオープンソースソフトウェアを利用して構築されています。これらはMITまたはApache 2.0ライセンスに基づき、著作権表示を条件に利用を許可されています。  
詳細なライブラリ一覧およびライセンス全文が必要な場合は、下記の連絡先までご請求ください。

---

## 7. よくある質問

- Q1. vMix以外のソフトウェアには対応していますか？
  - A1. 対応していません。
- Q2. vMixに接続が出来ません。
  - データ転送に対応しているケーブルかご確認ください。また、ネットワークアダプタとして認識されているかご確認ください。

---

## 8. お問い合わせ・フィードバック

不具合報告、機能要望、または現場での使用感などのフィードバックを心よりお待ちしております。  
SNSでの投稿は #Iryx をご利用ください。

* **開発元:** [未完成成果物研究所](https://github.com/Incomplete-Outputs-Lab)
* **Firmware:** [Flowing](https://github.com/FlowingSPDG)
* **Hardware:** [mizuyoukan](https://github.com/mizuyoukanao)
* **Contact:** [ruk1ium@gmail.com](mailto:ruk1ium@gmail.com)

---
