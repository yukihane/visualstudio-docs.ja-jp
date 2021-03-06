---
title: ワークフロー デザイナーの従来のワークフローのデバッグ
ms.date: 11/04/2016
ms.topic: conceptual
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
helpviewer_keywords:
- workflows, debugging
- debugging, workflows
- debugging workflows
ms.assetid: e6097b47-760a-4b30-a92c-ae70cdbda49f
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 33a8358c5d62b938fc64d608c9b4546ab1745aaa
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/26/2018
---
# <a name="debugging-legacy-workflows"></a>従来のワークフローのデバッグ

Visual Studio で、従来の Windows ワークフロー デザイナーを使用して、その target.NET Framework 3.0 または 3.5 は、Windows Workflow Foundation (WF) アプリケーションをビルドするが場合をデバッグするその他のプログラムと同様に、ワークフロー、ブレークポイントの設定プロセスへのアタッチスレッドと呼び出し履歴を調べることです。 また、リモート デバッグを実行することもできます。

> [!NOTE]
> コンピューターに複数のバージョンの Visual Studio をインストールしてアンインストールした場合、WF3 のデバッグは失敗し、次のいずれかが発生する可能性があります。
>
> -   ブレークポイントがヒットしません。
> -   次のメッセージが表示されます。
>
> **Web サーバーでデバッグを開始できません。デバッガーが正しくインストールされていません。要求された種類のコードがデバッグできません。セットアップを実行してインストールするか、デバッガーを修復します。**
>
> .NET Framework 3.0 または 3.5 のワークフローのデバッグ時にこれらのシナリオのいずれかが発生する場合は、Visual Studio インストールの修復を実行してください。

 Windows Workflow Foundation は、次のような標準の Visual Studio デバッグ ウィンドウに統合されています。

-   **ブレークポイント**: 想定どおりに動作しますが、関数名のアクティビティを指定します。

-   **呼び出し履歴**: ワークフロー インスタンス内で実行されたアクティビティの概要を変更します。 内のエントリ、**呼び出し履歴**ウィンドウは、実行されるアクティビティの深さ優先検索します。 エントリをダブルクリックすると、選択したアクティビティにフォーカスを設定できます。

-   **スレッド**: デバッグ中は、ワークフロー インスタンスのインスタンス ID を提供します。

 Visual Studio for Windows Workflow Foundation は、次のデバッグ機能をサポートしません。

-   デザイナ画面上の条件付きブレークポイント

-   クイック ウォッチ

-   次のステートメントの設定

-   カーソル行の前まで実行

-   エディット コンティニュ

-   ジャスト イン タイム デバッグ

-   混合モードのデバッグ