======================
ソースコード管理の流れ
======================

PG・UT中のソースコード管理の流れを以下に記載します。

.. image:: img/all.png

使用ツール
========

- バージョン管理：Git / GitBucket
- ビルドツール：maven
- ライブラリ管理：Artifactory
- CI：Jenkins
- ソースコードの品質監視：SonarQube

開発フロー
----------------------

1. 開発者は最新のソースコードをGitBucketから取得する。
2. mavenを使用して、プロジェクトが依存するライブラリをArtifactoryから取得し、依存関係を解決する。
3. プログラムを修正し、gitにてバージョン管理(commit)する。
4. 修正したプログラムをGitBucketにpushする。
5. JenkinsはGitBucketから最新のソースコードを取得し、アプリケーションが常に動作する状態か監視する。
6. JenkinsとSonarQubeは連携されており、ソースコードの品質を常に監視する。
7. Jenkinsは、各リポジトリのソースをライブラリ(jar)として **Artifactory** に格納する。

.. note::

   * Jenkinsはテスト・ビルドを実行します。
   * Jenkinsの監視対象はmasterブランチとdevelopブランチです。
   * SonarQubeはソースコードの複雑度の計測やコーディングチェックなどを行い、結果を視覚化します。
   * SonarQubeの監視対象はmasterブランチとdevelopブランチです。
   * Artifactoryはjarをライブラリとして管理することが出来ます。

Gitについて
===========

| Gitの使用方法を以下ドキュメントに記載します。
| コミットコメントやレビュー方法についても記載しているので、目を通してください。
|

* :doc:`Git/index`
