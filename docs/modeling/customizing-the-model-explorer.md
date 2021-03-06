---
title: モデル エクスプローラーのカスタマイズ
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.dsltools.dsldesigner.explorerbehavior
helpviewer_keywords:
- Domain-Specific Language Tools, Domain-Specific Language Explorer
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.technology: vs-ide-modeling
ms.openlocfilehash: 4f136f61976c3980f95977e4f93b5c57789235f6
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/26/2018
---
# <a name="customizing-the-model-explorer"></a>モデル エクスプローラーのカスタマイズ
ことができます、エクスプ ローラーの動作と外観、ドメイン固有言語デザイナー用よう変更。

-   ウィンドウのタイトルを変更します。

-   タブ アイコンを変更します。

-   ノードのアイコンを変更します。

-   ノードを非表示にします。

## <a name="changing-the-window-title"></a>ウィンドウのタイトルを変更します。
 生成されたエクスプ ローラーのウィンドウのタイトルを変更するには、選択**エクスプ ローラー動作**で、 **DSL のエクスプ ローラー**、し、**プロパティ**ウィンドウで、設定、 **タイトル**プロパティを使用タイトル。

## <a name="changing-the-tab-icon"></a>タブ アイコンを変更します。
 エクスプ ローラーのタブのアイコンを変更するには、.bmp ファイルで、16 x 16 ピクセルのアイコンを使用します。 \DslPackage\Resources\ フォルダーで、アイコン ファイルを配置し、ファイルの名前を変更し、 **ModelExplorerToolWindowBitmaps.bmp**です。 たとえば、変更する可能性があります、 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] setup.ico アイコン ファイルに .bmp 形式にして変更**DSLLanguageName\DslPackage\Resources\ModelExplorerToolWindowBitmaps.bmp**です。 生成されたデザイナー アイコンが表示されますこの、エクスプ ローラーのタブでと共にドッキングされている**ソリューション エクスプ ローラー**です。

## <a name="setting-custom-icons-on-explorer-nodes"></a>エクスプ ローラーのノードでカスタム アイコンを設定します。
 エクスプ ローラー ノードの設定を使用して、エクスプ ローラーでノードをカスタマイズできます。 次の手順では、ノードにアイコンを追加する方法を示します。

#### <a name="to-add-an-icon-to-an-explorer-node"></a>エクスプ ローラーのノードにアイコンを追加するには

1.  作成、[!INCLUDE[dsl](../modeling/includes/dsl_md.md)]タスク フロー ソリューション テンプレートを使用してソリューションです。

2.  16 x 16 ピクセルのアイコンを含む .bmp ファイルを配置、 **Dsl\Resources**ソリューションのフォルダーです。

3.  **DSL のエクスプ ローラー**を右クリックして**エクスプ ローラー動作**順にクリック**エクスプ ローラー ノードの新しい設定の追加**です。

     **ExplorerNodeSettings**ノードが表示されます、**カスタム ノード設定**ノード。

4.  選択**ExplorerNodeSettings**、し、**プロパティ**ウィンドウで、設定**クラス**に**アクター**です。

5.  設定**アイコンを表示する**アイコン ファイルのパスにします。

6.  すべてのテンプレートが変換をビルドおよびソリューションを実行します。

7.  生成されたデザイナーでサンプル ダイアグラムを開きます。

     エクスプ ローラーは、3 つを表示する必要があります**アクター**のアイコンを持つノード。

> [!NOTE]
>  生成されたエクスプ ローラーに表示される任意の要素ノードのアイコンを設定すると、エクスプ ローラーのすべてのノードにアイコンが表示されます。 アイコンが設定されていない場合、ノードには既定のアイコンが表示されます。

## <a name="changing-the-name-displayed-on-an-explorer-node"></a>エクスプ ローラーのノードに表示される名前を変更します。
 エクスプ ローラーで、モデル要素の名前を表示する方法を変更することができます。 次の手順の名前を表示する方法を示しています、**タスク**によって参照される、**コメント**コメント ノードにします。

#### <a name="to-display-a-property"></a>プロパティを表示するには

1.  前の手順で作成したソリューションを開きます。

2.  確認して、**コメント**プロパティ名を持つロールの多重度を設定して 1 つのドメイン クラスのみを参照して**サブジェクト**0..1 です。 プロパティ名になります**サブジェクト**、リレーションシップの名前になり、 **CommentReferencesSubject**です。

3.  **DSL のエクスプ ローラー**を右クリックして**エクスプ ローラー動作**順にクリック**エクスプ ローラー ノードの新しい設定の追加**です。

     **ExplorerNodeSettings**ノードが表示されます、**カスタム ノード設定**ノード。

4.  選択**ExplorerNodeSettings**、し、**プロパティ**ウィンドウで、設定**クラス**に**コメント**です。

5.  右クリックし、**コメント**ノードをクリックして**新しいプロパティのパスを追加**です。

     新しいノードには、という名前が表示**プロパティが表示される**です。

6.  選択**プロパティを表示**、し、、**プロパティ**ウィンドウの値フィールドをクリックして**プロパティ パス**です。 選択**コメント**、し**CommentReferencesSubject**、し**FlowElement**です。 結果のパスのようになります**CommentReferencesSubject.Subject/!サブジェクト**です。

7.  値フィールドに**プロパティ****名前**です。

8.  すべてのテンプレートが変換をビルドおよびソリューションを実行します。

9. 生成されたデザイナーでサンプル ダイアグラムを開きます。

10. 描画、**コメント コネクタ**コメント要素の間、 **Task1**図上の要素。

     エクスプ ローラーのノードとコメントを表示する必要があります**Task1**です。

## <a name="hiding-nodes"></a>ノードを非表示にします。
 パスを追加することで、エクスプ ローラーでノードを非表示にできます、**ノードの非表示に**のノード、 **DSL のエクスプ ローラー**です。 次の手順は、非表示にする方法を示しています。**コメント**ノード。

#### <a name="to-hide-an-explorer-node"></a>エクスプ ローラーのノードを非表示にするには

1.  前の手順で作成したソリューションを開きます。

2.  **DSL のエクスプ ローラー**を右クリックして**エクスプ ローラーの動作** をクリックし、**新規ドメイン パスの追加**です。

     A**ドメイン パス**ノードが表示されます**ノードの非表示に**です。

3.  選択**ドメイン パス**、し、**プロパティ**ウィンドウの値フィールドをクリックして**パスの定義**です。 選択**フローグラフ**、し**FlowGraphHasComments**です。 結果のパスのようになります**FlowGraphHasComments.Comments**

4.  すべてのテンプレートが変換をビルドおよびソリューションを実行します。

5.  生成されたデザイナーでサンプル ダイアグラムを開きます。

     のみを表示する必要があります、エクスプ ローラー、**アクター**  ノードを表示しないと、**コメント**ノード。

## <a name="see-also"></a>関連項目

- [ドメイン固有言語ツールの用語集](http://msdn.microsoft.com/ca5e84cb-a315-465c-be24-76aa3df276aa)