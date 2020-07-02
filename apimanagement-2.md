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

開発者ポータルは {apim-service-name}.developer.azure-api.net から利用できます。

Azure Portalの概要(Overview)にあるリンクからアクセスすると、開発者ポータルが管理者/編集モードで開きます。
Operationsアイコン > Publish Website をクリックすると、ユーザーからアクセスできるようになります。

![](Images/APIMDeveloperPortal.png)

### User Experience

#### Anoymous User (匿名ユーザー)

- 認証されていないユーザーとして開発者ポータルを見ていきましょう。
- Products (製品) の確認
  - Starter と Unlimited という製品の違いに注意してください。
- APIの確認

![](Images/APIMDevPortalProducts.png)

![](Images/APIMDevPortalAPIs.png)

#### アカウントの登録

- Administrator としてログイン済みの場合は一旦ログアウトしてください。
- アカウント取得のためにサインアップします。

![](Images/APIMDevSignup.png)

- メールの記述に従い、アカウントの有効化確認をしてください。

![](Images/APIMDevSignupEmail.png)

- アカウントにサインインします。

![](Images/APIMDevSignin.png)

- Unlimited という製品を選択し、 "Unlimited" サブスクリプションをサブスクライブします。
  - メールを確認してください（承認が必要です）。
- Starter という製品を選択し、"Starter" サブスクリプションをサブスクライブします。
  - メールを確認してください（すでに受け入れ済みの状態です）。

![](Images/APIMDevSubscribe.png)

- ユーザー・プロファイルで、製品とキーを確認します。
  - まだ承認されていないので、Unlimited サブスクリプションはまだ有効ではない点に注意してください。

![](Images/APIMDevSubscribe2.png)

#### APIを試す

- Echo APIを見てみましょう。
  - 開発者情報に注意してください。
  - Echo APIをテストしようとすると、CORSエラーが出る可能性があります。これは後で対応します。

![](Images/APIMDevTryAPI.png)

![](Images/APIMDevTryAPI2.png)

![](Images/APIMDevTryAPI3.png)

### 開発者ポータルのカスタマイズ

#### サイトの構成

開発者ポータルはPaperbits <https://paperbits.io/> というWebフレームワークをフォークしたものにAPI管理固有の機能を追加しています。フォークしたものはGitHubにあります。<https://github.com/Azure/api-management-developer-portal>.

API Managementインスタンスの外部でご自身の開発者ポータルを自身でホストし、管理することもできるため、ポータルのコードベースを編集し、提供されているコアの機能を拡張することもできます。詳細は以下のドキュメントに記載があります。 <https://github.com/Azure/api-management-developer-portal/wiki>/ <https://docs.microsoft.com/en-us/azure/api-management/api-management-howto-developer-portal>.

Before you make your portal available to the visitors, you should personalize the automatically generated content. Recommended changes include the layouts, styles, and the content of the home page. This is documented at <https://docs.microsoft.com/en-us/azure/api-management/api-management-howto-developer-portal-customize>

Video on customisation is at <https://www.youtube.com/watch?v=5mMtUSmfUlw>

![](Images/APIMDevConfig.png)

![](Images/APIDevConfig2.png)

![](Images/APIMDevStyles.png)

#### Email Configuration

The templates for the email notifications are managed from the Azure Management Portal

- Look at notifications
- Look at email templates

![](Images/APIMNotifications.png)

![](Images/APIMNotificationTemplates.png)

![](Images/APIMNotificationEdit.png)


### Product Management

A product contains one or more APIs as well as a usage quota and the terms of use. Once a product is published, developers can subscribe to the product and begin to use the product's APIs.

#### Product definition

- Look at existing products

![](Images/APIMProducts.png)

- Add new product - for example a Gold tier
  - Assign APIs | set Visibility | Create

![](Images/APIMAddProduct.png)

![](Images/APIMAddProduct2.png)

- Set Access Controls to allow developer access

![](Images/APIMAddProductsAccess.png)

- See the new Gold Tier product in the Developer portal

![](Images/APIMAddProductsDevPortal.png)

---
[Home](README.md) | [Prev](apimanagement-1.md) | [Next](apimanagement-3.md)
