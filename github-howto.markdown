githubの使い方
==============


githubへの登録
--------------

githubは無料でアカウントを登録することができます。
ユーザー会コンテンツの編集などは、すべて無料のアカウントのみで行うことができます。

アカウントの登録は、[githubのアカウント種別ページ](http://github.com/plans)で「Free!」欄のSign Up!をクリックし、フォームに適宜情報を入力するのみです。


### アイコンの登録

githubのアカウントアイコンは、GRAVATARという外部サービスを利用しています。
ご自分のアイコン画像を登録したい場合は、[Gravatar](http://ja.gravatar.com/)のサイトにもアカウントを登録し、お好きな画像を登録してください。

> **CAUTION**
> githubに登録したメールアドレスとGravatarに登録したメールアドレスが一致していないと、正しくアイコン画像が表示されないことに注意して下さい。



既存リポジトリのFork
--------------------

既存のリポジトリをForkするには、単にForkしたいリポジトリにWebブラウザでアクセスし、「Fork」ボタンをクリックするだけです。

![Forkボタン](images/github/fork.png)


しばらくすると、自分のダッシュボードにForkされたリポジトリが追加されます。



リポジトリのコンテンツの編集（簡易）
------------------------------------

リポジトリのコンテンツは、githubのWebサイトで、Webブラウザから直接編集することができます。手順は以下のとおりです。

1. githubの自分のリポジトリで編集したいコンテンツのページを表示する。
2. コンテンツの右上にあるeditボタンをクリックする。
   ![editボタン](images/github/edit.png)
3. 適宜内容を編集する。
4. 編集が完了したら、編集内容の説明を「Commit Message」欄に入力し、Commitボタンをクリックする。

これだけで、コンテンツを編集できます。



リポジトリのコンテンツの編集（上級者向け）
------------------------------------------

多くのドキュメントを編集する場合などは、ウェブブラウザでは作業効率が落ちてしまいます。
ご自分のローカル環境にgithubへのアクセスをセットアップすれば、お気に入りのテキストエディタなどでコンテンツの編集を行えます。

これには以下のような作業が必要になり、説明が高度になるため、ここでは参考となるブログへのリンクのみ紹介します。

### 必要な作業

- gitのインストール
- ssh鍵の作成、登録


### 参考リンク

- [はじめてのgithub - blog.katsuma.tv](http://blog.katsuma.tv/2009/02/first_github.html)
- [CygwinでGit(GitHub)を始めるための準備・設定メモ - Rewish](http://rewish.org/tools/cygwin_github)
- [github を使うためのメモ。 - WOMO](http://womo.nconc.net/2010/03/04/github)



編集したコンテンツを元のリポジトリに反映する（Pull Request）
------------------------------------------------------------

Forkした自分のリポジトリでコンテンツの編集が完了したら、変更を元のリポジトリに反映（マージ）してもらうために、元のリポジトリの管理者へPull Requestを送信します。

Pull Requestを送信するには、単に自分のリポジトリにWebブラウザでアクセスし、右上にある「Pull Request」ボタンを押すだけです。

![Pull Requestボタン](images/github/pullrequest.png)

> **NOTE**
> Commitメッセージと同様に、Pull Request送信時に変更箇所の概要などをメッセージ欄に記入してください。



Pull Requestを受け取った場合のマージの仕方
------------------------------------------

自分のリポジトリに対して他の人が修正などを行いPull Requestを受信した場合、以下の手順でマージします。

1. 修正した人のリポジトリを自分の作業リポジトリのリモートに追加する。
2. 修正した人のブランチに切り替え、pullする。
3. 自分の元のブランチに戻り、マージする。

コマンドは、例えば以下のようになります。

<pre class="command-line">
# リモートに追加
git remote add -f hidenorigoto git://github.com/hidenorigoto/sfjp-doc-main.git

# ブランチの切り替え
git checkout -b hidenorigoto/master

# 最新をpull
git pull hidenorigoto master

# 元のブランチに戻る
git checkout master

# マージする
git merge hidenorigoto/master
</pre>



参考リンク（その他）
--------------------

gitを使う上での参考となるページなどを紹介します。

- [Pro Git](http://progit.org/book/ja/)<br />
  すべてオンラインでフリーで読めるGitの解説書。内容も新しくgitを使う上では必読。
- [知らないと損をするgit - Absolute Playing!](http://d.hatena.ne.jp/Kiske/20081003/1223008270)

