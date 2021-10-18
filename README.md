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
