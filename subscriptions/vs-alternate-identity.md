---
title: Visual Studio サブスクライバー向けの ID
author: evanwindom
ms.author: jaunger
manager: evelynp
ms.date: 04/10/2018
ms.topic: conceptual
description: VSTS と Azure で使用するために Visual Studio サブスクリプションに代替 ID を追加する方法
ms.prod: vs-subscription
ms.technology: vs-subscriptions
searchscope: vs subscription
ms.openlocfilehash: 9a83f78f35b9533c554c81cecd181c00eca05568
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/16/2018
---
# <a name="identities-for-visual-studio-subscribers"></a>Visual Studio サブスクライバー向けの ID

Visual Studio サブスクリプションをアクティブ化すると、アクティベーション中に使用した ID (またはログイン) が Visual Studio サブスクリプションとリンクされます。 これにより、Microsoft は [Visual Studio サブスクライバー ポータル](https://my.visualstudio.com?wt.mc_id=o~msft~docs)、Visual Studio Team Services (VSTS)、Azure でユーザーを認識できます。

VSTS では、ユーザーがログインするたびに Visual Studio サブスクリプションの状態を確認し、メンバーである各アカウント内に自動的に機能を付与します。
これらの機能はサブスクライバーの特典として含まれるため、Visual Studio サブスクリプションにリンクされている ID を使用しているときに、任意の VSTS アカウントのメンバーとして無料で追加されます。

Azure では、サブスクライバーの特典である[月単位の Azure クレジット](https://azure.microsoft.com/pricing/member-offers/credit-for-visual-studio-subscribers/)をアクティブ化すると、Visual Studio サブスクリプションの状態が確認されます。

[Visual Studio サブスクライバー ポータル](https://my.visualstudio.com?wt.mc_id=o~msft~docs)内で、アクティベーション中に使用した ID に加えて、**代替 ID** を追加できる可能性があります。 現在、サブスクリプションをアクティブ化するために Microsoft アカウントを使用した場合、代替 ID を追加することを許可しています。 この方法で、個人用アカウントと職場または学校アカウントの両方を使用して VSTS にアクセスすることを許可し、(Visual Studio、Office 365、または会社または学校のネットワークにログインするときに使用する) 職場または学校アカウントを追加することもできます。

## <a name="add-an-alternate-account-to-your-visual-studio-subscription"></a>Visual Studio サブスクリプションに代替 ID を追加する

Visual Studio サブスクリプションに代替アカウントを追加すると、サブスクリプションが割り当てられている別の ID を利用し、Visual Studio Team Services (VSTS) や Azure など、サブスクリプションの特典にアクセスできます。 以前は、この機能は、Visual Studio (VS) サブスクリプションが Microsoft Account (MSA) に割り当てられた場合にのみ利用できました。 Azure Active Directory (Azure AD) でこの機能が職場や学校のアカウントにも使えるようになりました。

サブスクリプションのコピーが他のアカウントに与えられるわけではなく、代替アカウントを利用して 2 つの特典にアクセスする機能のみが与えられます。

すべてのサブスクリプションで、"職場または学校のアカウント" を追加できます。ログインを必要とする特典 (VS IDE、VSTS、Azure) でそのアカウントを使用できます。

### <a name="prerequisites"></a>必須コンポーネント

* [VSTS プロジェクト コレクションの管理者またはアカウント所有者のアクセス許可](https://docs.microsoft.com/en-us/vsts/accounts/faq-add-delete-users#find-owner)。

* 代替アカウントを使用するには、自分のアカウントに関連付けられているサブスクリプションに Visual Studio Team Services または Microsoft Azure が含まれている必要があります。

> [!Note]
> 代替 ID でサブスクリプション特典の使用を継続できますが、サブスクリプションは元のアカウントに関連付けられています。

### <a name="add-the-alternate-account"></a>代替アカウントを追加する

1. 自分の Microsoft アカウントで Visual Studio にサインインします (https://{あなたのアカウント}.visualstudio.com)。

2. **サブスクリプション**に移動します。

  ![代替アカウントの追加 - VS でサブスクリプションに移動する](_img/vs-alternate-identity/my-vs-subscriptions.png)

3. **[代替アカウントを追加する]** を選択します。

  ![代替アカウントの追加を選択する ](_img/vs-alternate-identity/choose-add-alternate-account.png)

4. 職場または学校アカウントを追加します。

  ![職場または学校のアカウントを追加する](_img/vs-alternate-identity/enter-alternate-account-my-visual-studio-com-portal.png)

5. 職場または学校のアカウントを使用し、Visual Studio にサインインします (https://{あなたのアカウント}.visualstudio.com)。

  ![職場または学校アカウントを使用する](_img/vs-alternate-identity/sign-in-with-alternate-account.png)

  代替アカウントが Visual Studio に追加されました。代替アカウントでのサインインを要求するサブスクリプション特典 (IDE、VSTS、Azure) を両方の ID で活用できます。

代替アカウントの追加については、[My Visual Studio のよく寄せられる質問](https://www.visualstudio.com/my/myvsfaq#alternate)ページを参照してください。

## <a name="faq"></a>FAQ

### <a name="q--why-doesnt-vsts-recognize-me-as-a-visual-studio-subscriber"></a>Q: VSTS で Visual Studio サブスクライバーとして認識されないのはなぜですか?
A: プライマリ ID または代替 ID を使用してサインインすると、VSTS で自動的にサブスクリプションが認識されます。 認識されない場合は、次のいくつかのことを試すことができます。

* [特典として VSTS を含む](vs-vsts.md)アクティブな Visual Studio サブスクリプションがあることを確認します。

* Visual Studio サブスクリプション用のプライマリ ID または代替 ID のいずれかであるログインまたは ID を使用していることを確認します。

* VSTS にサインインする前に、少なくとも 1 回は [Visual Studio サブスクライバー ポータル](https://my.visualstudio.com?wt.mc_id=o~msft~docs)にアクセスします。

引き続き VSTS でサブスクリプションが認識されない場合は、[サポートにお問い合わせください](https://www.visualstudio.com/team-services/support/)。
