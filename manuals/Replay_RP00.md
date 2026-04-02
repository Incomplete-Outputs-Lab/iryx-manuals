# vMixコントローラー Iryx Replay RP-00 取扱説明書

## 目次

- [1. はじめに](#section-1)
- [2. 安全上のご注意](#section-2)
- [3. 動作環境](#section-3)
  - [3.1 製品の種類（LAN搭載とUSB専用）](#section-3-1)
- [4. 使用方法](#section-4)
  - [4.1 接続方法](#section-4-1)
  - [4.2 メイン画面の表示内容](#section-4-2)
  - [4.3 操作の全体像](#section-4-3)
  - [4.4 メニュー内のボタン対応](#section-4-4)
  - [4.5 メニュー階層](#section-4-5)
  - [4.6 キーマトリクスとショートカット（メイン画面）](#section-4-6)
  - [4.7 回転エンコーダ（ジョグ）](#section-4-7)
  - [4.8 Tバー（スライド）](#section-4-8)
  - [4.9 LEDの意味（目安）](#section-4-9)
- [5. 免責事項](#section-5)
- [6. ライセンス表示について](#section-6)
- [7. よくある質問](#section-7)
- [8. お問い合わせ・フィードバック](#section-8)

<a id="section-1"></a>

## 1. はじめに

本製品は、vMixのリプレイ操作に特化したコントローラーです。  
vMixの状態取得および操作をTCP API経由で行うための評価用試作機です。  
本製品は現在開発中です。完成次第Boothでの頒布を予定しています。  
**本製品の転売・譲渡を固く禁止します。**

---

<a id="section-2"></a>

## 2. 安全上のご注意

本製品は開発中の試作品であり、一般的な市販製品と同等の保護機能を備えていない場合があります。

* 電源: USB-Cから直接給電が可能です。PCのUSBポートに接続してください。
* 環境: ライブ配信現場などの機材密集地で使用する場合、排熱を妨げないように設置してください。
* 異常時: 本体が異常に熱くなる、焦げた臭いがする等の場合は直ちにUSBケーブルを抜いてください。

---

<a id="section-3"></a>

## 3. 動作環境

- vMixのReplay機能が利用できること（バージョンはvMix側の要件に従います）
- (USBモード) USB CDC-NCMに対応したWindows（Windows 10 Version 1903以降、Windows 11）
- (USBモード) データ転送可能なUSB-Cケーブル(USB 1.1 Full-speed)
- (LANモード) 100BASE-TX規格に対応したネットワーク

<a id="section-3-1"></a>

### 3.1 製品の種類（LAN搭載とUSB専用）

本体には、次の2種類があります。ネットワークの取り扱いが異なるので、お手元の機種に合わせてください。

| 区分 | 特徴 | ネットワーク |
| :--- | :--- | :--- |
| LAN搭載モデル | 有線LANポート付き | 有線LANとUSB接続のどちらを使うかを、保存された接続方法に従います（初期は有線LAN） |
| USB専用モデル | 有線LANポートなし | USB接続のみ。起動時に接続方法はUSBに固定されます |

資料によっては、このUSB専用モデルを「USB非搭載版」と書くことがあります。ここでは**有線LANがない**ことを指し、USBケーブルによる接続は行います。

<a id="section-3-1-lan"></a>

#### LAN搭載モデル

- 起動時は保存領域に記録された接続方法（LANまたはUSB）に従います。
- リプレイパネル単体の画面には、接続方法の切替やvMixのIP・LANのDHCP／固定IPを編集するメニューはありません。別途、同系統の試作機で設定した値が保存領域に入っている場合は、その内容で接続します。
- 有線LANを選んでいるときは、LAN側のvMix接続先が使われます。USBを選んでいるときは、USBテザー用の接続先（`172.31.x.2` 側）が使われます。

<a id="section-3-1-usb-only"></a>

#### USB専用モデル（有線LAN非搭載の構成）

- 有線Ethernetを使わない構成では、接続方法はUSBに固定されます。LANポートはありません。
- PCとはデータ転送対応のUSBケーブルで接続し、本機とvMix用PCのIPは、[4.1.1 接続方法(USBモード)](#section-4-1-1)（`172.31.x.x`）と同様の考え方になります。
- 画面の Status では `Link: USB` と表示されます。
- 上記のとおり、本機の画面からネットワークや接続先を編集する操作はできません。

---

<a id="section-4"></a>

## 4. 使用方法

<a id="section-4-1"></a>

### 4.1 接続方法

<a id="section-4-1-1"></a>

#### 4.1.1 接続方法(USBモード)

PCと本機を、データ転送対応のUSBケーブルで接続してください。  
イーサネットアダプターとして認識され、本機のIPに `172.31.x.1` が割り当てられます（サブネットの第3オクテット `x` は保存領域の値が使われます）。  
複数台を同一PCに接続する場合はIPの重複を避けるため、別途設定手段で第3オクテットを変えた値を保存してください。

<a id="section-4-1-2"></a>

#### 4.1.2 接続方法(LANモード)

LAN搭載モデルで、接続方法がLANに設定されている場合に限ります。  
本機にUSBで給電し、LANケーブルを接続してください。DHCP対応環境の場合、自動的にIPが設定されます。  
接続先のvMixのIPは保存領域に記録された値が使われます。  
DHCPに対応していない環境の場合、IPを手動で保存領域へ入れる必要があります（本機の画面からは編集できません）。

<a id="section-4-2"></a>

### 4.2 メイン画面の表示内容

電源投入後、通常は Status 画面が表示されます。

| 表示行 | 内容 | 補足 |
| :--- | :--- | :--- |
| （見出し） | `Iryx Replay` | 製品名 |
| TCP | `TCP: connected` / `TCP: disconnected` | vMixとのTCP接続状態 |
| Target | `vMixのIP:ポート` | 接続先 |
| This IP | 本機のIPv4 | 未取得時は `0.0.0.0` など |
| Link | `LAN` または `USB` | 現在の接続方法 |
| Version | vMixから取得した文字列 | 未取得時は `Version: —` |
| Menu | `Menu: open menu` | メニュー操作の案内 |

<a id="section-4-3"></a>

### 4.3 操作の全体像

- 6×6のキーマトリクス、回転エンコーダ、スライド式のTバー（可変抵抗）があります。
- 左上のキーが Shift です。他のキーと組み合わせると、別のショートカットになります。
- メニューを開いている間は、リプレイ用のコマンドは送られず、メニュー操作にキーが割り当てられます。

<a id="section-4-4"></a>

### 4.4 メニュー内のボタン対応

メニュー表示中は、次のように割り当てられます。

| 物理ボタン | 意味 |
| :--- | :--- |
| Clip 前後（クリップを選ぶ左右のキー） | カーソル上／下 |
| Menu | メニューを開く（メイン画面から）／メニュー内では未使用 |
| Back | 戻る |
| Enter | 決定 |

メイン画面のフッタには `Menu / Back / Enter` と表示されます。

<a id="section-4-5"></a>

### 4.5 メニュー階層

<a id="section-4-5-1"></a>

#### 4.5.1 メインメニュー

| 行 | 選択 | 遷移先 |
| :--- | :--- | :--- |
| [1] | Reset replay defaults | [初期値に戻す確認画面へ](#section-4-5-2) |
| [2] | Help (URL) | ヘルプ（表示内容は書き込み済みの機種により異なります） |
| [3] | License | ライセンス抜粋の案内 |
| [4] | Reboot | 本体の再起動 |

<a id="section-4-5-2"></a>

#### 4.5.2 Reset replay defaults（確認画面）

「Reset replay tuning to firmware defaults?」と表示されます。  
Enter で確定すると、リプレイ関連の内部パラメータ（ジョグの刻み幅、クイッククリップの秒数、複合シーケンスの待ち時間など）が初期値に戻り、保存領域へ書き込まれます。Back でキャンセルします。

TC-00にあるような「Settings」一式（vMix IPの編集、LAN/USBの切替、トランジション設定など）は、本機の画面にはありません。

<a id="section-4-6"></a>

### 4.6 キーマトリクスとショートカット（メイン画面）

行は上から0行目、列は左から0列目とします。メニュー表示中は [4.4 メニュー内のボタン対応](#section-4-4) の動作になります。

| 位置 | 通常 | Shift併用 |
| :--- | :--- | :--- |
| (0,0) Shift | （修飾キー） | — |
| (0,1) Clip 前 | `ReplaySelectPreviousEvent` | `ReplaySelectFirstEvent` |
| (0,2) Clip 後 | `ReplaySelectNextEvent` | `ReplaySelectLastEvent` |
| (0,3)～(0,5) | ユーザースクリプト1～3 | Shift時は5～7番のスクリプトを起動 |
| (1,0)～(1,3) | `ReplaySelectChannelA`～`D` | 同左 |
| (1,4)～(1,5) | ユーザースクリプト4～5 | Shift時は4→8番、5→5番のスクリプトを起動 |
| (2,0) Jump In | `ReplayJumpToSelectedInPoint` | 同左 |
| (2,1) Jump Out | `ReplayJumpToSelectedOutPoint` | 同左 |
| (2,2) Play | `ReplayPlay` | 送信なし（Playのみ有効） |
| (2,3) Pause | `ReplayPause` | 同左 |
| (2,4) Play Out | [下記「Play Out」](#section-4-6-play-out) | 同左 |
| (2,5) Rec | `ReplayStartRecording` | `ReplayStopRecording` |
| (3,0)～(3,5) | `ReplayCamera1`～`ReplayCamera6` | `ReplaySelectedEventSingleCameraOn`（値1～6） |
| (4,0)～(4,1) | `ReplayCamera7`～`ReplayCamera8` | 同上（値7～8） |
| (4,2) Mark In | `ReplayMarkIn` | `ReplayUpdateSelectedInPoint` |
| (4,3) Mark Out | `ReplayMarkOut` | `ReplayUpdateSelectedOutPoint` |
| (4,4) Jump To Now | [下記「Jump To Now」](#section-4-6-jump-to-now) | [同左](#section-4-6-jump-to-now) |
| (4,5) Quick Clip | [下記「Quick Clip」](#section-4-6-quick-clip) | [同左](#section-4-6-quick-clip) |
| (5,0) Copy | `ReplayCopySelectedEvent` | `ReplayDuplicateSelectedEvent` |
| (5,1) Delete | 送信なし | `ReplayDeleteSelectedEvent` |
| (5,2) Menu | メニューへ | — |
| (5,3) Back | メニュー操作 | — |
| (5,4) Enter | メニュー操作 | — |
| (5,5) | 未使用 | — |

物理キーに割り当てがあるのはユーザースクリプト1～5までです。6～8番は、Shiftを押しながら1～4番のキーを押すと起動します（5番キーをShiftと押すと5番のままです）。vMix側では `Iryx_RP00_UserScript1`～`Iryx_RP00_UserScript8` という名前のスクリプトを用意し、`ScriptStart` で起動します。

<a id="section-4-6-play-out"></a>

#### Play Out

`ReplayPlayAllEvents` を送ります。内部設定により、短い動作に留めるか、一定時間待ってから `ReplayPause` まで送るかが切り替わります。Shiftの解釈を反転する設定が保存領域に入っている場合があります。

<a id="section-4-6-jump-to-now"></a>

#### Jump To Now

通常は `ReplayJumpToNow` のあと、内部で決めたフレーム数だけ `ReplayJumpFrames` を送り、待ってから `ReplayPlay` まで行う一連の動作です。Shiftを押しているときは `ReplayJumpToNow` のみです。

<a id="section-4-6-quick-clip"></a>

#### Quick Clip

押した瞬間に、マークの入りと秒数指定の入出点、のどちらか一方が送られます。離したときに、もう一方のパターンでは `ReplayMarkOut` が送られます。Shiftの解釈を反転する設定が保存領域に入っている場合があります。秒数は内部パラメータで決まります。

<a id="section-4-7"></a>

### 4.7 回転エンコーダ（ジョグ）

一定時間回転が止まると、溜めた分だけまとめて `ReplayJumpFrames` が送られます。  
Shiftを押しながら回すと、1ステップあたりのフレーム数が大きくなります（通常時とShift時で別々に保存されています）。  
「Reset replay defaults」でこれらは初期値に戻ります。

<a id="section-4-8"></a>

### 4.8 Tバー（スライド）

アナログ値から `ReplaySetSpeed` を送ります。値は0.0から1.0の範囲です。変化が小さいときは送信を省略して負荷を抑えます。

<a id="section-4-9"></a>

### 4.9 LEDの意味（目安）

キーを押している間、そのキーに対応する位置が発光します。  
再生中・録画中・チャンネル選択・アングル選択などは、vMixから届く状態に応じて色が変わります。詳細は現場の光量や見え方に依存するため、まずはvMix側の表示とあわせて確認してください。

---

<a id="section-5"></a>

## 5. 免責事項

本機は将来的な製品化に向けたデータ収集を目的とした評価試験機です。  
本機を使用したことによる本番配信の停止、vMixのフリーズ、接続PCの故障、その他一切の二次的損害について、開発者は責任を負いかねます。  
重要な現場で使用される際は、必ず事前の検証とバックアップ体制の確保をお願いいたします。

**本機の分解、解析、および内蔵ソフトウェアの抽出・転用、転売・譲渡を固く禁止します。**

---

<a id="section-6"></a>

## 6. ライセンス表示について

本機のソフトウェアは、多数のオープンソースソフトウェアを利用して構築されています。MITまたはApache 2.0等のライセンスに基づき、著作権表示を条件に利用を許可されています。  
画面上の License に主要名の抜粋が表示されます。詳細な一覧やライセンス全文が必要な場合は、下記の連絡先までご請求ください。

---

<a id="section-7"></a>

## 7. よくある質問

- Q1. vMix以外のソフトウェアには対応していますか？  
  A1. 対応していません。

- Q2. vMixに接続ができません。  
  A2. USBモードの場合、ネットワークアダプタとして認識されているかご確認ください。LANモードの場合は、保存された接続先が正しいか、ケーブルやルータ側の設定を確認してください。

- Q3. メニューに「Settings」がなく、IPを変えられません。  
  A3. 本機の画面からは編集できません。別途、開発者が案内する方法で保存内容を書き換えるか、同系統の別試作機で設定してください。

- Q4. ボタン操作が効かない  
  A4. シャットダウン後もUSBの電源を供給するPCの場合に、稀に応答が不安定になることがあります。電源を抜き差しし、再起動してください。

---

<a id="section-8"></a>

## 8. お問い合わせ・フィードバック

不具合報告、機能要望、または現場での使用感などのフィードバックを心よりお待ちしております。  
SNSでの投稿は #Iryx をご利用ください。

* 開発元: [未完成成果物研究所](https://incomplete-outputs-lab.github.io)
* ファームウェア開発: [Flowing](https://github.com/FlowingSPDG)
* 回路設計・基板筐体制作: [mizuyoukan](https://github.com/mizuyoukanao)
* Contact: [ruk1ium@gmail.com](mailto:ruk1ium@gmail.com)

---
