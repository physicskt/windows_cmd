# 💻 Windows コマンドプロンプト完全攻略ガイド

Windows のコマンドプロンプトでよく使用される代表的なコマンドと使い方を、わかりやすく楽しく解説します！ 🚀

## 📁 ファイル・ディレクトリ操作

### `dir` - ディレクトリの中身を表示
```cmd
dir                    # 現在のディレクトリ内容を表示
dir C:\Users           # 指定したディレクトリの内容を表示
dir *.txt              # txt ファイルのみ表示
dir /s                 # サブディレクトリも含めて表示
```

### `cd` - ディレクトリの移動
```cmd
cd Documents           # Documents フォルダに移動
cd ..                  # 一つ上のディレクトリに移動
cd \                   # ルートディレクトリに移動
cd /d D:\              # ドライブも含めて移動
```

### `tree` - フォルダ構造をツリー表示
```cmd
tree                   # 現在のディレクトリ構造を表示
tree /f                # ファイルも含めて表示
tree C:\Windows /a     # ASCII文字でツリー表示
```

### `mkdir (md)` - ディレクトリ作成
```cmd
mkdir NewFolder        # NewFolder という名前のディレクトリを作成
md "My Documents"      # スペースを含む名前の場合はダブルクォートで囲む
```

### `rmdir (rd)` - ディレクトリ削除
```cmd
rmdir OldFolder        # 空のディレクトリを削除
rmdir /s /q TempDir    # ディレクトリと中身を確認なしで削除
```

## 📄 ファイル操作コマンド

### `copy` - ファイルのコピー
```cmd
copy file.txt backup.txt      # ファイルをコピー
copy *.txt D:\Backup\         # すべての txt ファイルをコピー
copy /y source.txt dest.txt   # 確認なしで上書きコピー
```

### `move` - ファイル・フォルダの移動/名前変更
```cmd
move file.txt Documents\      # ファイルを Documents フォルダに移動
move oldname.txt newname.txt  # ファイル名を変更
```

### `del` - ファイル削除
```cmd
del file.txt           # ファイルを削除
del *.tmp              # 拡張子が tmp のファイルをすべて削除
del /q /f locked.txt   # 確認なしで強制削除
```

### `type` - ファイル内容の表示
```cmd
type readme.txt        # ファイルの内容を表示
type *.txt             # 複数ファイルの内容を順番に表示
```

### `attrib` - ファイル属性の変更
```cmd
attrib +h secret.txt   # ファイルを隠しファイルにする
attrib -r readonly.txt # 読み取り専用属性を解除
attrib +r +s +h file   # 読み取り専用・システム・隠しファイル属性を設定
```

## 🔍 検索・フィルタコマンド

### `find` - 文字列検索
```cmd
find "error" log.txt   # log.txt から "error" という文字列を検索
find /i "hello" *.txt  # 大文字小文字を区別せずに検索
find /c "line" file.txt # マッチした行数をカウント
```

### `findstr` - より高度な文字列検索
```cmd
findstr "pattern" *.log    # パターンマッチング検索
findstr /r "^Error" log    # 正規表現を使用（行頭の "Error"）
findstr /i /s "TODO" *.cs  # 大文字小文字無視でサブディレクトリも検索
```

## 🌐 ネットワークコマンド

### `ping` - ネットワーク接続テスト
```cmd
ping google.com        # google.com への接続テスト
ping -t 192.168.1.1    # 連続して ping を送信
ping -n 5 example.com  # 5回だけ ping を送信
```

### `ipconfig` - ネットワーク設定表示
```cmd
ipconfig               # 基本的な IP 設定を表示
ipconfig /all          # 詳細なネットワーク情報を表示
ipconfig /release      # IP アドレスを解放
ipconfig /renew        # IP アドレスを再取得
ipconfig /flushdns     # DNS キャッシュをクリア
```

