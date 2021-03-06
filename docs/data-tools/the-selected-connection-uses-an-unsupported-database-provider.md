---
title: 選択した接続では、サポートされていないデータベース プロバイダーが使用されています
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: 4d25dfa1-8fa4-4529-9b90-973bc2ec2993
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 77519a5497c26553e2023862e46f3ba618e4f99f
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/26/2018
---
# <a name="the-selected-connection-uses-an-unsupported-database-provider"></a>選択した接続では、サポートされていないデータベース プロバイダーが使用されています

SQL Server からの .NET Framework データ プロバイダーを使用しない項目をドラッグすると、このメッセージが表示される**サーバー エクスプ ローラー**/**データベース エクスプ ローラー**上に、 [LINQ to SQLVisual Studio tools](../data-tools/linq-to-sql-tools-in-visual-studio2.md)です。

[!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)]では、.NET Framework Provider for SQL Server を使用するデータ接続のみがサポートされます。 有効な接続は、Microsoft SQL Server または Microsoft SQL Server データベース ファイルへの接続だけです。

このエラーを修正する項目のみを追加する SQL Server の .NET Framework データ プロバイダーを使用するデータ接続から、[!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)]です。

## <a name="see-also"></a>関連項目

- <xref:System.Data.SqlClient>
- [O/R デザイナーのメッセージ](../data-tools/o-r-designer-messages.md)
- [Visual Studio での LINQ to SQL ツールします。](../data-tools/linq-to-sql-tools-in-visual-studio2.md)
