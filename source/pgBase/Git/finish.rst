:orphan:

========================
レビュー合格のときにやること(レビュアーが実施)
========================

.. contents::
    :depth: 3

作業概要
====

レビューし、内容に問題がなければ、featureブランチをdevelopブランチへマージしましょう。  
developブランチへマージすると、他の開発者に対して変更内容を展開することが出来ます。

featureブランチはdevelopブランチへのマージ後は不要になるので、削除しましょう。  
残しておくと、どれが既にマージ済みのfeatureブランチなのかわからなくなり、ソースコードの取り込み漏れが発生する可能性があります。

.. image:: ./img/finish.png

事前準備
====

- レビュー指摘に全て対応されていること

作業内容
====

1. gitBucketの画面を開きます。
2. Merge pull requestボタンを押します。

.. image:: ./img/gitBucket_finish.png

3. Confirmマージボタンを押します。これがイメージ図の**Merge**です。

.. image:: ./img/gitBucket_merge.png

4. Delete branchボタンを押して、不要になったブランチを削除しましょう。

.. note::

    ブランチを削除しても、コミットの記録およびpull requestは"Close"のステータスで残ります。

.. image:: ./img/gitBucket_deleteBranch.png

事後確認
====

* developブランチに変更が反映されています。
* featureブランチが削除されています。
