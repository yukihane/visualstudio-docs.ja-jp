---
title: Visual Studio で EditorConfig をサポートするために言語サービスを拡張 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/22/2017
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- editorconfig [extensibility]
- editorconfig, supporting in a language service
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 2aa80903b3e5ea2723ec576fa463161b8d003c93
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/16/2018
---
# <a name="supporting-editorconfig-for-your-language-service"></a>言語サービスの EditorConfig をサポートします。

[EditorConfig](http://editorconfig.org/)ファイルを使用すると、プロジェクトごとに 1 つのインデントのサイズなどの一般的なテキスト エディター オプションについて説明します。 EditorConfig ファイルの Visual Studio のサポートに関する詳細については、次を参照してください。 [EditorConfig を使用してポータブル エディターの設定を作成する](../ide/create-portable-custom-editor-options.md)です。

ほとんどの場合、Visual Studio 言語サービスを実装するとき、EditorConfig ユニバーサル プロパティをサポートするための追加の作業は必要ありません。 ユーザーがファイルを開くと、コア エディターが .editorconfig ファイルを自動的に検出して読み込み、適切なテキスト バッファーとビュー オプションを設定します。 ただし、タブとスペースなどの編集、一部の言語サービスはグローバル設定を使用するのではなく、適切なコンテキストのテキスト表示 オプションを使用できます。 そのような場合は、EditorConfig ファイルをサポートするように言語サービスを更新する必要があります。

グローバルに置き換えることで、EditorConfig ファイルをサポートするために言語サービスを更新するために必要な変更は、次_言語固有_オプションは、_コンテキスト_オプション。

## <a name="indent-style"></a>インデント スタイル

言語固有のオプション | コンテキストのオプション
-------|--------
Microsoft.VisualStudio.TextManager.Interop.LANGPREFERENCES.fInsertTabs<br/>Microsoft.VisualStudio.Package.LanguagePreferences.InsertTabs|!textBufferOptions.GetOptionValue(DefaultOptions.ConvertTabsToSpacesOptionId)<br/>!textView.Options.GetOptionValue(DefaultOptions.ConvertTabsToSpacesOptionId)

## <a name="indent-size"></a>[インデント サイズ]

言語固有のオプション | コンテキストのオプション
-------|--------
Microsoft.VisualStudio.TextManager.Interop.LANGPREFERENCES.uIndentSize<br/>Microsoft.VisualStudio.Package.LanguagePreferences.InsertTabs.IndentSize|textBufferOptions.GetOptionValue(DefaultOptions.IndentSizeOptionId)<br/>textView.Options.GetOptionValue(DefaultOptions.IndentSizeOptionId)

## <a name="tab-size"></a>[タブ サイズ]

言語固有のオプション | コンテキストのオプション
-------|--------
Microsoft.VisualStudio.TextManager.Interop.LANGPREFERENCES.uTabSize<br/>Microsoft.VisualStudio.Package.LanguagePreferences.InsertTabs.TabSize|textBufferOptions.GetOptionValue(DefaultOptions.TabSizeOptionId)<br/>textView.Options.GetOptionValue(DefaultOptions.TabSizeOptionId)

## <a name="see-also"></a>関連項目

[EditorConfig を使用してポータブル エディターの設定を作成します。](../ide/create-portable-custom-editor-options.md)  
[エディターと言語サービスの拡張](../extensibility/extending-the-editor-and-language-services.md)