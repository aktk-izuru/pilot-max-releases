# Pilot Max installation / インストール

Download packages only from [Pilot Max Releases](https://github.com/aktk-izuru/pilot-max-releases/releases). Initial builds are for evaluation; consult each release's verification notes.

## macOS / Apple Silicon

1. macOS 26以降のApple Silicon MacでDMGを開き、Pilot Max.appをアプリケーションフォルダへコピーします。ユーザーの `~/Applications` に配置することもできます。
2. 初版はアドホック署名です。初回起動がブロックされたら、「システム設定 → プライバシーとセキュリティ → このまま開く」で、このアプリを許可してください。
3. Pilot Maxの「設定」でアクセシビリティと入力監視を許可します。Bluetooth利用時はBluetoothの許可も必要です。OSが求める場合はアプリを終了して開き直します。
4. PilotControllerなど、同じデバイスを操作するアプリを終了し、USBでPilot Proを接続します。接続表示を確認してから割り当てを保存します。

Open the DMG and copy Pilot Max to Applications (or your user's `~/Applications`). This first build is ad-hoc signed, so macOS may require **Privacy & Security → Open Anyway**. Grant Accessibility and Input Monitoring in Pilot Max's settings, plus Bluetooth when requested. Quit other applications controlling the same device. Grant permissions again after updates if macOS requests it; ad-hoc builds cannot promise persistent permission approval.

## Windows / x64

Windows 11 x64で `Pilot Max_*_x64-setup.exe` を実行します。ユーザー単位でインストールされ、初版にはWindowsのコード署名がありません。SmartScreenの警告が表示された場合は、ダウンロード元を確認してから「詳細情報 → 実行」を選択してください。WebView2が必要です。

Run the x64 NSIS installer on Windows 11. Installation is per user. Initial installers are unsigned; verify the download source before choosing **More info → Run anyway** in SmartScreen. WebView2 is required. Input into elevated applications can be blocked by Windows.

## 日常の使い方 / Everyday use

- デバイス図の操作子を選び、アクションを編集し「変更を保存」で適用します。
- アプリ別プロファイルに設定がなければ共通設定を継承します。「何もしない」で明示的に無効にできます。
- macOSのWineプロファイルはexeパスと任意のBottleで識別します。
- ウィンドウを閉じても常駐します。トレイ／メニューバーから設定・一時停止・マクロ停止・終了を操作できます。
- 更新は自動取得までを行い、「更新して再起動」を選ぶまで適用しません。設定は更新前にバックアップします。
- Select controls in the device diagram, edit actions and save. App profiles inherit common settings unless explicitly overridden. Closing the window keeps the app resident. Pause, stop macros, reopen settings or quit from the tray/menu bar. Updates download automatically but install only when you choose **Install and restart**.

If a control does not respond, open Device diagnostics and export a capture for the specific connection. Do not treat an unverified input as supported based solely on its presence in the diagram.
