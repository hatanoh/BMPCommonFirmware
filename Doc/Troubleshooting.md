## Troubleshooting
### tap/holdのキーが期待通りに動かない
標準状態ではTAPPING_TERMが設定されていませんので正しく動きません。
TAPTERM.JSNファイルもコピーして下さい(TAPPINGTERM 200 の物が用意されています。必要に応じて変更して下さい)

### ファームウェアをアップデートしたらキー入力がおかしくなった
キーの内部コードが変更された可能性があります。
再度KEYMAP.JSN / TAPTERM.JSN をコピーして下さい。

またβ版のうちはキーコードの機能が変更/キーコードの名前が変更される場合があります。
ファームウェアのアップデート前には必ず設定ファイルの保存をして下さい。
