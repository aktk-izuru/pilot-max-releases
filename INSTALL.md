# Pilot Max installation / インストール

Download packages only from [Pilot Max Releases](https://github.com/aktk-izuru/pilot-max-releases/releases). Initial builds are for evaluation; consult each release's verification notes.

## macOS / Apple Silicon

1. macOS 26以降のApple Silicon MacでDMGを開き、Pilot Max.appをアプリケーションフォルダへコピーします。ユーザーの `~/Applications` に配置することもできます。
2. Pilot Max専用の固定証明書で署名しています。AppleのDeveloper ID署名・公証は行っていません。初回起動がブロックされたら、「システム設定 → プライバシーとセキュリティ → このまま開く」で、このアプリを許可してください。
3. Pilot Maxの「設定」でアクセシビリティと入力監視を許可します。Bluetooth利用時はBluetoothの許可も必要です。OSが求める場合はアプリを終了して開き直します。
4. PilotControllerなど、同じデバイスを操作するアプリを終了し、USBでPilot Proを接続します。接続表示を確認してから割り当てを編集します。変更は自動保存され、すぐに適用されます。

0.1.3以降は同じ証明書とアプリ識別子を継続使用し、更新によってOSの権限判定用の識別条件が変わらないようにしています。0.1.2以前からの初回更新時は、権限を一度設定し直す必要がある場合があります。設定がオンでも操作できない場合は、アプリを終了し、該当する権限のPilot Maxの登録を削除して、更新後のアプリを登録し直してください。

Open the DMG and copy Pilot Max to Applications (or your user's `~/Applications`). The app uses a dedicated, persistent self-signed certificate; it is not Developer ID signed or notarized, so macOS may require **Privacy & Security → Open Anyway**. Grant Accessibility and Input Monitoring in Pilot Max's settings, plus Bluetooth when requested. Quit other applications controlling the same device. From 0.1.3 onward, updates retain the certificate and application identity used for permission checks. The first update from 0.1.2 or earlier may require granting permissions once more. If an enabled permission no longer works, quit the app and remove/re-add Pilot Max in that permission's settings.

## Windows / x64

Windows 11 x64で `Pilot Max_*_x64-setup.exe` を実行します。ユーザー単位でインストールされ、初版にはWindowsのコード署名がありません。SmartScreenの警告が表示された場合は、ダウンロード元を確認してから「詳細情報 → 実行」を選択してください。WebView2が必要です。

Run the x64 NSIS installer on Windows 11. Installation is per user. Initial installers are unsigned; verify the download source before choosing **More info → Run anyway** in SmartScreen. WebView2 is required. Input into elevated applications can be blocked by Windows.

## 日常の使い方 / Everyday use

- デバイス図の操作子を選び、アクションを編集します。変更は自動保存・即時適用され、「保存・適用済み」と表示されます。
- アプリ別プロファイルに設定がなければ共通設定を継承します。「何もしない」で明示的に無効にできます。
- macOSのWineプロファイルはexeパスと任意のBottleで識別します。
- ウィンドウを閉じても常駐します。トレイ／メニューバーから設定・一時停止・マクロ停止・終了を操作できます。
- macOSではDockにアイコンを表示せず、メニューバーに常駐します。設定画面を開き直すには、メニューバーのアイコンから「Pilot Max…」を選びます。
- 更新は起動時と6時間ごとに自動確認・取得します。「設定 → アプリの更新 → 今すぐ確認」で手動確認もできます。「更新して再起動」を選ぶまで適用せず、設定は更新前にバックアップします。
- Select controls in the device diagram, edit actions; changes save and apply automatically. App profiles inherit common settings unless explicitly overridden. Closing the window keeps the app resident. Pause, stop macros, reopen settings or quit from the tray/menu bar. Updates download automatically but install only when you choose **Install and restart**.
- On macOS, Pilot Max stays in the menu bar without a Dock icon. Choose **Pilot Max…** from its menu bar icon to reopen settings.

If a control does not respond, open Device diagnostics and export a capture for the specific connection. Do not treat an unverified input as supported based solely on its presence in the diagram.
