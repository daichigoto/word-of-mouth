## PowerShell Selenium

|コマンドレット(URL系)|内容|
|:---|:---|
|Set-SeUrl -Url URL|Webページを開く|
|Set-SeUrl -Url https://ユーザ:パスワード@ドメイン/パス|Webページを開く(ベーシック認証あり)|

|コマンドレット(要素取得系)|内容|
|:---|:---|
|$Element = Get-SeElement -By XPath -Value xpath|要素の取得(xpath)|
|$Element = Get-SeElement -By Id -Value id|要素の取得(id)|
|$Element = Get-SeElement -By Name -Value name|要素の取得(name)|

|コマンドレット(操作系)|内容|
|:---|:---|
|Invoke-SeClick -Element $Element -Action Click|クリック|
|Invoke-SeKeys -Element $Element -Keys 文字列|文字列の入力|
|Set-SeSelectValue -Element $Element -Value 値|selectの選択|
|SeShouldHave -Alert -PassThru \| Clear-SeAlert -Action Accept|確認ダイアログでOKをクリック|

|コマンドレット(待機系)|内容|
|:---|:---|
|Wait-SeElement -By XPath -Value xpath -Condition ElementToBeClickable -Timeout 秒|待機(クリック可能になるまで)|

|コマンドレット(JavaScriptコード実行)|内容|
|:---|:---|
|Invoke-SeJavascript -Script 'JavaScriptコード'|JavaScriptを実行|

||コマンドレット(ファイルの選択)|内容|
|:---|:---|:---|
|1.|$Element = Get-SeElement -By XPath -Value xpath|要素の取得(xpath)|
|2.|Invoke-SeKeys -Element $Element -Keys $env:HOME|ファイル選択ダイアログを表示|
|3.|add-type -AssemblyName System.Windows.Forms|.NETのSystem.Windows.Formsを使うために読み込み|
|4.|[System.Windows.Forms.SendKeys]::SendWait($env:HOME+"ファイルパス`n")|ファイルパスの入力と選択|

## pacman

|コマンド|内容|
|:---|:---|
|pacman -S|パッケージインストール|
|pacman -Ss|パッケージ検索|
|pacman -R|パッケージアンインストール|
|pacman -Rdd|パッケージ強制アンインストール|
|pacman -Rs|パッケージおよびそのパッケージのみが必要としているパッケージをアンインストール|
|pacman -Rns|パッケージおよびそのパッケージのみが必要としているパッケージおよびバックアップファイルをアンインストール|
|pacman -Fx|指定したファイルが含まれているパッケージを一覧表示|
|pacman -Fl|指定したパッケージがインストールするファイルを一覧表示|
|pacman -Q|インストール済みパッケージ一覧表示|
|pacman -Syu|メタデータアップデートとパッケージアップグレード|

## brew

|コマンド|内容|
|:---|:---|
|brew list -v 対象|インストールされたファイルを一覧表示|
|brew update && brew upgrade|メタデータアップデートとパッケージアップグレード|

## samba4

|コマンド|内容|
|:---|:---|
|pdbedit -a ユーザ|既存ユーザをSambaユーザとして登録。登録時にパスワードを設定|
|pdbedit -x ユーザ|登録したユーザをSambaから削除|
|pdbedit -L|登録されているSambaユーザを一覧表示|
|testparm|設定ファイルの内容を確認|
|testparm -v|設定ファイルの内容を確認（全設定情報を出力）|

###### smb4.conf サンプル

    [global]
            dos charset = CP932
    
    [名前1]
            path = パス1
            writable = yes
    
    [名前2]
            path = パス2
            writable = yes
