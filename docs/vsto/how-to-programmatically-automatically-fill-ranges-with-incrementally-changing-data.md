---
title: '方法: 増分するデータを自動的にプログラムで塗りつぶし範囲 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Autofill method [Excel]
- filling ranges automatically
- ranges, automatically filling
- workbooks, filling ranges
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: e358869dea101d0c0ca012acd46b7822e6cf5873
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-programmatically-automatically-fill-ranges-with-incrementally-changing-data"></a>方法: 増分するデータを範囲内にプログラムによって自動的に入力する
  <xref:Microsoft.Office.Interop.Excel.Range.AutoFill%2A>のメソッド、<xref:Microsoft.Office.Interop.Excel.Range>オブジェクトでは、値を含むワークシートの範囲を自動的に入力することができます。 ほとんどの場合、<xref:Microsoft.Office.Interop.Excel.Range.AutoFill%2A>増分を増減させる範囲内の値を格納するメソッドを使用します。 省略可能な定数を指定することによって、動作を指定することができます、<xref:Microsoft.Office.Interop.Excel.XlAutoFillType>列挙します。  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
 使用する場合は、2 つの範囲を指定する必要があります<xref:Microsoft.Office.Interop.Excel.Range.AutoFill%2A>:  
  
-   呼び出すの範囲、<xref:Microsoft.Office.Interop.Excel.Range.AutoFill%2A>メソッドは、塗りつぶしの開始位置を指定しますが、初期値が含まれています。  
  
-   パラメーターとして渡される塗りつぶすには、必要な範囲、<xref:Microsoft.Office.Interop.Excel.Range.AutoFill%2A>メソッドです。 このターゲット範囲には、初期値を含む範囲を含める必要があります。  
  
    > [!NOTE]  
    >  渡すことはできません、<xref:Microsoft.Office.Tools.Excel.NamedRange>制御の代わりに、<xref:Microsoft.Office.Interop.Excel.Range>です。 詳細については、「 [ホスト項目およびホスト コントロールのプログラム上の制限事項](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)」を参照してください。  
  
## <a name="example"></a>例  
 [!code-csharp[Trin_VstcoreExcelAutomation#49](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#49)]
 [!code-vb[Trin_VstcoreExcelAutomation#49](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#49)]  
  
## <a name="compiling-the-code"></a>コードのコンパイル  
 格納する範囲の最初のセルには、初期値を含める必要があります。  
  
 この例では、3 つの領域を設定することが必要です。  
  
-   列 B では、5 つの曜日を含むです。 初期値に「**月曜日**セル B1 にします。  
  
-   列 C には 5 つの月が含まれます。 初期値に「**年 1 月**セル C1 にします。  
  
-   列 D では、一連の数字、行ごとに 2 つずつ増分されます。 初期値として、入力**4**セル D1 と**6**セル D2 にします。  
  
## <a name="see-also"></a>関連項目  
 [範囲の使用](../vsto/working-with-ranges.md)   
 [方法: プログラムによってワークシートの範囲をコード内を参照してください](../vsto/how-to-programmatically-refer-to-worksheet-ranges-in-code.md)   
 [方法: プログラムによってブック内の範囲にスタイルを適用](../vsto/how-to-programmatically-apply-styles-to-ranges-in-workbooks.md)   
 [方法: プログラムによって Excel の計算を実行](../vsto/how-to-programmatically-run-excel-calculations-programmatically.md)   
 [ホスト項目とホスト コントロールの概要](../vsto/host-items-and-host-controls-overview.md)   
 [Office ソリューションの省略可能なパラメーター](../vsto/optional-parameters-in-office-solutions.md)  
  
  