# ⚡ HID Remapper for E2mini Controller

イーグレットツーミニ向けコントローラーをSwitchで使うためのカスタムHID Remapperファームウェアや設定ファイルです。

カスタムファームは、Raspberry Pi Pico（RP2040）向けのものになります。

## ✨ Features

- 🎮 **Joystick → Switch Pad** — JoystickをSwitch用パッドとして使用するための設定
- 🖱️ **Trackball & Pad → Mouse** — トラックボールとパッドをマウスとして使用するための設定
- 🔧 **Custom HID Firmware** — トラックボールとパッドをSwitchにマウスとして認識させるカスタムファーム

## 🚀 Downloads

<details>
<summary><strong>📦 ファームウェアと設定ファイル</strong></summary>

### Custom Firmware

[**⬇ remapper.uf2 — ファームウェアをダウンロード**](https://github.com/ashisle375/HIDremapper-for-E2miniController/releases/download/v1.0/remapper.uf2)

Raspberry Pi Pico（RP2040）向けのカスタムファームウェアです。

### Configuration 1 — Joystick as Switch Pad

[**📄 hid-remapper-config-Joystick_as_SwitchPad.json**](https://github.com/ashisle375/HIDremapper-for-E2miniController/releases/download/v1.0/hid-remapper-config-Joystick_as_SwitchPad.json)

JoystickをSwitch用パッドとして使用するための設定ファイルです。

### Configuration 2 — Trackball & Pad as Mouse

[**📄 hid-remapper-config-tackball_and_pad_as_Mouse.json**](https://github.com/ashisle375/HIDremapper-for-E2miniController/releases/download/v1.0/hid-remapper-config-tackball_and_pad_as_Mouse.json)

トラックボールとパッドをマウスとして使用するための設定ファイルです。

</details>

## 🧩 Hardware

### Raspberry Pi Pico — RP2040

本プロジェクトでは、Raspberry Pi Pico互換のRP2040ボードを使用します。

購入したハードウェアの例：

- [AliExpress — 購入したボードの製品ページ](https://ja.aliexpress.com/item/1005012443032183.html?spm=a2g0o.order_list.order_list_main.5.7ecc585aWqqbq6&gatewayAdapt=glo2jpn)

上記はオリジナルのHIDremapperファームウェア書き込み済みで、配線などの手間も不要です。
もちろん、通常のRaspberry Pi Picoボードに自分でUSBコネクターやUSBケーブルを配線しても構いません。

### 必要なもの

- Raspberry Pi Pico互換ボード（RP2040）
- データ通信対応USBケーブル
- 使用するイーグレットツーミニ向けコントローラー（Joystick、パドル＆トラックボール）
- Configuration Toolを実行するPC

※ 商品ページは購入したハードウェアの一例です。すべての互換ボードでの動作を保証するものではありません。

## 🔥 Flashing the Firmware

※HIDremapper書き込み済みのボード（購入例）で、パドル＆トラックボールをSwitchで使用しない場合（Joystickのみの使用や、パドル＆トラックボールをPCで使用する場合）はファームウェアの書き換えは不要です。

### 1. UF2ファイルをダウンロード

[**⬇ ファームウェアをダウンロード**](https://github.com/ashisle375/HIDremapper-for-E2miniController/releases/download/v1.0/remapper.uf2)

### 2. BOOTSELモードで接続

1. Raspberry Pi PicoをUSBから取り外します。
2. 基板上の **BOOTSELボタン** を押したまま、USBケーブルを接続します。
3. PCに `RPI-RP2` ドライブが表示されたら、ボタンを離します。

### 3. ファームウェアを書き込む

ダウンロードした `remapper.uf2` を `RPI-RP2` ドライブにコピーします。

コピーが完了すると、基板は自動的に再起動します。

### 4. 接続を確認

再起動後、Configuration Toolからデバイスに接続できることを確認します。

## ⚙️ Configuration

設定には、HID Remapper公式のConfiguration Toolを使用します。

**[Open HID Remapper Configuration Tool →](https://www.remapper.org/config)**

Google ChromeやMicrosoft Edgeなど、WebHIDに対応したブラウザーを使用してください。

### 基本的な設定手順

1. HID RemapperをPCに接続します。
2. Configuration Toolを開き、デバイスに接続（メニューのOpenDevice押下後、HIDremapperを選択）します。
3. 設定画面から用途に合ったJSONファイルをインポートします。（メニューの二段目にあるActions選択後、Import JSONを押下してファイルを選択）
4. 入力マッピングと出力デバイスの設定を確認します。（JSONファイルが正しく読み込めていれば正しく設定されているはずです）
5. 設定をデバイスに保存します。（メニューのSave to Device押下）
6. 実際の入力デバイスで動作を確認します。

設定画面の名称や操作手順は、使用するバージョンによって異なる場合があります。

## 🎮 Configuration 1 — Joystick as Switch Pad

JoystickをSwitch用パッドとして使用するための設定です。

**[⬇ Joystick設定JSONをダウンロード](https://github.com/ashisle375/HIDremapper-for-E2miniController/releases/download/v1.0/hid-remapper-config-Joystick_as_SwitchPad.json)**

### 設定方法

1. [Configuration Tool](https://www.remapper.org/config) を開きます。
2. HID Remapperに接続します。
3. 上記のJSONファイルをダウンロードします。
4. 設定画面からJSONファイルをインポートします。
5. 入力マッピングと出力デバイスの設定を確認します。
6. 設定を保存し、Joystickの方向入力やボタン操作をテストします。

Switch側での認識や動作は、USB HIDの出力形式や接続環境によって異なる場合があります。

## 🖱️ Configuration 2 — Trackball & Pad as Mouse

トラックボールとパッドをマウスとして使用するための設定です。

**[⬇ Trackball & Pad設定JSONをダウンロード](https://github.com/ashisle375/HIDremapper-for-E2miniController/releases/download/v1.0/hid-remapper-config-tackball_and_pad_as_Mouse.json)**

### 設定方法

1. [Configuration Tool](https://www.remapper.org/config) を開きます。
2. HID Remapperに接続します。
3. 上記のJSONファイルをダウンロードします。
4. 設定画面からJSONファイルをインポートします。
5. トラックボールの移動とパッドの入力割り当てを確認します。
6. 設定を保存し、マウス操作をテストします。

### 確認ポイント

- トラックボールの移動がマウスカーソルに反映されること
- パッドに割り当てられた入力が意図した動作になること
- 接続先の機器でマウスとして認識されること

## 🙏 Acknowledgements

本プロジェクトは、**Jacek Fedoryński氏によるHID Remapper**をベースにしています。

- **Original Repository:** [jfedor2/hid-remapper](https://github.com/jfedor2/hid-remapper)
- **Official Website:** [remapper.org](https://www.remapper.org/)
- **Configuration Tool:** [remapper.org/config](https://www.remapper.org/config)

HID Remapperを開発・公開してくださった作者およびコントリビューターの皆様に、心より感謝いたします。

オリジナルプロジェクトの設計、USB HID処理、リマッピング機能、設定インターフェースは、本カスタムファームウェアの開発において重要な基盤となっています。

本リポジトリはオリジナルプロジェクトの公式リリースではなく、独自のカスタマイズ版です。

## 📜 License

 [MIT License](https://github.com/ashisle375/HIDremapper-for-E2miniController/blob/main/LICENSE)

オリジナルプロジェクトのライセンスおよび著作権表示については、[jfedor2/hid-remapper](https://github.com/jfedor2/hid-remapper) を参照してください。