### `tracert` - パケットの経路追跡
```cmd
tracert google.com     # google.com までの経路を追跡
tracert -h 15 server   # 最大 15 ホップまで追跡
```

### `netstat` - ネットワーク接続状況表示
```cmd
netstat -a             # すべての接続とリスニングポートを表示
netstat -b             # 各接続に関連するプログラムを表示
netstat -n             # アドレスとポート番号を数値で表示
```

## 🖥️ システム情報・管理コマンド

### `systeminfo` - システム情報表示
```cmd
systeminfo             # 詳細なシステム情報を表示
systeminfo | findstr "System Type"  # システムタイプのみ抽出
```

### `tasklist` - 実行中のプロセス一覧
```cmd
tasklist               # 実行中のプロセス一覧を表示
tasklist /svc          # サービス情報も含めて表示
tasklist | findstr "notepad"  # notepad プロセスを検索
```

### `taskkill` - プロセス終了
```cmd
taskkill /im notepad.exe      # notepad.exe を終了
taskkill /pid 1234 /f         # プロセス ID 1234 を強制終了
taskkill /im "*.exe" /t       # 実行ファイルとその子プロセスを終了
```

## 🔧 システムメンテナンス

### `sfc` - システムファイルチェック
```cmd
sfc /scannow           # システムファイルの整合性をチェックして修復
sfc /verifyonly        # チェックのみ実行（修復は行わない）
```

### `chkdsk` - ディスクチェック
```cmd
chkdsk C:              # C ドライブの基本チェック
chkdsk C: /f           # エラーを自動修復
chkdsk C: /r           # 不良セクタの回復も実行
```

### `runas` - 別のユーザーとしてコマンド実行
```cmd
runas /user:Administrator cmd    # Administrator としてコマンドプロンプトを起動
runas /savecred /user:admin program.exe  # 資格情報を保存して実行
```

## 📝 その他の便利コマンド

### `cls` - 画面クリア
```cmd
cls                    # コマンドプロンプトの画面をクリア
```

### `echo` - メッセージ表示・ファイル作成
```cmd
echo Hello World       # メッセージを表示
echo. > newfile.txt    # 空のファイルを作成
echo "Text" >> file.txt # ファイルに文字列を追記
```

### `date` / `time` - 日時の表示・設定
```cmd
date                   # 現在の日付を表示・変更
time                   # 現在の時刻を表示・変更
date /t                # 日付のみ表示（変更プロンプトなし）
time /t                # 時刻のみ表示（変更プロンプトなし）
```

### `whoami` - 現在のユーザー名表示
```cmd
whoami                 # 現在ログイン中のユーザー名を表示
```

## 💡 便利なTips

- **Tab補完**: ファイル名やディレクトリ名の一部を入力して Tab キーを押すと自動補完
- **履歴機能**: ↑↓キーで過去に実行したコマンドを呼び出し
- **ワイルドカード**: `*` (任意の文字列) と `?` (任意の1文字) を使用可能
- **パイプ**: `|` を使って複数のコマンドを連結
- **リダイレクト**: `>` でファイルに出力、`>>` で追記

## 🎯 実践例

### ログファイル分析
```cmd
type server.log | findstr "ERROR" | find /c "404"
# server.log から ERROR を含む行を抽出し、404 エラーの件数をカウント
```

### バックアップ作業
```cmd
xcopy C:\Important D:\Backup\Important /e /i /y
# 重要なフォルダを外部ドライブにバックアップ（サブフォルダ含む）
```

### システム診断
```cmd
systeminfo > sysinfo.txt && ipconfig /all >> sysinfo.txt
# システム情報とネットワーク設定をファイルに出力
```

---

## 🚀 まとめ

これらのコマンドを覚えておけば、Windows でのファイル操作やシステム管理が格段に効率的になります！
最初は基本的なコマンドから始めて、徐々に高度なオプションにチャレンジしてみてください。

Happy Computing! 🎉