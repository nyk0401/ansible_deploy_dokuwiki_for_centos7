# Deploy DokuWiki for CentOS7

## インストール対象

- CentOS7 (vagrant box centos/7)
    - SSHでのアクセスが可能なこと
    - sudo権限を利用可能なユーザがいること

## 実行環境

- ansible 2.3.1.0


## 使い方

### 1. このプロジェクトをダウンロードする

git clone またはzip等でダウンロードする。

### 2. インストール対象のIPアドレスをhostsファイルに書き込む


```
[dokuwiki-server]
192.168.33.30   # <= ここを書き換える
```

### 3. DokuWikiのダウンロードリンクを調べる

1. [Dokuwiki'のダウンロードページ](https://download.dokuwiki.org/)にアクセスする。

2. 「Download」ボタンをクリックする。

3. "download via this link"の部分のリンクを右クリック等でコピーする。

4. dokuwiki-ansible.yml の 「dokuwiki_download_url」のURLを書き換える。

### 4. インストール対象のディレクトリを設定する

-  dokuwiki-ansible.yml の 「dokuwiki_install_dir」を変更する。デフォルトはwiki  
  
http://192.168.33.30/wiki でアクセスできるようになります。

### 5. sudoを利用できるユーザを指定する

- dokuwiki-ansible.yml の 「remote_user」を変更する。デフォルトはvagrant


### 6. bash exec.sh でAnsible-playbookを実行する

```bash exec.sh``` でAnsible-playbookが実行されます。  

実行直後にSSHのパスワードとsudo実行時のパスワードを要求されるので入力してください。  


## 実行後の確認

http://192.168.33.30/wiki/install.php にアクセスして
DokuWikiの初期設定画面が表示されれば完了です。



