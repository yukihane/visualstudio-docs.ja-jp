---
title: '方法: プログラムによって文書内のテキストを非表示に |Microsoft ドキュメント'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- documents [Office development in Visual Studio], hiding text
- text [Office development in Visual Studio], hiding in documents
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: b8e2ea2f5f8af3876fe64d90d5f2d77874ebb252
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-programmatically-hide-text-in-documents"></a>方法: プログラムによって文書内のテキストを非表示にする
  特定範囲のテキストに対応する <xref:Microsoft.Office.Interop.Word._Font.Hidden%2A> の <xref:Microsoft.Office.Interop.Word.Range.Font%2A> プロパティを設定して、文書内のテキストを非表示にできます。  
  
 たとえば、文書をプリンターに送信する前に、 <xref:Microsoft.Office.Tools.Word.Bookmark> (ドキュメント レベルのカスタマイズ) または <xref:Microsoft.Office.Interop.Word.Bookmark> (VSTO アドイン) 内のテキストを一時的に非表示にできます。  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
### <a name="to-hide-text-in-a-bookmark-control-while-printing-the-document"></a>文書の印刷時に Bookmark コントロール内のテキストを非表示にするには  
  
1.  指定した範囲内にあるテキストをすべて非表示にするプロシージャを作成します。  
  
     [!code-vb[Trin_VstcoreWordAutomation#105](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#105)]
     [!code-csharp[Trin_VstcoreWordAutomation#105](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#105)]  
  
2.  指定した範囲内にあるテキストをすべて再表示するプロシージャを作成します。  
  
     [!code-vb[Trin_VstcoreWordAutomation#106](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#106)]
     [!code-csharp[Trin_VstcoreWordAutomation#106](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#106)]  
  
3.  `HideText` メソッドにブックマークの範囲を渡し、文書を印刷して、 `UnhideText` メソッドに同じ範囲を渡します。  
  
     次のコード例はドキュメント レベルのカスタマイズで使用できます。 このコード例を使用するには、プロジェクトの `ThisDocument` クラスから実行します。  
  
     [!code-vb[Trin_VstcoreWordAutomation#107](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#107)]
     [!code-csharp[Trin_VstcoreWordAutomation#107](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#107)]  
  
     次のコード例は VSTO アドインで使用できます。 この例ではアクティブ ドキュメントを使用します。 この例を使用するには、プロジェクトの `ThisAddIn` クラスから実行します。  
  
     [!code-vb[Trin_VstcoreWordAutomationAddIn#107](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#107)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#107](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#107)]  
  
## <a name="compiling-the-code"></a>コードのコンパイル  
 このコード例では、 <xref:Microsoft.Office.Tools.Word.Bookmark> という名前の <xref:Microsoft.Office.Interop.Word.Bookmark> コントロール (ドキュメント レベルのカスタマイズの場合) または `bookmark1`コントロール (VSTO アドインの場合) が文書に含まれていることを前提にしています。  
  
## <a name="see-also"></a>関連項目  
 [方法: プログラムによって文書を印刷します。](../vsto/how-to-programmatically-print-documents.md)   
 [方法: プログラムによってを定義し、ドキュメントで範囲を選択](../vsto/how-to-programmatically-define-and-select-ranges-in-documents.md)   
 [方法: プログラムによってリセット Word 文書の範囲](../vsto/how-to-programmatically-reset-ranges-in-word-documents.md)   
 [方法: プログラムによってブックマークのテキストを更新](../vsto/how-to-programmatically-update-bookmark-text.md)   
 [Office ソリューションの省略可能なパラメーター](../vsto/optional-parameters-in-office-solutions.md)  
  
  