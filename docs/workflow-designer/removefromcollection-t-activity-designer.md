---
title: ワークフロー デザイナー - RemoveFromCollection&lt;T&gt;アクティビティ デザイナー
ms.date: 11/04/2016
ms.topic: reference
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
f1_keywords:
- System.Activities.Statements.RemoveFromCollection`1.UI
ms.assetid: 6617ba26-c8bc-4aed-b746-112bf490d288
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: b6aedee945ab19201406ce26183db4e2f3519263
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/26/2018
---
# <a name="removefromcollectiont-activity-designer"></a>RemoveFromCollection\<T > アクティビティ デザイナー

**RemoveFromCollection\<T >** アクティビティ デザイナーを使用して作成し、構成、<xref:System.Activities.Statements.RemoveFromCollection%601>アクティビティ。

## <a name="the-removefromcollectiontactivity"></a>RemoveFromCollection\<T > アクティビティ
 <xref:System.Activities.Statements.RemoveFromCollection%601> アクティビティは、指定した項目を特定のコレクションから削除します。

### <a name="using-the-removefromcollectiont-activity-designer"></a>使用して、RemoveFromCollection\<T > アクティビティ デザイナー
 **RemoveFromCollection\<T >** アクティビティ デザイナーは含まれて、**コレクション**のカテゴリ、**ツールボックス**をクリックしてアクセスするが、**ツールボックス**ワークフロー デザイナーのタブ (または、選択**ツールバー**から、**ビュー**メニューのまたは CTRL + ALT + X です)。

 **RemoveFromCollection\<T >** からアクティビティ デザイナーをドラッグすることができます、**ツールボックス**アクティビティを通常配置しているなど、場所に、ワークフロー デザイナー画面にドロップし、内部、<xref:System.Activities.Statements.Sequence>です。 これを作成、 <xref:System.Activities.Statements.RemoveFromCollection%601> 、既定値を持つアクティビティ<xref:System.Activities.Activity.DisplayName%2A>の RemoveFromCollection < Int32\>です。 <xref:System.Activities.Activity.DisplayName%2A>ヘッダーの値を編集できます、 **RemoveFromCollection < T\>** アクティビティ デザイナーまたは、 **DisplayName**プロパティ グリッドのボックスです。 他のプロパティは、プロパティ グリッドで編集する必要があります。

### <a name="the-removefromcollectiont-properties"></a>RemoveFromCollection < T\>プロパティ
 次の表に、<xref:System.Activities.Statements.RemoveFromCollection%601> のプロパティと、デザイナーでのその使用方法を示します。

|プロパティ名|必須|使用方法|
|-------------------|--------------|-----------|
|<xref:System.Activities.Activity.DisplayName%2A>|False|<xref:System.Activities.Statements.RemoveFromCollection%601> アクティビティの省略可能な表示名。 既定値は、RemoveFromCollection < Int32\>です。<br /><br /> <xref:System.Activities.Activity.DisplayName%2A> は必須ではありませんが、使用することをお勧めします。|
|<xref:System.Activities.Statements.RemoveFromCollection%601.Item%2A>|True|追加する項目、**コレクション\<T >** です。 この項目の型は*T*、種類がある*TypeArgument*です。 項目を指定するには、プロパティ グリッドで Visual Basic の式を入力します。|
|<xref:System.Activities.Statements.RemoveFromCollection%601.Collection%2A>|True|項目の追加先のコレクション。 このコレクションの型は**ICollection < TypeArgument\>です。** コレクションを指定するには、プロパティ グリッドで Visual Basic の式に入力します。|
|*TypeArgument*|True|<xref:System.Collections.Generic.ICollection%601> に格納される項目の T 型。 既定では、この*TypeArgument*に設定されている型**Int32**です。 型を変更するには、値を変更、 *TypeArgument*プロパティ グリッドのコンボ ボックスにします。|
|<xref:System.Activities.Activity%601.Result%2A>|False|指定した項目がコレクションから削除されたかどうかを示す値。 結果にバインドする変数を指定するには、プロパティ グリッドで変数を入力します。|

## <a name="see-also"></a>関連項目

- [コレクション](../workflow-designer/collection-activity-designers.md)
- [AddToCollection\<T>](../workflow-designer/addtocollection-t-activity-designer.md)
- [ClearCollection\<T>](../workflow-designer/clearcollection-t-activity-designer.md)
- [ExistsInCollection\<T>](../workflow-designer/existsincollection-t-activity-designer.md)