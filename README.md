# github-handson

GitHubになれるため、初めてファイルをプッシュしました。  
Git Bashをインストールし、ハンズオンの手順に従って、Gitの操作をしました。  

### Gitのインストール確認
次のコマンドを実行してgitのバージョン情報が表示されました。
```
$ git --version
```

### Gitの初期設定
GitHubに登録したユーザー名とメールアドレスの設定を下記のように実行しました。
```
$ git config --global user.name "GitHubのユーザー名"
$ git config --global user.email GitHubに登録しているメールアドレス
```

### GitHub 個人アクセストークンの作成
今回はclassicではなく**Fine-grained personal access tokens**を作成しました。

### GitHubにてリポジトリを作成
リポジトリ名: github-handson　

### プロジェクトの配置場所を作成
ターミナルを開いて、プロジェクトを配置するディレクトリ（フォルダー）を作成しました。 
``` 
$ cd c:/  
$ mkdir projects  
$ cd projects  
$ pwd
```
ディレクトリをc/projectsとしました。

### プロジェクトの作成
Gitで管理するプロジェクトを作成します。  
projectsディレクトリ配下であることを確認します。  
```
$ pwd
```
  
次に、github-handsonディレクトリを作成して移動します。  
```
$ mkdir github-handson  
$ cd github-handson  
$ pwd
```

### ファイルの作成
ファイルを作成します。
```
$ echo "# github-handson" >> README.md  
$ ls
```
README.mdが表示されたことを確認しました。  
  
```
$ cat README.md
```
**# github-handson**と表示されることを確認する。

### リポジトリの初期化
```
$ git init
```
**Initialized empty Git repository**というようなメッセージが表示されることを確認する。  
  
ブランチ名をmasterからmainに変更します。  
```
$ git branch -M main  
$ git status
```
> On branch main
と表示されました。  

```
$ ls -a
```
**.git**というディレクトリが作成されました。

### ステージング（add）
まずは以下のgitコマンドを実行して表示内容の確認をします。
``` 
$ git status
```
  
赤字で示された変更内容をステージング（add）します。
```
$ git add .  
$ git status
```
Changes to be committed以下はこれからコミットする変更の一覧を緑色で表しています。  

### コミット（commit）
変更内容をコミットします。
```
$ git commit -m "README.mdを追加"
```
念の為コミットができているか確認をします。
``` 
$ git log
``` 
「README.mdを追加」という文言が表示されていることを確認しました。  
作成したリポジトリにプッシュします。  
```
$ git remote add origin https://github.com/silvernyanko/github-handson.git
``` 

### プッシュ（push）
GitHubのmainブランチにpushします。
```
$ git push origin main -u
``` 
GitHub のユーザー名とパスワードを聞かれるので入力します。  
ユーザー名はアカウント開設したときの名称で、リポジトリ URL に含まれています。  
パスワードは、GitHub 個人アクセストークン（PAT）を入力します。  
また、パスワードは入力しても表示されませんが、入力されています。  
これは盗み見に対するセキュリティ対策です。  
