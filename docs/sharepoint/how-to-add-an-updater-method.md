---
title: '方法: Updater メソッドを追加 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords:
- BDC [SharePoint development in Visual Studio], updating data
- BDC [SharePoint development in Visual Studio], Updater
- Business Data Connectivity service [SharePoint development in Visual Studio], updating data
- Business Data Connectivity service [SharePoint development in Visual Studio], Updater
- Business Data Connectivity service [SharePoint development in Visual Studio], updating entity instances
- BDC [SharePoint development in Visual Studio], updating entity instances
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: fc7c946a89c8ba05ffed443816d6ce4e9056b88b
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-add-an-updater-method"></a>方法: Updater メソッドを追加する
  作成することで、SharePoint の外部リストのビジネス データを更新するユーザーを有効にすることができます、 *Updater*メソッドです。 詳細については、次を参照してください。[ビジネス データ接続モデルをデザイン](../sharepoint/designing-a-business-data-connectivity-model.md)です。  
  
### <a name="to-create-an-updater-method"></a>Updater メソッドを作成するには  
  
1.  BDC デザイナーでは、エンティティを選択します。  
  
2.  メニュー バーで、次のように選択します。**ビュー**、**その他のウィンドウ**、 **BDC メソッドの詳細**です。  
  
     [BDC メソッドの詳細] ウィンドウを開きます。 このウィンドウの詳細については、次を参照してください。 [BDC モデルのデザイン ツールの概要](../sharepoint/bdc-model-design-tools-overview.md)です。  
  
3.  **メソッドを追加**一覧で、選択**Updater メソッドの作成**です。  
  
     Visual Studio では、モデルに、次の要素を追加します。 これらの要素は、BDC メソッドの詳細 ウィンドウに表示されます。  
  
    -   という名前のメソッド**更新**です。  
  
    -   メソッドの入力パラメーター。  
  
    -   パラメーターの型記述子。 既定では、Visual Studio は、定義したエンティティ型記述子 Finder メソッド (例: 連絡先)。  
  
    -   メソッドのメソッドのインスタンス。  
  
     詳細については、次を参照してください。[ビジネス データ接続モデルをデザイン](../sharepoint/designing-a-business-data-connectivity-model.md)です。  
  
    > [!NOTE]  
    >  エンティティ型の識別子は、自動的に生成されるデータベース テーブル内のフィールドを表している場合は、設定、**前 Updater フィールド**プロパティを**True**です。  
  
4.  **ソリューション エクスプ ローラー**エンティティには、生成されたサービス コード ファイルのショートカット メニューを開きを選択し、**コードの表示**です。  
  
     エンティティ サービス コード ファイルでは、コード エディターで開きます。 そのファイルに関する詳細については、次を参照してください。[ビジネス データ接続モデルを作成する](../sharepoint/creating-a-business-data-connectivity-model.md)です。  
  
5.  データを更新する Update メソッドにコードを追加します。 次の例では、SQL Server については、AdventureWorks サンプル データベース内の連絡先の情報を更新します。  
  
    > [!NOTE]  
    >  値を置き換える、`ServerName`フィールドに、サーバーの名前。  
  
     [!code-csharp[SP_BDC#5](../sharepoint/codesnippet/CSharp/SP_BDC/bdcmodel1/contactservice.cs#5)]
     [!code-vb[SP_BDC#5](../sharepoint/codesnippet/VisualBasic/sp_bdc/bdcmodel1/contactservice.vb#5)]  
  
## <a name="see-also"></a>関連項目  
 [ビジネス データ接続モデルの設計](../sharepoint/designing-a-business-data-connectivity-model.md)   
 [方法: Finder メソッドを追加](../sharepoint/how-to-add-a-finder-method.md)   
 [方法: Specificfinder メソッドを追加します。](../sharepoint/how-to-add-a-specific-finder-method.md)   
 [方法: Creator メソッドを追加](../sharepoint/how-to-add-a-creator-method.md)   
 [方法: Updater メソッドを追加](../sharepoint/how-to-add-an-updater-method.md)   
 [方法: Deleter メソッドを追加](../sharepoint/how-to-add-a-deleter-method.md)   
 [BDC モデルのデザイン ツールの概要](../sharepoint/bdc-model-design-tools-overview.md)   
 [方法: メソッドにパラメーターを追加](../sharepoint/how-to-add-a-parameter-to-a-method.md)   
 [方法: メソッド インスタンスを定義する](../sharepoint/how-to-define-a-method-instance.md)  
  
  