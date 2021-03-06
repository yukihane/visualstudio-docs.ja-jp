---
title: ワークフロー デザイナーで Pick アクティビティ デザイナー
ms.date: 11/04/2016
ms.topic: reference
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
f1_keywords:
- System.Activities.Statements.Pick.UI
ms.assetid: 642c0a47-1b47-45de-a19a-ca0606cedd7a
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: f664ac3a22b91780d392e0fef3224cd80b1e7919
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/26/2018
---
# <a name="pick-activity-designer"></a>Pick アクティビティ デザイナー

<xref:System.Activities.Statements.Pick> アクティビティでは、イベント ベースの制御フローを提供します。 このアクティビティは、トリガー起動イベントに応答して、複数の分岐のいずれか 1 つを実行します。

## <a name="the-pick-activity"></a>Pick アクティビティ

<xref:System.Activities.Statements.Pick> アクティビティには、<xref:System.Activities.Statements.PickBranch> オブジェクトのコレクションが含まれており、<xref:System.Activities.Statements.Pick> アクティビティはそのオブジェクトの 1 つを、トリガーの役割を果たす受信イベントに応答して実行できます。 この方法では、Windows ワークフロー デザイナーは、イベント ベースの制御フロー モデリングを提供します。 各 <xref:System.Activities.Statements.PickBranch> には、<xref:System.Activities.Statements.PickBranch.Trigger%2A> および <xref:System.Activities.Statements.PickBranch.Action%2A> が含まれます。 先頭に、<xref:System.Activities.Statements.Pick>アクティビティの実行のすべてのトリガー アクティビティ、<xref:System.Activities.Statements.PickBranch>要素がスケジュールされます。 最初のアクティビティが完了すると、対応するアクション アクティビティがスケジュールされ、他のすべてのトリガー アクティビティは取り消されます。

### <a name="how-to-use-the-pick-activity-designer"></a>Pick アクティビティ デザイナーの使用方法

**Pick**アクティビティ デザイナーは含まれて、**制御フロー**のカテゴリ、**ツールボックス**をクリックしてアクセスする、**ツールボックス**ワークフロー デザイナーのタブ (または、選択**ツールバー**から、**ビュー**メニューまたは CTRL + ALT + X です)。

**Pick**からアクティビティ デザイナーをドラッグすることができます、**ツールボックス**アクティビティ デザイナーを通常配置している内などの場所に、ワークフロー デザイナー画面にドロップし、 **シーケンス**アクティビティ デザイナー。 ワークフロー デザイナーにドロップすた後、作成、<xref:System.Activities.Statements.Pick>を既定では 2 つの空白を含むアクティビティを<xref:System.Activities.Statements.PickBranch>アクティビティを含む要素としては、Branch1 および Branch2 の名前を表示します。 それぞれ<xref:System.Activities.Statements.PickBranch.DisplayName%2A>でプロパティの値を編集できる、 **PickBranch**アクティビティ デザイナーのヘッダー内、または、**プロパティ**各分岐のウィンドウ。

2 つの方法を追加する<xref:System.Activities.Statements.PickBranch>のコレクションにアクティビティ、<xref:System.Activities.Statements.Pick>オブジェクト: ドラッグ アンド ドロップ、 **PickBranch**からデザイナー、**ツールボックス**からコンテキスト メニューを使用内で、 **Pick**デザイン サーフェイスです。 詳細については、次を参照してください。、 [PickBranch](../workflow-designer/pickbranch-activity-designer.md)トピックです。 内に配置できますのみ項目されることに注意してください、 **Pick**アクティビティ デザイナーは、 **PickBranch**アクティビティ デザイナー。

### <a name="pick-activity-properties-in-the-workflow-designer"></a>ワークフロー デザイナーでの Pick アクティビティのプロパティ

次の表に、<xref:System.Activities.Statements.Pick> のプロパティと、デザイナーでのその使用方法を示します。 これらのプロパティは、プロパティ グリッドまたはデザイナー画面で編集できます。

|プロパティ名|必須|使用方法|
|-------------------|--------------|-----------|
|<xref:System.Activities.Activity.DisplayName%2A>|False|ヘッダーの <xref:System.Activities.Statements.Pick> アクティビティ デザイナーの表示名を指定します。 既定値は Pick です。 この値は、プロパティ グリッドで編集することも、アクティビティ デザイナーのヘッダーで直接編集することもできます。<br /><br /> <xref:System.Activities.Activity.DisplayName%2A> は必須ではありませんが、使用することをお勧めします。|

## <a name="see-also"></a>関連項目

- [制御フロー](../workflow-designer/control-flow-activity-designers.md)
- [Pick アクティビティ](/dotnet/framework/windows-workflow-foundation/pick-activity)
- [Pick アクティビティの使用](/dotnet/framework/windows-workflow-foundation/samples/using-the-pick-activity)