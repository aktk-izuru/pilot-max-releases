# コマンド実行とアプリ起動

コントロールを選択して「アクションを割り当てる」を押し、アクションから「任意コマンドを実行」または「アプリを開く」を選びます。マクロのアクションステップでも同じ設定を使えます。編集・保存だけでは実行されず、設定画面が最前面にある間は割り当ての実行を停止します。

## 任意コマンドを実行

macOSはzshのログインシェル、Windowsはcmd.exeで実行します。引数、引用符、パイプ、リダイレクトを含むコマンドを入力できます。macOSの例は `say "Hello from Pilot Max"`、Windowsの例は `echo Hello > "%TEMP%\pilot-max.txt"` です。PowerShellを使う場合は `powershell.exe -NoProfile -Command "..."` のように指定します。

「作業フォルダー」は参照ボタンから選択するか、絶対パスを入力します。空欄はユーザーのホームフォルダーです。パス欄の外側に引用符を付ける必要はありません。`~/`（Windowsでは `~\` も）を使えます。macOSではログイン時のシェル設定を読み込みますが、対話用の `.zshrc` は読み込みません。

ターミナルを表示せずバックグラウンドで開始します。対話入力はできません。標準出力・標準エラーは表示されないため、ログが必要な場合はコマンドでファイルにリダイレクトしてください。開始失敗や0以外の終了コードは「デバイス診断」に表示します。

## アプリを開く

macOSは `.app`、Windowsは `.exe` を参照ボタンから選択します。Windowsの `.lnk` ショートカット自体を開く場合は、パスを直接入力してください。ショートカットに保存された引数も利用されます。パスに引用符は不要です。macOSでは起動済みのアプリを前面に表示します。アプリ独自の引数を指定したい場合は「任意コマンドを実行」を使います。

## マクロと停止

マクロはコマンドの終了やアプリの準備完了を待たずに次へ進みます。起動後にキー操作などを行う場合は、待機ステップを追加し、「アプリが切り替わっても続行する」を有効にしてください。適切な待機時間はアプリによって異なります。

一時停止、マクロ停止、プロファイル切り替え、Pilot Maxの終了では、開始済みの外部コマンドやアプリを終了しません。同時に追跡するコマンドと起動処理は最大16件です。コマンド自身が切り離して起動する子プロセスはこの制限に含みません。

## English

Choose **Run command** or **Open application** in a control assignment or macro action step. Commands run in a macOS zsh login shell or Windows cmd.exe, with shell arguments, quotes, pipes and redirection preserved. The optional working folder defaults to your home; enter an absolute path or use `~/` (`~\` also works on Windows). Directory and application path fields do not need surrounding quotes.

Choose a macOS `.app` or Windows `.exe` using the browse button. To open a Windows `.lnk` itself with its saved arguments, enter its full path directly. macOS activates an already running application. Use **Run command** when you need custom application arguments.

Execution starts in the background with no terminal or interactive stdin. Redirect output if you need a log; launch failures and nonzero exit status appear in Device diagnostics. Loading, editing, saving and browsing never execute the action. Assignments are suspended while the settings window is in front.

Macros proceed without waiting for completion. Add a wait before subsequent input and enable **Continue after switching applications** when necessary. Stopping a macro, pausing or exiting Pilot Max does not terminate an external process that has already started. Up to 16 active commands/launch dispatches are tracked; processes detached by the command itself are outside this limit.
