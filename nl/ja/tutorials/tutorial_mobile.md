---

copyright:
  years: 2016, 2017
lastupdated: "2017-05-18"

---
{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}

# モバイル・ベーシック・スターターのエンドツーエンド・チュートリアル
{: #tutorial}

以下のエンドツーエンド・チュートリアルでは、モバイル・ベーシック・スターターからプロジェクトを作成するための手順を段階的に説明します。このガイドには、前提条件ツールのインストールと、Xcode および Android Studio でのプロジェクトの実行手順が含まれます。


## 開発者ツールのインストール
{: #dev_tools}

[前提条件の開発者ツール![外部リンク・アイコン](../icons/launch-glyph.svg "外部リンク・アイコン")](get_code.html#prereq-dev-tools "外部リンク・アイコン"){: new_window} を必ずインストールしてください。


## プロジェクトの作成方法の選択
{: #choose_how}

Web ベースの [{{site.data.keyword.dev_console}}](#create-devex) を使用するか、またはコマンド駆動型 [{{site.data.keyword.dev_cli_notm}}](#create-cli) を使用して、プロジェクトを作成することができます。


## {{site.data.keyword.dev_console}} を使用したプロジェクトの作成
{: #create-devex}

1. {{site.data.keyword.Bluemix}} で {{site.data.keyword.dev_console}} プロジェクトを作成します。

   1. {{site.data.keyword.dev_console}} 内の [**「開始」** ![外部リンク・アイコン](../icons/launch-glyph.svg "外部リンク・アイコン")](https://console.ng.bluemix.net/developer/getting-started/ "外部リンク・アイコン") ページから**「プロジェクトの作成」**をクリックします。

      代替方法として、**「プロジェクト」**ページから**「プロジェクトの作成」**をクリックすることもできます。

   2. **「モバイル・アプリ (Mobile App)」**を選択し、**「次へ」**をクリックします。

   3. **「ベーシック (Basic)」**を選択し、**「次へ」**をクリックします。

   4. プロジェクト名を入力します。このチュートリアルでは、`MobileBasicProject` を使用します。

   5. プラットフォームを選択します。このチュートリアルでは、`Swift` を使用します。
   
   6. **「作成」**をクリックします。

2. オプション: Authentication (認証) 機能を追加します。

   1. **「プロジェクト概要 (Project Overview)」** ページで、**「Authentication (認証)」**に対して**「追加」**をクリックします。

      代替方法として、**「機能 (Capabilities)」>「Authentication (認証)」**ページで**「作成」**または**「既存の追加 (Add Existing)」**を選択することもできます。

   2. サービス名を入力し、**「作成」**をクリックします。
   
   3. **「Authentication (認証)」**をオンに切り替えます。
   
   4. ID プロバイダーを選択し、それを構成するための情報を入力します。ID プロバイダーは 1 つだけ有効にすることができます。
   
   5. Authentication の構成方法について詳しくは、『[ID プロバイダーの構成![外部リンク・アイコン](../icons/launch-glyph.svg "外部リンク・アイコン")](/docs/services/appid/identity-providers.html "外部リンク・アイコン"){: new_window}』 を参照してください。
   
3. オプション: Analytics (分析) 機能を追加します。

   1. **「プロジェクト概要 (Project Overview)」** ページで、**「Analytics (分析)」**に対して**「追加」**をクリックします。

      代替方法として、**「機能 (Capabilities)」>「Analytics (分析)」**ページから**「作成」**または**「既存の追加 (Add Existing)」**をクリックすることもできます。

   2. サービス名を入力し、**「作成」**をクリックします。
   
   3. アプリを実行した後、**「デモ・モード」**をオフに切り替えて、分析データを確認できます。
   
   4. Analytics の構成方法について詳しくは、 『[{{site.data.keyword.mobileanalytics_short}} の概説 ![外部リンク・アイコン](../icons/launch-glyph.svg "外部リンク・アイコン")](/docs/services/mobileanalytics/index.html "外部リンク・アイコン"){: new_window}』を参照してください。

4. オプション: {{site.data.keyword.mobilepushshort}} 機能を追加します。

   1. **「プロジェクト概要 (Project Overview)」**ページで**「{{site.data.keyword.mobilepushshort}}」**に対して**「追加」**をクリックします。

      代替方法として、**「機能 (Capabilities)」>「{{site.data.keyword.mobilepushshort}}」**ページから**「作成」**または**「既存の追加 (Add Existing)」**をクリックすることもできます。

   2. サービス名を入力し、**「作成」**をクリックします。

   3. iOS の場合、[Apple プッシュ通知サービスを構成します ![外部リンク・アイコン](../icons/launch-glyph.svg "外部リンク・アイコン")](/docs/services/mobilepush/t_push_provider_ios.html "外部リンク・アイコン"){: new_window}。

   4. Android の場合、[Firebase Cloud Messaging を構成します ![外部リンク・アイコン](../icons/launch-glyph.svg "外部リンク・アイコン")](/docs/services/mobilepush/t_push_provider_android.html "外部リンク・アイコン"){: new_window}。

5. オプション: Data (データ) 機能を追加します。

   1. **「プロジェクト概要 (Project Overview)」**ページで、**「Data (データ)」**に対して**「表示」**をクリックします。

      代替方法として、**「データ (Data)」**ページで**「作成」**を選択することもできます。
      
   2. **「{{site.data.keyword.cloudant_short_notm}}」**または**「{{site.data.keyword.objectstorageshort}}」**を選択します。

   3. サービス名を入力し、**「作成」**をクリックします。

   4. {{site.data.keyword.cloudant_short_notm}} の構成方法について詳しくは、『[Getting started with {{site.data.keyword.cloudant_short_notm}} ![外部リンク・アイコン](../icons/launch-glyph.svg "外部リンク・アイコン")](/docs/services/Cloudant/index.html "外部リンク・アイコン"){: new_window}』を参照してください。

   5. {{site.data.keyword.objectstorageshort}} の構成方法について詳しくは、 『[{{site.data.keyword.objectstorageshort}} 概説 ![外部リンク・アイコン](../icons/launch-glyph.svg "外部リンク・アイコン")](/docs/services/ObjectStorage/index.html "外部リンク・アイコン"){: new_window}』を参照してください。

6. プロジェクト・コードを生成します。

   1. **「プロジェクト概要 (Project Overview)」**ページで**「コードの取得 (Get the Code)」**をクリックして、言語を選択します。
   
      代替方法として、**「コード」**ページで以下をクリックすることもできます。
      
   2. **「Swift の生成 (Generate Swift)」**をクリックします。
   
   3. プロジェクト・コードの生成が完了したら、**「Swift のダウンロード (Download Swift)」**をクリックして、プロジェクトのアーカイブをダウンロードします。

7. ダウンロードされたプロジェクトの処理を開始します。

	1. アーカイブされたファイルを解凍します。
	
	2. 新規プロジェクト・ディレクトリーにナビゲートします。
	
	3. {{site.data.keyword.dev_cli_notm}} を使用して処理を続行します。

8. オプション: 新しい言語を生成するために[プロジェクトを更新します](project_overview_page.html#update_language)。


## {{site.data.keyword.dev_cli_notm}} を使用したプロジェクトの作成
{: #create-cli}

1. [{{site.data.keyword.dev_cli_short}}](dev_cli.html) を必ずインストールしてください。

2. 端末のプロンプトで、使用するローカル・ディレクトリーにナビゲートし、以下のコマンドを実行します。

	```
	bx dev create
	```
	{: codeblock}
	
3. プロンプトが出されたら、以下の値を入力します。

	* パターンの選択: 2 (モバイル)
	* スターターの選択: 1 (ベーシック)
	* プラットフォームの選択: 3 (iOS Swift)
	* プロジェクト名の入力: `MobileBasicProjectCLI`

4. プロジェクトにサービスを追加する場合は、該当の質問のプロンプトで `y` を入力し、残りの質問に答えます。

5. `MobileBasicProjectCLI` が正常に保存されたら、`MobileBasicProjectCLI/MobileBasicProjectCLI-Swift` フォルダーにナビゲートします。


## Xcode での Swift プロジェクトの実行
{: #run_swift}

1. `MobileBasicProject-Swift.zip` ファイルを解凍します。

2. Markdown ビューアーで `README.md` ファイルを開き、プロジェクトを構成する手順を確認します。

   1. ターミナルを開き、プロジェクト・フォルダーに移動します。
   
      1. CocoaPods リポジトリーをセットアップする必要がある場合は、`pod setup` を実行します。
      
      2. 既存の Pods を更新する必要がある場合は、`pod update` を実行します。
      
      3. プロジェクト用の Pods をインストールするには、`pod install` を実行します。
      
   3. `BasicProject.xcworkspace` Xcode ワークスペースを開きます。
      
3. アプリを実行します。


## Xcode での Cordova プロジェクトの実行
{: #run_cordova_xcode}

1. `MobileBasicProject-Cordova.zip` ファイルを解凍します。

2. Markdown ビューアーで `README.md` ファイルを開き、プロジェクトを構成します。

   1. Xcode で `platforms/ios` プロジェクトを開きます。
      
3. アプリを実行します。


## Android Studio での Cordova プロジェクトの実行
{: #run_cordova_studio}

1. `BasicProject-Cordova.zip` ファイルを解凍します。

2. Markdown ビューアーで `README.md` ファイルを開き、プロジェクトを構成します。

   1. Android Studio で `platforms/android` プロジェクトを開きます。
      
3. アプリを実行します。


## Android Studio での Android プロジェクトの実行
{: #run_android}

1. `MobileBasicProject-Android.zip` ファイルを解凍します。

2. Markdown ビューアーで `README.md` ファイルを開き、プロジェクトを構成します。

   1. Android Studio で `BasicProject-Android` プロジェクトを開きます。
      
3. アプリを実行します。
