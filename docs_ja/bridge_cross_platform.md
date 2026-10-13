# Bridge: ユーザー向けインストール & プラットフォームガイド

## 要約

Bridge はコードを一から書き直したもので、現在ベータテスト中です。一部の機能はまだ利用できない、または不具合がある場合があります。問題が発生した場合は、アプリ内のフィードバック機能から開発者にご連絡ください。アプリ内のデータ移行オプションはベストエフォートで提供されており、一部の旧バージョンのデータについては、移行が不完全であったり、利用できなかったりする場合があります。

**すぐにインストールするには:**

* **iPhone / watchOS:** [TestFlight 経由で Bridge](https://testflight.apple.com/join/cNQxMjAu) をインストールします。
* **Android スマートフォン / Wear OS ウォッチ:** [bridge-x-testers Google グループ](https://groups.google.com/g/bridge-x-testers)に参加し、[Google Play テスト](https://play.google.com/apps/testing/com.orienlabs.bridge.wear)からインストールするか、[最新の APK をダウンロード](https://github.com/orienlabs/bridge_app/releases)してください（[リリースページ](https://github.com/orienlabs/bridge_app/releases)も参照）。

> [!IMPORTANT]
> **重要なお知らせ: Bridge をゼロから再構築しました**
> 
> Apple と Android の両エコシステムにまたがる、真のクロスプラットフォーム体験を提供するため、Bridge アプリを根本から作り直しています。この大きな移行に伴い、次の点にご注意ください。
> 
> * **対応デバイスの拡大:** 最低限必要な OS バージョンを引き下げ、より古いスマートフォンやウォッチのモデルでも Bridge を利用できるようにしました。
> * **ベストエフォートのデータ移行:** 以前の旧アプリのデータについては、アプリ内の移行オプションを利用できますが、一部のデータは移行が不完全であったり、利用できなかったりする場合があります。
> * **同時アップグレードが必須:** 新しい独自通信プロトコルを採用したため、**ペアリングと同期を行うには、スマートフォンとウォッチの両方のアプリを新バージョンにアップグレードする必要があります**。新バージョンのアプリは、旧バージョンとはペアリングできません。

## 1. Bridge とは？ なぜ必要なのか？

スマートウォッチとスマートフォンは、従来それぞれのエコシステムに縛られており、デバイスを自由に組み合わせたいユーザーの選択肢は限られていました。たとえば、Apple Watch と Android スマートフォンのペアリングは標準ではサポートされておらず、Wear OS スマートウォッチを iPhone と組み合わせると、機能が大きく制限されることがよくあります。

Bridge はこうしたプラットフォームの壁を取り払います。省電力の独自 Bluetooth 通信プロトコルを利用することで、対応するあらゆるスマートウォッチを、対応するあらゆるスマートフォンと直接ペアリングして同期できます。通知のミラーリング、ヘルスケア・アクティビティデータの同期、メディア再生の操作など、Bridge はブランドや OS を問わずデバイスをつなぐ汎用的なリンクとして機能します。

### 互換性マトリクス
以下の表は、対応するスマートウォッチとスマートフォンの組み合わせ、およびそれぞれで利用できる機能の一覧です。

> [!TIP]
> **マルチデバイスペアリング対応:** Bridge は両側でマルチデバイスペアリングに対応しました。1 台のスマートウォッチを複数のスマートフォン（たとえば個人用と仕事用）とペアリングでき、1 台のスマートフォンで複数のスマートウォッチに同時に接続して管理することもできます。

| スマートウォッチのプラットフォーム | スマートフォンのプラットフォーム | 対応する主な機能 |
| :--- | :--- | :--- |
| **Apple Watch**（watchOS） | **iPhone**（iOS） | 通知のミラーリング、ヘルスケア/ワークアウトデータの同期、メディア操作、設定の同期 |
| **Apple Watch**（watchOS） | **Android スマートフォン** | 通知のミラーリング、ワークアウトデータの同期、メディア再生の操作 |
| **Wear OS ウォッチ** | **iPhone**（iOS） | 通知のミラーリング、ヘルスケア同期（Apple ヘルスケアと連携）、メディア操作 |
| **Wear OS ウォッチ** | **Android スマートフォン** | 通知のミラーリング、ヘルスケア同期（Google ヘルスコネクトと連携）、メディア操作 |

### 対応 OS バージョンとプラットフォームの制限
以下は、アプリの設定から直接確認した最低限のソフトウェア要件と、プラットフォームごとの注意点です。

| デバイスプラットフォーム | 対応する最低 OS バージョン | 主な機能と制限事項 |
| :--- | :--- | :--- |
| **Android スマートフォン** | Android 8.0（Oreo / API 26）以降 | • 通知のミラーリングとメディア操作には Android 8.0 以上が必要です。<br>• **ヘルスケアデータの同期（ヘルスコネクト）** には、Android 9.0 以上（Google Play からダウンロード）または Android 14 以上（システムに組み込み済み）が必要です。 |
| **Android Wear OS ウォッチ** | Wear OS 2.0（Android 8.0 / API 26）以降 | • 基本的な通知のミラーリングとメディア操作には Wear OS 2.0 以上が必要です。<br>• **ヘルスケアデータの同期**は、Google Health Services のシステム要件により、**Wear OS 3.0（Android 11 / API 30）以降でのみ**利用できます。 |
| **iPhone（iOS）** | iOS 15.0 以降 | • 通知とヘルスケア同期のすべての機能を利用するには iOS 15.0 以上が必要です。<br>• バックグラウンド同期には、Bluetooth 共有とバックグラウンド App 更新を有効にする必要があります。アプリを長期間閉じたままにすると、iOS がバックグラウンド動作を制限する場合があります。 |
| **Apple Watch（watchOS）** | watchOS 9.6 以降 | • ネイティブのワークアウト記録と心拍数の同期に対応しています。<br>• バックグラウンドでの継続的なヘルスケア記録には、ワークアウトセッションの権限が必要です。<br>• TestFlight によるベータテストは、ファミリー共有設定の Apple Watch ではサポートされていません。 |

---

## 2. 早期アクセスのリクエスト（ベータテスト）

Bridge は現在、**非公開の内部テスト**中です。アプリをダウンロードしてインストールするには、まずお客様のアカウント ID を承認済みテスターリストに追加する必要があります。

> [!TIP]
> **Google グループ経由で Wear OS ウォッチ版にすぐアクセス:**
> メールによる手動の登録を待たずに、Wear OS アプリのテスト版にすぐアクセスできます。[bridge-x-testers Google グループ](https://groups.google.com/g/bridge-x-testers)に参加するだけです。参加後、[Google Play](https://play.google.com/apps/testing/com.orienlabs.bridge.wear) からテストに参加し、アプリを直接インストールできます。

### ステップ 1: テスター ID を送信する
[早期アクセスをリクエスト](mailto:bridge@olabs.app?subject=Request%20for%20Bridge%20Early%20Access&body=Hello,%0A%0AI%20would%20like%20to%20request%20early%20access%20to%20the%20Bridge%20beta.%20Here%20are%20my%20details:%0A%0A-%20Apple%20ID%20(for%20TestFlight/iOS):%20%0A-%20Google%20Play%20Email%20(for%20Android/Wear%20OS):%20%0A%0AThanks!)をクリックしてください。`bridge@olabs.app` が宛先に入力済みのメール下書きが、既定のメールクライアントで開きます。

次の情報を入力してください。
* **Apple ID**（iPhone と Apple Watch 向けの TestFlight 招待を受け取るため）。
* **Google Play のメールアドレス**（Android と Wear OS 向けに、Google Play Console の内部テストトラックへ追加されるため）。

アカウントを追加したら、TestFlight と Google Play の正式なダウンロードリンクを返信でお送りします。

### ステップ 2: APK による代替インストール（Android のみ）
Google Play Console への登録を待ちたくない場合、Android と Wear OS のユーザーはアプリのパッケージ（APK）をダウンロードして手動でインストールできます。[Wear OS 用 APK](https://olabs.app/assets/release/bridge-x_wearos.apk) を直接ダウンロードするか、[GitHub リリースページ](https://github.com/orienlabs/bridge_app/releases/)で詳細をご確認ください。

---

## 3. Apple デバイス（iPhone と Apple Watch）のインストールガイド

Apple ID がテスターリストに追加されたら、TestFlight をインストールし、iPhone で [Bridge の TestFlight 招待リンク](https://testflight.apple.com/join/cNQxMjAu)を開いてください。

### A. iPhone にインストールする
1. TestFlight アプリをお持ちでない場合は、App Store からインストールします。
2. [Bridge の TestFlight 招待リンク](https://testflight.apple.com/join/cNQxMjAu)を開きます。
3. 表示された場合は **「TestFlight で表示」** をタップします。
4. TestFlight アプリで **Bridge** の招待を承諾し、**「インストール」** をタップします。

### B. 標準的な Apple Watch（iPhone とペアリング済み）にインストールする
Apple Watch が個人の iPhone とペアリングされている場合:
1. **iPhone の TestFlight アプリ**を開きます。
2. テスト一覧の **Bridge** アプリをタップします。
3. **Apple Watch** セクションまでスクロールし、**「インストール」** をタップしてウォッチに導入します。

### C. ファミリー共有設定の Apple Watch（ペアリングされた iPhone なし）にインストールする
子どもや高齢者など、自分の iPhone を持たない家族のためにウォッチを設定する場合:
1. *注: ファミリー共有設定のウォッチでは TestFlight がサポートされていないため、リリース後に App Store からインストールするか、開発テスト中に Xcode で直接サイドロードする必要があります。*
2. アプリが一般公開された後（または限定公開リンクで配布された後）は、ユーザーが **Apple Watch 上で直接 App Store アプリ**を開き、**Bridge** を検索して、そのままダウンロードできます。

---

## 4. Android デバイス（Android スマートフォンと Wear OS）のインストールガイド

Google Play のメールアドレスがテスターリストに追加され、テスト用リンクを受け取ったら:

### A. Android スマートフォンにインストールする
1. Google Play のメールアドレス宛てに送られたテスト招待リンクを開きます。
2. **「ウェブで参加」** または **「Android で参加」** をタップして、内部テストプログラムに参加します。
3. 提供されたリンクから、Google Play ストアで **Bridge** をダウンロードします。
4. *（代替方法）* [GitHub リリースページ](https://github.com/orienlabs/bridge_app/releases/)からスマートフォン用 APK を直接ダウンロードし、スマートフォンで開いてインストールします（「提供元不明のアプリのインストール」の許可が必要です）。

### B. Wear OS スマートウォッチにインストールする

#### オプション 1: Google Play ストア（テスターグループ経由）
1. ウォッチ/スマートフォンで有効な Google アカウントで、[bridge-x-testers Google グループ](https://groups.google.com/g/bridge-x-testers)に参加します。
2. グループに参加したら、[Google Play 上の Bridge Wear OS テスト用リンク](https://play.google.com/apps/testing/com.orienlabs.bridge.wear)を開きます。
3. テストプログラムに参加し、Google Play ストアから Wear OS ウォッチに **Bridge** を直接インストールします。

#### オプション 2: ADB による APK の直接インストール
* [Wear OS 用 APK をダウンロード](https://olabs.app/assets/release/bridge-x_wearos.apk)します。詳細は[最新の GitHub リリース](https://github.com/orienlabs/bridge_app/releases)をご覧ください。
* APK をウォッチに転送し、ADB を使ってインストールします。[ADB インストールガイド](guides/install-via-adb.md)を参照してください。

#### オプション 3: ファイルブラウザによる代替インストール
* [ファイルブラウザアプリ](https://play.google.com/store/apps/details?id=com.orienlabs.filebrowser.wear)を使って、APK をウォッチに転送します。
* ファイルブラウザアプリが APK のインストールに対応している場合は、ウォッチ上で APK を開き、表示される案内に従ってインストールします。

---

## 5. アプリを最新の状態に保つ

最適な体験のため、自動更新をオンにしておくことをおすすめします。
* **Apple Watch:** ウォッチの「設定」➜「App Store」で **「自動ダウンロード」** をオンにします。
* **Wear OS ウォッチ:** ウォッチで Play ストアを開き、下にスワイプして設定を開き、**「アプリを自動更新」** をオンにします。
* **スマートフォン:** App Store（iOS）または Google Play ストア（Android）で自動更新を有効にします。

---

## 6. お困りですか？

インストール、ペアリング、データ同期の過程で問題が発生した場合は、次の点をご確認ください。
* 両方のデバイスで Bluetooth と Wi-Fi が有効になっていること。
* 初期設定中に求められたすべての権限（Bluetooth、バックグラウンド同期、ヘルスケアへのアクセスなど）を許可していること。
* 解決しない場合は、[bridge@olabs.app](mailto:bridge@olabs.app) まで開発チームに直接メールでご連絡ください。
