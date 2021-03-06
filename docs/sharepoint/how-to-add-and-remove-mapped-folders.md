---
title: '方法: 追加およびマップされたフォルダーを削除する |Microsoft ドキュメント'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
f1_keywords:
- VS.SharePointTools.Project.MappedFolder
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, mapped folders
- mapped folders [SharePoint development in Visual Studio]
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 43ec8b7c18d99880b1ab932ea28a371a7604b636
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-add-and-remove-mapped-folders"></a>方法: マップされたフォルダーを追加および削除する
  SharePoint では、フォルダーは、イメージとレイアウト、深くに埋め込まれたファイル階層のなど、いくつかよく使用されます。 これらのフォルダーは、これらをより簡単にアクセスする SharePoint プロジェクトにマップできます。 マップされたフォルダーは、SharePoint サーバーのインストール内のファイルの物理的な場所に対応する SharePoint プロジェクトのフォルダーです。  
  
 SharePoint アプリケーションを展開するときに、マップされたフォルダーとそのサブフォルダーは、サーバー上にソリューション パッケージ (.wsp) によりコピーされるすべての内容を実行している SharePoint SharePoint フォルダー ツリー内の指定された位置。 この場所がによって決定されます、**配置場所**マップされたフォルダーに設定されているプロパティ。 マップされたフォルダー内のすべてのサブフォルダーの基準になる**配置場所**のマップされたフォルダーです。 なお、**配置場所**プロパティ、マップされたフォルダーの名前ではなくでは、アイテムの配置場所を決定します。  
  
 プロジェクトにマップされたフォルダーを追加するには、プロジェクトのメニュー バーまたはショートカット メニューにコマンドを使用します。 使用することができます、**追加 SharePoint「イメージ」のマップされたフォルダー**と**追加 SharePoint「レイアウト」フォルダー**を追加するためのコマンドが最もよく使用されるフォルダーをマップします。 マップできます、他の使用可能な SharePoint フォルダーのいずれかのプロジェクトを使用して、 **SharePoint のマップされたフォルダーの追加**ショートカット メニューの [コマンドおよび内のフォルダーを指定して、 **SharePoint マップされたフォルダーの追加** ] ダイアログ ボックス。  
  
## <a name="adding-mapped-folders-to-a-project"></a>マップされたフォルダーをプロジェクトに追加します。  
 次の手順では、次の 2 つのマップされたフォルダーを視覚的 web パーツ プロジェクトに追加する方法について説明します。 開始するには、視覚的 web パーツ プロジェクトを作成します。  
  
#### <a name="to-add-mapped-folders-to-a-project"></a>プロジェクトにマップされたフォルダーを追加するには  
  
1.  メニュー バーで、 **[ファイル]**、 **[新規作成]**、 **[プロジェクト]**の順にクリックします。  
  
2.  **新しいプロジェクト** ダイアログ ボックスで、いずれかを展開、 **Visual Basic**または**Visual c#**  ノードを展開、 **Office/sharepoint**ノード、し、選択、 **SharePoint ソリューション**ノード。  
  
3.  プロジェクト テンプレートの一覧で選択、 **SharePoint 2013 視覚的 Web パーツ**テンプレート。  
  
4.  **名前**ボックスに、入力**TestProject1**を選択し、 **OK**ボタンをクリックします。  
  
5.  **SharePoint カスタマイズ ウィザード**、選択、**完了**既定の設定を保持するボタンをクリックします。  
  
6.  **ソリューション エクスプ ローラー**、プロジェクト ノードを選択し、次に、メニュー バーで、次のように選択します。**プロジェクト**、**追加 SharePoint"イメージ"のマップされたフォルダー**です。  
  
     という名前のフォルダー**イメージ**プロジェクトに表示され、TestProject1 という名前のサブフォルダーが含まれています。 このマップされたフォルダーは、視覚的 web パーツ プロジェクト用のイメージが格納されます。  
  
7.  **ソリューション エクスプ ローラー**、プロジェクト ノードを選択し、次に、メニュー バーで、次のように選択します**プロジェクト**、 **SharePoint のマップされたフォルダーの追加**を表示する、**追加。SharePoint のマップされたフォルダー**  ダイアログ ボックス。  
  
8.  マップできるは、フォルダーのツリー ビューで選択、**リソース**フォルダーを選択し、 **[ok]**ボタンをクリックします。  
  
     という名前のフォルダー**リソース**プロジェクトに表示されます。 このフォルダーは、文字列リソース ファイルなどの項目を格納できます。 サブフォルダーは、マップされたフォルダーの内容を整理するため便利ですを使用して、マップされたフォルダーを追加するときに自動的に作成される、 **SharePoint のマップされたフォルダーの追加**コマンド。 サブ フォルダーを追加する、**リソース**フォルダーで、次に、メニュー バーで、次のように選択します。**プロジェクト**、**新しいフォルダー**です。  
  
## <a name="changing-the-deployment-location-of-a-mapped-folder"></a>マップされたフォルダーの配置場所を変更します。  
 既定では、マップされたフォルダーは、SharePoint ルート インストール パスの相対、{sharepointroot} トークンが表す特定の場所に追加されます。 ただし、変更することによってこの場所を変更することができます、**配置場所**マップされたフォルダーのプロパティです。 各マップされたフォルダーには、独自**配置場所**プロパティです。  
  
#### <a name="to-change-the-deployment-location-of-a-mapped-folder"></a>マップされたフォルダーの配置場所を変更するには  
  
1.  先ほど作成したプロジェクトでは、マップされたフォルダーを選択します。  
  
2.  **プロパティ**ウィンドウで、選択、省略記号 (![ASP.NET モバイル デザイナー楕円](../sharepoint/media/mwellipsis.gif "ASP.NET モバイル デザイナー楕円")) のボタンでは、**展開場所**プロパティです。  
  
3.  **SharePoint のマップされたフォルダーの追加** ダイアログ ボックスで、マップされたフォルダーをポイントするフォルダーを参照します。  
  
4.  ノードを選択し、、 **OK**ボタンをクリックします。  
  
## <a name="renaming-or-removing-mapped-folders"></a>マップされたフォルダーの名前変更または削除  
  
#### <a name="to-rename-or-remove-a-mapped-folder"></a>名前を変更したり、マップされたフォルダーを削除します。  
  
1.  先ほど作成したプロジェクトでは、マップされたフォルダーを選択します。  
  
2.  マップされたフォルダーの名前を変更する、ショートカット メニューを開き、選択**の名前を変更**新しい名前を入力、および Enter キーを押します。  
  
     代わりに、マップされたフォルダーを開き、名前を変更することができます、**プロパティ** ウィンドウの値を設定し、**フォルダー名**プロパティを新しい名前にします。  
  
3.  をプロジェクトからマップされたフォルダーを削除する、ショートカット メニューを開き、選択**削除**、を選択し、 **OK**削除の確認 ダイアログ ボックスでボタンをクリックします。  
  
## <a name="see-also"></a>関連項目  
 [SharePoint ソリューションの開発](../sharepoint/developing-sharepoint-solutions.md)  
  
  