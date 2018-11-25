# HW開発環境設定
本プロジェクトでは、WindowsとLinuxのどちらでも開発できるようにします。

## 必要なソフトウェアのインストール
### Icarus Verilog
* Windows  
Icarus Verilogの[ホームページ](http://bleyer.org/icarus/ "Icarus Verilog")から、[setup.exe](http://bleyer.org/icarus/iverilog-10.1.1-x64_setup.exe "iverilog-10.1.1-x64_setup.exe")をダウンロード＆インストールする  
インストール先ディレクトリには半角空白を入れないこと  
(デフォルトの`C:\iverilog`を推奨)  
環境変数で、`C:\iverilog\bin`と`C:\iverilog\gtkwave\bin`にパスを通すこと

* Linux ( Ubuntu )  
aptからインストール  
    $ sudo apt-get install verilog gtkwave  

### Visual Studio Code
* Windows  
Visual Studio Codeの[ホームページ](https://code.visualstudio.com/ "VS Code")から、setup.exeをダウンロード＆インストールする  

* Linux ( Ubuntu )  
Visual Sdutio Codeの[SETUP-Linux](https://code.visualstudio.com/docs/setup/linux "SETUP-Linux")に従って、インストールする  
The repository and key can also be installed manually with the following script:  
`curl https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > microsoft.gpg  `  
`sudo install -o root -g root -m 644 microsoft.gpg /etc/apt/trusted.gpg.d/`  
`sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/vscode stable main" > /etc/apt/sources.list.d/vscode.list'  `  
Then update the package cache and install the package using:  
`sudo apt-get install apt-transport-https`  
`sudo apt-get update`  
`sudo apt-get install code`  

### GNU Make (Windowsのみ)
Windowsには、makeが含まれていないため、GNU Makeを別途インストールします。  
本家[Make for Windows](http://gnuwin32.sourceforge.net/packages/make.htm "Make for Windows")の
[Complete package, except sources](http://gnuwin32.sourceforge.net/downlinks/make.php "")を使用してもパスが通らなようです。 
環境変数で、`C:\Program Files (x86)\GnuWin32\bin`にパスを通してください。


---
## 開発環境の設定
Visual Studio Codeを開発環境とするための拡張機能をインストールします。
* *必須*  
**Verilog HDL**  (mshr-h.veriloghdl)  
Verilog HDLのシンタックスハイライト/リントを行います。
* *推奨*  
**Japanese Language Pack for Visual Studio Code**  
日本語環境  
Ver.1.25から英語だけが本体同梱のようです。  
**psioniq File Header**  (psioniq.psi-header)  
ファイルヘッダの生成/更新を自動で行います。  
プロジェクトで統一したファイルヘッダを使用できます。  
**Emacs Keymap** (hiro-san.vscode-emacs)  
必須に入れてもいい拡張機能！

### psioniq FIle Headerの設定  
User Settingに、`author`と`authoremail`を設定しておく  

    {
        "psi-header.variables": [
            ["author","AAM"],
            ["authoremail","aam.you@gmail.com"]
        ]
    }

## 

### Git/GitHubの設定 ###
* 公開鍵/秘密鍵の作成  
`$ cd ~/.ssh`  
`$ ssh-keygen -t rsa`  
id_rsa(秘密鍵)とid_rsa.pub(公開鍵)が作成されます  
id_ras.pubの内容をGitHubに登録します。  
[GitHubホームページ](https://github.com/settings/ssh "GitHub")で公開鍵の設定ができます。  
画面右上の「New SSH Key」のボタンを押します
「Title」に公開鍵名「key」に公開鍵の中身を入れます
`$ ssh -T git@github.com`
で接続が確認できます。