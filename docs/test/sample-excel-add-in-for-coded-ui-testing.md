---
title: コード化された UI テスト用の Excel アドインのサンプル
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.topic: sample
helpviewer_keywords:
- coded UI tests, Excel Add-in sample
ms.author: gewarren
manager: douge
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: a7d9c2e4e73ab2695f49cdcbd6f9a903b5db3229
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/26/2018
---
# <a name="sample-excel-add-in-for-coded-ui-testing"></a>コード化された UI テスト用の Excel アドインのサンプル
この [!INCLUDE[ofprexcel](../test/includes/ofprexcel_md.md)] 用アドイン サンプルは、Excel ワークシートのコード化された UI テストを明確にサポートし、Visual Studio Enterprise で動作するように設計されています。 このアドインは、Visual Studio Tools for Office を使用して作成されています。

 Excel アドインを作成する方法の詳細については、「[チュートリアル : 初めての Excel 用 VSTO アドインの作成](http://msdn.microsoft.com/Library/a855e2be-3ecf-4112-a7f5-ec0f7fad3b5f)」を参照するか、または MSDN で "Excel アドイン" を検索してください。

 Excel アドインは Excel 用のコード化された UI テスト拡張機能に関するこのドキュメントの主題ではありませんが、いくつかのコメントが役立ちます。

 このアドインの重要な部分:

-   `ThisAddIn` クラス - `ExcelUICommunicator` と [Excel 用にコード化された UI テストの拡張子のサンプル](../test/sample-coded-ui-test-extension-for-excel.md)の間の .NET リモート処理チャネルを管理します。

-   `ExcelCodedUIAddinHelper_TemporaryKey.pfx` - アドインのテスト用のセキュリティ証明書。

-   `ExcelUICommunicator` クラス - このクラスは、`IExcelUICommunication` インターフェイスを実装します。

## <a name="thisaddin-class"></a>ThisAddIn クラス
 このクラスのほとんどは、実際に Excel アドイン プロジェクトを作成するときに Visual Studio Tools for Office によって `ThisAddIn.Designer.cs` ファイルに生成されます。

 実装する必要があるメンバーは、`ThisAddIn_Startup()` と `ThisAddIn_Shutdown()` のイベント ハンドラーです。 これらのイベント ハンドラーは、`ExcelUICommunicator` によって使用される .NET リモート処理チャネルを初期化または閉じることを目的としています。

## <a name="excelcodeduiaddinhelpertemporarykeypfx"></a>ExcelCodedUIAddinHelper_TemporaryKey.pfx
 このファイルには、Visual Studio Tools for Office によって生成され、アドインと拡張機能のテストのために Excel プロセスで動作するのに必要なアドイン アセンブリのアクセス許可を与える一時的なセキュリティ証明書が含まれます。 この証明書を削除した後、プロジェクトの**プロパティ** ウィンドウの **[署名]** タブで新しい証明書を作成するか、または独自のテスト用証明書をアタッチする必要があります。

## <a name="exceluicommunicator-class"></a>ExcelUICommunicator クラス
 このクラスは、`IExcelUITestCommunication` インターフェイスを実装し、Excel オブジェクト モデルから要求された UI 情報を取得します。 詳細については、「[Excel Communicator インターフェイスのサンプル](../test/sample-excel-communicator-interface.md)」を参照してください。

## <a name="see-also"></a>関連項目

- [コード化された UI テストと操作の記録を拡張して Microsoft Excel をサポート](../test/extending-coded-ui-tests-and-action-recordings-to-support-microsoft-excel.md)
- [チュートリアル: 初めての Excel 用 VSTO アドインの作成](http://msdn.microsoft.com/Library/a855e2be-3ecf-4112-a7f5-ec0f7fad3b5f)
- [Office および SharePoint 開発](/office-dev/office-dev/office-and-sharepoint-development-in-visual-studio)
