# API Management - Hands-on Lab Script - part 5


- [Part 1 - API Managementインスタンスの作成](apimanagement-1.md)
- [Part 2 - 開発者ポータルと製品(Product)の管理](apimanagement-2.md)
- [Part 3 - APIの追加](apimanagement-3.md)
- [Part 4 - キャッシュとポリシー](apimanagement-4.md)
- Part 5 - バージョンとリビジョン
- [Part 6 - 分析と監視](apimanagement-6.md)
- [Part 7 - セキュリティ](apimanagement-7.md)
- [Part 8 - DevOps](apimanagement-8.md)

## Version and Revisions

Versions and revisions provide you with an elegant way to manage change and the lifecycle of your APIs.

[https://azure.microsoft.com/en-us/blog/versions-revisions/](https://azure.microsoft.com/en-us/blog/versions-revisions/)

Revisions allow you to safely make non-breaking changes to your API. Developers who consume the API can be given details about the changes. Revisions also allow you to roll-back changes.

With versions, you can group related APIs and associate them with a version number and scheme (path, query string or header). Versions are typically used when breaking changes are made to an API.

### Revisions

#### Add a new revision

- Select the Star Wars API
- Select `Revisions`
- Add a new revision called `rev2`

![Revisions](Images/APIMRevisionsMenu.png)
![Revisions](Images/APIMRevisionsAdd.png)
![Revisions](Images/APIMRevisionsCreate.png)

#### Add caching

- Select the `GetPeople` operation
- Add a caching policy for 10 seconds at the operation level

#### Test the new revision

- From the Azure portal, test the `GetPeople` operation
- Note the revision number at the top of the page as well as in the request URL.

![Revisions](Images/APIMRevisionsTest.png)

The request URL should look similar to: `https://<your-apim-name>.azure-api.net/sw;rev=2/people/`.

#### Make current revision

- Select the Revisions tab
- Make `rev2` the current revision

![Revisions](Images/APIMRevisionsMakeCurrent.png)

### Version

#### Add a new version

- Select the Star Wars API
- Add a new version
  - Set the name and identifier to `v2`
  - Select the `Path` versioning scheme
  - Add the `Starter` and `Unlimited` products

![Revisions](Images/APIMVersionsAdd.png)
![Revisions](Images/APIMVersionsCreate.png)

#### Test the new version

- Browse to the developer portal
- Select APIs and choose the `v2` version of the Star Wars API
- Notice the request URL and the inclusion of `v2` in the path
- Test the `GetPeople` operation

![Revisions](Images/APIMVersionsDevPortal.png)

---
[Home](README.md) | [Prev](apimanagement-5.md) | [Next](apimanagement-6.md)
