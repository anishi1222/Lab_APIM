# API Management - Hands-on Lab Script - part 2

- [Part 1 - API Managementインスタンスの作成](apimanagement-1.md)
- Part 2 - 開発者ポータルと製品(Product)の管理
- [Part 3 - APIの追加](apimanagement-3.md)
- [Part 4 - キャッシュとポリシー](apimanagement-4.md)
- [Part 5 - バージョンとリビジョン](apimanagement-5.md)
- [Part 6 - 分析と監視](apimanagement-6.md)
- [Part 7 - セキュリティ](apimanagement-7.md)
- [Part 8 - DevOps](apimanagement-8.md)

## 開発者ポータル

開発者ポータルは自動生成される、APIのドキュメンテーションを担うフルカスタマイズ可能なWebサイトです。API利用者はこの開発者ポータルを使ってAPIを発見、利用方法を学び、利用リクエストをして、試すことができます。開発者ポータルは {apim-service-name}.developer.azure-api.net から利用できます。

Azure Portalの概要(Overview)ブレードにあるリンクからアクセスすると、開発者ポータルが管理者/編集モードで開き、カスタマイズできるようになります。左側のメニューの Operationsアイコン > Publish Website をクリックすると、ユーザーから開発者ポータルにアクセスできるようになります。

![](Images/APIMDeveloperPortal.png)

### User Experience

ユーザーが開発者ポータルをどのように遷移していくのか体験しましょう。

#### Anoymous User (匿名ユーザー)

認証されていないユーザー（新たなブラウザでURLにアクセスした状態）として開発者ポータルを見ていきましょう。

> Starter と Unlimited という製品の違いに注意してください。

![](Images/APIMDevPortalProducts.png)

APIを確認することもできます。ご覧のように、公開された全てのオペレーションが表示されており、ポータル内から直接テストが可能です。

![](Images/APIMDevPortalAPIs.png)

#### アカウントの登録

アカウント取得のためにサインアップします（Administrator としてログイン済みの場合は一旦ログアウトしてください）。

![](Images/APIMDevSignup.png)

メールの記述に従い、アカウントの有効化確認をしてください。

![](Images/APIMDevSignupEmail.png)

アカウントにサインインします。

![](Images/APIMDevSignin.png)

Starter という製品を選択し、"Starter" サブスクリプションをサブスクライブします。
- メールを確認してください（すでに受け入れ済みの状態です）。

Unlimited という製品を選択し、 "Unlimited" サブスクリプションをサブスクライブします。

- メールを確認してください（承認が必要です）。

![](Images/APIMDevSubscribe.png)

ユーザー・プロファイルで、製品とキーを確認します。

- Unlimited に対するサブスクリプションリクエストはまだ承認されていない（ステータスはsubmitted）ので、Unlimited サブスクリプションはまだ有効ではない点に注意してください。

![](Images/APIMDevSubscribe2.png)

Unlimited サブスクリプションが submitted の状態で承認が必要になったら、Azure Portalでサブスクリプションブレードに移動し、承認してください。

#### APIを試す

ようやく公開されたAPIをテストできるようになりました。APIのエージを開き、Echo APIを見てみましょう。

- 開発者向けの情報に着目してください。
- GETでEcho APIをテストします（CORSエラーが出る可能性があります。これは後で対応します）。

![](Images/APIMDevTryAPI.png)

![](Images/APIMDevTryAPI2.png)

<!-- ![](Images/APIMDevTryAPI3.png) -->

### 開発者ポータルのカスタマイズ

#### サイトの構成

開発者ポータルは[Paperbits](https://paperbits.io/) というフレームワークをフォークしたものにAzure API Management固有の機能を追加しています。フォークしたものは[GitHub](https://github.com/Azure/api-management-developer-portal)にあります。

API Managementインスタンスの外部でご自身の開発者ポータルを自身でホストし、管理することもできるため、ポータルのコードベースを編集し、提供されているコアの機能を拡張することもできます。詳細は [https/github.com/Azure/api-management-developer-portal/wiki](https://github.com/Azure/api-management-developer-portal/wiki) と [https://docs.microsoft.com/en-us/azure/api-management/api-management-howto-developer-portal](https://docs.microsoft.com/en-us/azure/api-management/api-management-howto-developer-portal) に記載があります。

開発者ポータルを外部ユーザーに公開する前に、自動生成されるコンテンツのパーソナライズ、具体的には、レイアウトやスタイル、ホームページのコンテンツなどの変更を推奨します。詳細は [https://docs.microsoft.com/en-us/azure/api-management/api-management-howto-developer-portal-customize](https://docs.microsoft.com/en-us/azure/api-management/api-management-howto-developer-portal-customize) をご覧ください。 

カスタマイズに関する動画は [https://www.youtube.com/watch?v=5mMtUSmfUlw](https://www.youtube.com/watch?v=5mMtUSmfUlw) でご覧いただけます。

![](Images/APIMDevConfig.png)

![](Images/APIDevConfig2.png)

![](Images/APIMDevStyles.png)

#### メールの設定

メール通知のテンプレートの管理はAzure管理ポータルのブレードのサイドメニューから直接実施します。利用可能な通知とカスタマイズ可能な通知テンプレートを確認しましょう。

![](Images/APIMNotifications.png)

![](Images/APIMNotificationTemplates.png)

![](Images/APIMNotificationEdit.png)


### 製品 (Product) の管理

製品には1個以上のAPIが含まれているとともに、利用上限、利用条件が含まれています。製品を公開すると、開発者はその製品をサブスクライブでき、製品に含まれるAPIを利用できるようになります。

#### 製品の定義

再度Azure PortalのAPI Managementに戻り、左側のメニュー `Products` を開きます。

![](Images/APIMProducts.png)

新たな製品を追加します。今回は例としてGold tierとします。ビジビリティを `Published` に変更し、\[Create\] ボタンをクリックします。

![](Images/APIMAddProduct.png)

![](Images/APIMAddProduct2.png)

開発者がアクセスできるようアクセス管理を構成します。

![](Images/APIMAddProductsAccess.png)

保存したら、作成したGold Tierという製品が開発者ポータルに現れていることを確認します。

![](Images/APIMAddProductsDevPortal.png)

---
[Home](README.md) | [Prev](apimanagement-1.md) | [Next](apimanagement-3.md)
