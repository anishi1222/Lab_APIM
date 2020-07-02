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

Azure Portalの概要(Overview)にあるリンクからアクセスすると、開発者ポータルが管理者/編集モードで表示されます。
Using the Operations Icon - select `Publish Website`.  It will then be available for users to access.

![](Images/APIMDeveloperPortal.png)

### User Experience

#### Anoymous User

- As an unauthenticated user, look around the developer portal
- Check the Products
  - Notice the difference between the Starter & Unlimited products
- Check the APIs

![](Images/APIMDevPortalProducts.png)

![](Images/APIMDevPortalAPIs.png)

#### Register for an account

- If logged in as Administrator - log out
- Sign up for an account

![](Images/APIMDevSignup.png)

- Check acceptance email and confirm to activate account

![](Images/APIMDevSignupEmail.png)

- Sign into account

![](Images/APIMDevSignin.png)

- Select Unlimited Product - Subscribe to a "Unlimited" subscription
  - Check email - needs approval
- Select Starter Product - Subscribe to a "Starter" subscription
  - Check email - accepted

![](Images/APIMDevSubscribe.png)

- Check user profile - see products and keys
  - Note that the Unlimited subscription is not yet Active as this request has not yet been approved

![](Images/APIMDevSubscribe2.png)

#### Try an API

- Look at the Echo API
  - Notice the developer information
  - Test the Echo API ... there may be a CORS error - we will address that later.

![](Images/APIMDevTryAPI.png)

![](Images/APIMDevTryAPI2.png)

![](Images/APIMDevTryAPI3.png)

### Customising the Developer Portal

#### Site Configuration

The developer portal is based on a fork of the Paperbits web framework <https://paperbits.io/>, and is enriched with API Management-specific features.  The fork resides at <https://github.com/Azure/api-management-developer-portal>.

It is possible to self-host, and manage your own developer portal outside of an API Management instance. It's an advanced option, which allows you to edit the portal's codebase and extend the provided core functionality. This is documented at <https://github.com/Azure/api-management-developer-portal/wiki>/ and <https://docs.microsoft.com/en-us/azure/api-management/api-management-howto-developer-portal>.

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
