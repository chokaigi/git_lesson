# Gitを使ってみよう！
## この章でやること
GitHubを利用して実際にGitを使ってみましょう

## 1.実習環境

#### 図：実習環境
![image](https://raw.githubusercontent.com/chokaigi/git_lesson/master/lesson/images/training_environment.png)

今回は、リモートリポジトリはGitHubのサービス、ローカルリポジトリはMacbookを利用して実習を進めます。
※もちろんGitはWindowsでも使えます！

* 利用PC：MacBookAir（Mac OSX）
* コマンドツール：Macのターミナル（※コマンドラインでGitの使い方を学びます。）

## 1.Gitインストール

Gitのバージョン管理システムを利用するには、Gitをインストールする必要があります。

* Gitダウンロードサイト

http://git-scm.com/


### 図：Gitダウンロードサイト
![image](https://raw.githubusercontent.com/chokaigi/git_lesson/master/lesson/images/git_download.png)


MacOSにははじめからGitがインストールされていますので、今回はインストール手順は省きますが、
Windowsにインストールしたい場合や、Macに最新のGitをインストールしたい場合などは、
ここからダウンロードしてインストールしてください。
（ウィザードを進めていくだけのインストールなので簡単です。）

## 2.GitHubアカウントの作成
今回はリモートリポジトリはGitHubのサービスを利用して用意します。
GitHubサービスを利用するにはアカウント登録が必要となりますので、アカウントを作成します。

1. GitHubサイトにアクセスします
[https://github.com/](https://github.com/)
* 「Sign up for GitHub」ボタンをクリックします
* Username、EmailAddress、Passwordを入力して、「Create an account」ボタンをクリックします

## 3.リモートリポジトリの作成

GitHubにログインした状態で、「New Repository」ボタンを押下します。

#### 図：リモートリポジトリ作成1
![image](https://raw.githubusercontent.com/chokaigi/git_lesson/master/lesson/images/create_remote_repository01.png)


Repository name、Descriptionを入力し、publicを選択します。
その後、「Create repository」ボタンをクリックします。

#### 図：リモートリポジトリ作成2
![image](https://raw.githubusercontent.com/chokaigi/git_lesson/master/lesson/images/create_remote_repository02.png)

作成が完了しました。
赤枠に表示されたURLがリモートリポジトリのURLになります。

#### 図：リモートリポジトリ作成3

![image](https://raw.githubusercontent.com/chokaigi/git_lesson/master/lesson/images/create_remote_repository03.png)

## 4.ローカルリポジトリの作成
ターミナルを開きます。（ターミナルは、Windowsでいうコマンドプロンプトになります。）

```
$ cd /Users/tt/Documents/
$ mkdir myapp
$ cd myapp
$ git init
```

.gitフォルダが作成されていますが、これはgitの設定ファイルが入っているフォルダになります。
このフォルダがあると、gitでバージョン管理されていることがわかります。

## 5.リモートリポジトリ設定

リモートリポジトリの設定を行います。
mydocフォルダにいることを確認し、以下のコマンドで設定します。

```
$ git remote add origin https://github.com/chokaigi/myapp.git
```

## 6.Gitの設定
Gitのバージョン管理では、ファイルの編集者などがわかるように、自分のユーザー設定（名前とemailの設定）が必要です。
ターミナルで以下のコマンドをたたいて設定します。

#### 1. Gitの初期設定を行いましょう

```
$ git config user.name "hiromintt"
$ git config user.email "xxxx@xxxxx"
```

#### 2. メッセージカラーリングをつけよう

```
$ git config --global color.ui true

```
#### 3. 設定を確認してみよう

```
$ git config -l
```

## 7. Gitの設定から、コミットまでやってみよう
#### 1. コミットするファイルを作成
	cd /Users/tt/Documents/myapp
    vim index.html
#### 2. 作成したファイルの状態を確認する
	 git status
#### 3. ファイルをgitの管理に追加する
    git add index.html
#### 3. ファイルが追加されていることを確認する
    git status
#### 4. コミットする
    git commit -m 'initial commit'
#### 5. コミットされたことを確認する
    git log

## 8. git helpでコマンドが引ける
以下のコマンドを打ってみましょう

    git help

利用できるオプション、機能が表示されます。

普段開発で利用する際は大体ここに載っているコマンドですので、
困ったら見てみると良いでしょう

    usage: git [--version] [--help] [-C <path>] [-c name=value]
           [--exec-path[=<path>]] [--html-path] [--man-path] [--info-path]
           [-p|--paginate|--no-pager] [--no-replace-objects] [--bare]
           [--git-dir=<path>] [--work-tree=<path>] [--namespace=<name>]
           <command> [<args>]

    The most commonly used git commands are:
       add        Add file contents to the index
       bisect     Find by binary search the change that introduced a bug
       branch     List, create, or delete branches
       checkout   Checkout a branch or paths to the working tree
       clone      Clone a repository into a new directory
       commit     Record changes to the repository
       diff       Show changes between commits, commit and working tree, etc
       fetch      Download objects and refs from another repository
       grep       Print lines matching a pattern
       init       Create an empty Git repository or reinitialize an existing one
       log        Show commit logs
       merge      Join two or more development histories together
       mv         Move or rename a file, a directory, or a symlink
       pull       Fetch from and integrate with another repository or a local branch
       push       Update remote refs along with associated objects
       rebase     Forward-port local commits to the updated upstream head
       reset      Reset current HEAD to the specified state
       rm         Remove files from the working tree and from the index
       show       Show various types of objects
       status     Show the working tree status
       tag        Create, list, delete or verify a tag object signed with GPG

    'git help -a' and 'git help -g' list available subcommands and some
    concept guides. See 'git help <command>' or 'git help <concept>'
    to read about a specific subcommand or concept.

もっと細かくHELP一覧がみたい！という方は以下のコマンドを叩いてみましょう

    git help config

vimで開くので、qキーで閉じましょう

それぞれの機能の詳細が知りたい！という方は、以下のコマンドを実行してみましょう

（add　の部分は詳細を知りたいコマンドに変更してみてください）

    git help -w add


## 演習問題

1. ローカルにgitリポジトリを新たに作成するコマンドは何ですか。
* gitの設定をリストで表示させるコマンドは何ですか。
* gitのヘルプを見るコマンドは何ですか。
* myappフォルダのローカルリポジトリのindex.htmlフィアルを再編集し、変更をコミットしてください。（コミット時のコメントは何でもOK）
