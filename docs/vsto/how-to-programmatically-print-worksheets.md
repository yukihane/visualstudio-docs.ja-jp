---
title: '方法: プログラムによってワークシートを印刷 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- printing [Office development in Visual Studio], worksheets
- worksheets, printing
- print preview, worksheets
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 9d9bd4d28afb1eca2ff07a8847081864c7af5744
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-programmatically-print-worksheets"></a>方法: プログラムによってワークシートを印刷する
  ブック内のワークシートはすべて印刷できます。  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
## <a name="printing-a-worksheet-in-a-document-level-customization"></a>ドキュメント レベルのカスタマイズでのワークシートの印刷  
  
#### <a name="to-print-a-worksheet"></a>ワークシートを印刷するには  
  
1.  `Sheet1` の <xref:Microsoft.Office.Tools.Excel.Worksheet.PrintOut%2A> メソッドを呼び出します。印刷部数は 2 部で、印刷前に文書をプレビューします。  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#22](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#22)]
     [!code-vb[Trin_VstcoreExcelAutomation#22](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#22)]  
  
 <xref:Microsoft.Office.Tools.Excel.Worksheet.PrintPreview%2A>メソッドでは、指定されたオブジェクトを表示することができます、**印刷プレビュー**ウィンドウです。 次のコードでは、`Sheet1` という名前の <xref:Microsoft.Office.Tools.Excel.Worksheet> ホスト項目があることを前提としています。  
  
#### <a name="to-preview-a-page-before-printing"></a>印刷する前にページをプレビューするには  
  
1.  ワークシートの <xref:Microsoft.Office.Tools.Excel.Worksheet.PrintPreview%2A> メソッドを呼び出します。  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#23](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#23)]
     [!code-vb[Trin_VstcoreExcelAutomation#23](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#23)]  
  
## <a name="printing-a-worksheet-in-a-vsto-add-in"></a>VSTO アドインでのワークシートの印刷  
  
#### <a name="to-print-a-worksheet"></a>ワークシートを印刷するには  
  
1.  作業中のワークシートの <xref:Microsoft.Office.Interop.Excel._Worksheet.PrintOut%2A> メソッドを呼び出します。印刷部数は 2 部で、印刷前に文書をプレビューします。  
  
     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#14](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#14)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#14](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#14)]  
  
 <xref:Microsoft.Office.Interop.Excel._Worksheet.PrintPreview%2A>メソッドでは、指定されたオブジェクトを表示することができます、**印刷プレビュー**ウィンドウです。  
  
#### <a name="to-preview-a-page-before-printing"></a>印刷する前にページをプレビューするには  
  
1.  作業中のワークシートの <xref:Microsoft.Office.Interop.Excel._Worksheet.PrintPreview%2A> メソッドを呼び出します。  
  
     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#15](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#15)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#15](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#15)]  
  
## <a name="see-also"></a>関連項目  
 [ワークシートの操作](../vsto/working-with-worksheets.md)   
 [方法: プログラムによってワークシートでスペル チェック](../vsto/how-to-programmatically-check-spelling-in-worksheets.md)   
 [Worksheet ホスト項目](../vsto/worksheet-host-item.md)   
 [Office プロジェクト内のオブジェクトへのグローバル アクセス](../vsto/global-access-to-objects-in-office-projects.md)   
 [Office ソリューションの省略可能なパラメーター](../vsto/optional-parameters-in-office-solutions.md)  
  
  