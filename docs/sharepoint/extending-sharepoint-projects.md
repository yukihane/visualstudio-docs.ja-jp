---
title: SharePoint プロジェクトの拡張 |Microsoft ドキュメント
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- projects [SharePoint development in Visual Studio], extending
- SharePoint development in Visual Studio, extending projects
- SharePoint projects, extending
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 622596249e92d73dd4f504a445d43405847e9629
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/16/2018
---
# <a name="extending-sharepoint-projects"></a>SharePoint プロジェクトの拡張
  SharePoint プロジェクトのプロジェクト レベルの機能をカスタマイズする場合は、プロジェクトの拡張機能を作成します。 たとえば、カスタム プロジェクトのプロパティ を追加したり、ユーザーは、Visual Studio で SharePoint ソリューションを開発するときに発生するプロジェクト レベルのイベントに応答することができます。  
  
## <a name="creating-project-extensions"></a>プロジェクトの拡張機能の作成  
 プロジェクト項目を拡張するアセンブリをビルドする Visual Studio 拡張機能を実装する、<xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectExtension>インターフェイスです。 詳細については、次を参照してください。[する方法: SharePoint プロジェクトの拡張機能を作成する](../sharepoint/how-to-create-a-sharepoint-project-extension.md)です。  
  
 プロジェクトの拡張機能を作成するときに、SharePoint プロジェクトに、次の機能を追加することもできます。  
  
-   ショートカット メニュー項目を追加します。 SharePoint プロジェクト ノードのショートカット メニューを開くと、メニュー項目が表示される**ソリューション エクスプ ローラー**ノードを右クリックしてまたは選択するか、shift キーを押しながら F10 を選択し、キーします。 詳細については、次を参照してください。[する方法: SharePoint プロジェクトへのショートカット メニュー項目の追加](../sharepoint/how-to-add-a-shortcut-menu-item-to-sharepoint-projects.md)です。  
  
-   カスタム プロパティを追加します。 このプロパティを表示、**プロパティ**で SharePoint プロジェクトを選択するときにウィンドウ**ソリューション エクスプ ローラー**です。 詳細については、次を参照してください。[する方法: SharePoint プロジェクトにプロパティを追加](../sharepoint/how-to-add-a-property-to-sharepoint-projects.md)です。  
  
 作成、配置、およびプロジェクトの拡張機能をテストする方法について説明するチュートリアルでは、次を参照してください。[チュートリアル: SharePoint プロジェクトの拡張機能を作成する](../sharepoint/walkthrough-creating-a-sharepoint-project-extension.md)です。  
  
## <a name="understanding-the-relationship-between-project-extensions-and-project-instances"></a>プロジェクトの拡張機能とプロジェクトのインスタンス間の関係を理解します。  
 任意の種類の SharePoint プロジェクトを開いたときに、拡張機能を読み込みますプロジェクトの拡張機能を作成するときに[!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]です。 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] リスト定義、コンテンツの種類、およびイベント レシーバーなど、いくつかの SharePoint プロジェクト テンプレートが含まれます。 ただし、これには 1 つだけの SharePoint プロジェクトの種類があります。 表示されるプロジェクトの種類、**新しいプロジェクト** ダイアログ ボックスは、1 つまたは複数の SharePoint プロジェクト項目をすべてまとめますテンプレートのみです。 SharePoint プロジェクトの種類を 1 つだけなので、1 つのプロジェクト用に作成された拡張機能は、すべての SharePoint プロジェクトに適用されます。 たとえば、のみに適用される拡張機能を作成することはできません、**コンテンツ タイプ**プロジェクト。  
  
 インスタンスにアクセスする、特定のプロジェクトのいずれかの処理、<xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectEvents>のイベント、 *projectService*の実装でのパラメーター、<xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectExtension.Initialize%2A>メソッドです。 たとえば、調べるには、SharePoint プロジェクトをソリューションに追加するときに、処理、<xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectEvents.ProjectAdded>イベント。 詳細については、次を参照してください。[する方法: SharePoint プロジェクトの拡張機能を作成する](../sharepoint/how-to-create-a-sharepoint-project-extension.md)です。  
  
## <a name="see-also"></a>関連項目  
 [方法: SharePoint プロジェクトの拡張機能を作成します。](../sharepoint/how-to-create-a-sharepoint-project-extension.md)   
 [方法: SharePoint プロジェクトへのショートカット メニュー項目の追加](../sharepoint/how-to-add-a-shortcut-menu-item-to-sharepoint-projects.md)   
 [方法: SharePoint プロジェクトにプロパティを追加](../sharepoint/how-to-add-a-property-to-sharepoint-projects.md)   
 [チュートリアル: SharePoint プロジェクトの拡張機能の作成](../sharepoint/walkthrough-creating-a-sharepoint-project-extension.md)   
 [カスタム SharePoint プロジェクト項目の種類を定義します。](../sharepoint/defining-custom-sharepoint-project-item-types.md)   
 [SharePoint プロジェクト項目の拡張](../sharepoint/extending-sharepoint-project-items.md)   
 [SharePoint の拡張のパッケージ化と配置](../sharepoint/extending-sharepoint-packaging-and-deployment.md)   
 [SharePoint プロジェクト システムの拡張](../sharepoint/extending-the-sharepoint-project-system.md)  
  
  