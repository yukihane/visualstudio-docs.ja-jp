---
title: '方法: ワークシートに NamedRange コントロールを追加します。'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- ranges, adding to worksheets
- NamedRange control, adding to worksheets
- controls [Office development in Visual Studio], adding to worksheets
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 88f427dd22b7395141ce4ffe0c970cdf9c07ff71
ms.sourcegitcommit: 209c2c068ff0975994ed892b62aa9b834a7f6077
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2018
---
# <a name="how-to-add-namedrange-controls-to-worksheets"></a>方法: ワークシートに NamedRange コントロールを追加します。
  追加することができます<xref:Microsoft.Office.Tools.Excel.NamedRange>デザイン時およびドキュメント レベルのプロジェクトでの実行時に、Microsoft Office Excel ワークシートにコントロールできます。  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
 追加することも<xref:Microsoft.Office.Tools.Excel.NamedRange>VSTO アドイン プロジェクトでは実行時にコントロールできます。  
  
 このトピックでは、次のタスクについて説明します。  
  
-   [デザイン時に NamedRange コントロールを追加します。](#designtime)  
  
-   [ドキュメント レベルのプロジェクトの実行時に NamedRange コントロールを追加します。](#runtimedoclevel)  
  
-   [VSTO アドイン プロジェクトでの実行時に NamedRange コントロールを追加します。](#runtimeaddin)  
  
 詳細については<xref:Microsoft.Office.Tools.Excel.NamedRange>コントロールを参照してください[NamedRange コントロール](../vsto/namedrange-control.md)です。  
  
##  <a name="designtime"></a> デザイン時に NamedRange コントロールを追加します。  
 デザイン時にドキュメント レベルのプロジェクトのワークシートに <xref:Microsoft.Office.Tools.Excel.NamedRange> コントロールを追加する方法として、Excel から行う方法、Visual Studio の **ツールボックス**から行う方法、 **[データ ソース]** ウィンドウから行う方法があります。  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
### <a name="to-add-a-namedrange-control-to-a-worksheet-using-the-name-box-in-excel"></a>Excel で [名前ボックス] を使用してワークシートに NamedRange コントロールを追加するには  
  
1.  名前付き範囲に含める 1 つ以上のセルを選びます。  
  
2.  **名 ボックス**、キーを押して、範囲の名前を入力**Enter**です。  
  
     **[名前ボックス]** は、数式バーの横、ワークシートの列 **A** の真上にあります。  
  
### <a name="to-add-a-namedrange-control-to-a-worksheet-using-the-toolbox"></a>ツールボックスを使用してワークシートに NamedRange コントロールを追加するには  
  
1.  **ツールボックス** を開き、 **[Excel コントロール]** タブをクリックします。  
  
2.  <xref:Microsoft.Office.Tools.Excel.NamedRange> をクリックし、ワークシートにドラッグします。  
  
     **[NamedRange コントロールの追加]** ダイアログ ボックスが表示されます。  
  
3.  名前付き範囲に含める 1 つ以上のセルを選びます。  
  
4.  **[OK]** をクリックします。  
  
     コントロールに既定の名前を付けない場合は、 **[プロパティ]** ウィンドウで名前を変更します。  
  
### <a name="to-add-a-namedrange-control-to-a-worksheet-using-the-data-sources-window"></a>[データ ソース] ウィンドウを使用してワークシートに NamedRange コントロールを追加するには  
  
1.  **[データ ソース]** ウィンドウを開いて、プロジェクトのデータ ソースを作成します。 詳細については、次を参照してください。[新しい接続を追加](../data-tools/add-new-connections.md)です。  
  
2.  **[データ ソース]** ウィンドウからワークシートにフィールドを 1 つドラッグします。  
  
     データがバインドされた <xref:Microsoft.Office.Tools.Excel.NamedRange> コントロールがワークシートに追加されます。 詳細については、次を参照してください。[データ連結と Windows フォーム](/dotnet/framework/winforms/data-binding-and-windows-forms)です。  
  
##  <a name="runtimedoclevel"></a> ドキュメント レベルのプロジェクトの実行時に NamedRange コントロールを追加します。  
 追加することができます、<xref:Microsoft.Office.Tools.Excel.NamedRange>実行時にワークシートにプログラムで制御します。 この方法を使用すると、イベントに応答してホスト コントロールを作成できます。 動的に作成された名前付き範囲は、ワークシートを閉じたときに、ホスト コントロールとしてワークシートに保持されません。 詳細については、次を参照してください。[実行時に Office ドキュメントにコントロールを追加](../vsto/adding-controls-to-office-documents-at-run-time.md)です。  
  
### <a name="to-add-a-namedrange-control-to-a-worksheet-programmatically"></a>プログラムによってワークシートに NamedRange コントロールを追加するには  
  
1.  <xref:Microsoft.Office.Tools.Excel.Worksheet.Startup> の `Sheet1`イベント ハンドラーに、以下のコードを挿入します。このコードでは、 <xref:Microsoft.Office.Tools.Excel.NamedRange> コントロールをセル **A1** に追加して、その <xref:Microsoft.Office.Tools.Excel.NamedRange.Value2%2A> プロパティを `Hello world!`に設定します。  
  
     [!code-csharp[Trin_VstcoreHostControlsExcel#3](../vsto/codesnippet/CSharp/Trin_VstcoreHostControlsExcelCS/Sheet1.cs#3)]
     [!code-vb[Trin_VstcoreHostControlsExcel#3](../vsto/codesnippet/VisualBasic/Trin_VstcoreHostControlsExcelVB/Sheet1.vb#3)]  
  
##  <a name="runtimeaddin"></a> VSTO アドイン プロジェクトでの実行時に NamedRange コントロールを追加します。  
 プログラムによって <xref:Microsoft.Office.Tools.Excel.NamedRange> コントロールを VSTO アドイン プロジェクトの任意の開いているワークシートに追加できます。 動的に作成された名前付き範囲は、ワークシートを閉じたときに、ホスト コントロールとしてワークシートに保持されません。 詳細については、次を参照してください。[拡張 Word 文書と実行時に VSTO アドイン内の Excel ブック](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md)です。  
  
### <a name="to-add-a-namedrange-control-to-a-worksheet-programmatically"></a>プログラムによってワークシートに NamedRange コントロールを追加するには  
  
1.  次のコードでは、開いているワークシートに基づいたワークシート ホスト項目を生成し、 <xref:Microsoft.Office.Tools.Excel.NamedRange> コントロールをセル **A1** に追加して、その <xref:Microsoft.Office.Tools.Excel.NamedRange.Value2%2A> プロパティを `Hello world`に設定します。  
  
     [!code-csharp[Trin_Excel_Dynamic_Controls#7](../vsto/codesnippet/CSharp/Trin_Excel_Dynamic_Controls/ThisAddIn.cs#7)]
     [!code-vb[Trin_Excel_Dynamic_Controls#7](../vsto/codesnippet/VisualBasic/Trin_Excel_Dynamic_Controls/ThisAddIn.vb#7)]  
  
## <a name="see-also"></a>関連項目  
 [Word 文書と実行時に VSTO アドイン内の Excel ブックを拡張します。](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md)   
 [Office ドキュメントのコントロール](../vsto/controls-on-office-documents.md)   
 [NamedRange コントロール](../vsto/namedrange-control.md)   
 [拡張オブジェクトによる Excel を自動化します。](../vsto/automating-excel-by-using-extended-objects.md)   
 [ホスト項目とホスト コントロールの概要](../vsto/host-items-and-host-controls-overview.md)   
 [方法: NamedRange コントロールのサイズを変更します。](../vsto/how-to-resize-namedrange-controls.md)   
 [ホスト項目とホスト コントロールのプログラム上の制限事項](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)  
  
  