---
title: '方法: プログラムによってワークシート内の行をグループ化 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- worksheets, creating groups
- groups, creating in worksheets
- ranges, creating groups
- worksheets, clearing groups
- groups
- groups [Office development in Visual Studio], clearing in worksheets
- worksheets, ungrouping rows and columns
- rows [Office development in Visual Studio], ungrouping
- columns [Office development in Visual Studio], ungrouping
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 894e3971c257a6461aa975a9d6bb1cf933234440
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-programmatically-group-rows-in-a-worksheet"></a>方法: プログラムによってワークシート内の行をグループ化する
  1 つ以上の行をグループ化することができます。 ワークシート内でグループを作成するには、<xref:Microsoft.Office.Tools.Excel.NamedRange>コントロールまたはネイティブな Excel 範囲オブジェクト。  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
## <a name="using-a-namedrange-control"></a>NamedRange コントロールを使用します。  
 追加する場合、<xref:Microsoft.Office.Tools.Excel.NamedRange>コントロール、デザイン時にドキュメント レベルのプロジェクトをプログラムでグループを作成するコントロールを使用することができます。 次の例では 3 つ<xref:Microsoft.Office.Tools.Excel.NamedRange>同じワークシートにコントロール: `data2001`、 `data2002`、および`dataAll`です。 各名前付き範囲は、ワークシートの行全体を指します。  
  
#### <a name="to-create-a-group-of-namedrange-controls-on-a-worksheet"></a>ワークシートに NamedRange コントロールのグループを作成するには  
  
1.  呼び出して次の 3 つの名前付き範囲にグループ化、<xref:Microsoft.Office.Tools.Excel.NamedRange.Group%2A>各範囲のメソッドです。 このコードは、 `ThisWorkbook` クラスではなく、シート クラスに配置する必要があります。  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#32](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#32)]
     [!code-vb[Trin_VstcoreExcelAutomation#32](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#32)]  
  
    > [!NOTE]  
    >  行を解除するを呼び出して、<xref:Microsoft.Office.Tools.Excel.NamedRange.Ungroup%2A>メソッドです。  
  
## <a name="using-native-excel-ranges"></a>ネイティブ Excel の範囲を使用します。  
 コードでは、という 3 つの Excel 範囲であると想定`data2001`、 `data2002`、および`dataAll`ワークシートにします。  
  
#### <a name="to-create-a-group-of-excel-ranges-in-a-worksheet"></a>ワークシート内で Excel の範囲のグループを作成するには  
  
1.  呼び出して次の 3 つの名前付き範囲にグループ化、<xref:Microsoft.Office.Interop.Excel.Range.Group%2A>各範囲のメソッドです。 次の例では 3 つ<xref:Microsoft.Office.Interop.Excel.Range>という名前のコントロール`data2001`、 `data2002`、および`dataAll`同じワークシートにします。 各名前付き範囲は、ワークシートの行全体を指します。  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#33](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#33)]
     [!code-vb[Trin_VstcoreExcelAutomation#33](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#33)]  
  
    > [!NOTE]  
    >  行を解除するを呼び出して、<xref:Microsoft.Office.Interop.Excel.Range.Ungroup%2A>メソッドです。  
  
## <a name="see-also"></a>関連項目  
 [ワークシートの操作](../vsto/working-with-worksheets.md)   
 [NamedRange コントロール](../vsto/namedrange-control.md)   
 [方法: ワークシートに NamedRange コントロールを追加します。](../vsto/how-to-add-namedrange-controls-to-worksheets.md)   
 [Office ソリューションの省略可能なパラメーター](../vsto/optional-parameters-in-office-solutions.md)  
  
  