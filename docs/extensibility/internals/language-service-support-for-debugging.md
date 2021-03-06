---
title: デバッグのための言語サービス サポート |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debugger, language support
- language services, debugging support
ms.assetid: 7a44067f-a410-4a6a-84d2-bda5184140bc
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 59c044f6ffc3f2cdf0749f0192f4b8fa458b00cc
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/16/2018
---
# <a name="language-service-support-for-debugging"></a>デバッグのための言語サービスのサポート
言語サービスが使用して、デバッガーをサポートする機能を提供できる、<xref:Microsoft.VisualStudio.TextManager.Interop.IVsLanguageDebugInfo>インターフェイスです。 これらの機能は、ブレークポイントを検証する式のリストを指定、 **[自動変数]**ウィンドウです。  
  
 ただし、式エバリュエーターを使用する言語をデバッグする必要があります。 式エバリュエーターは、デバッグ中に値を生成するために式を評価します。 CLR 式エバリュエーターを実装する方法の詳細についてを参照してください。  
  
-   [CLR 式エバリュエーター](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators)  
  
-   [マネージ式エバリュエーターのサンプル](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample)  
  
## <a name="compiler-output"></a>コンパイラ出力  
 コンパイラの型は、使用する言語のデバッグを実装するための必要を決定します。 場合は、コンパイラは、Windows オペレーティング システムを対象し、.pdb ファイルに書き込み、デバッグ エンジンは Visual Studio に統合されているネイティブ コードでプログラムをデバッグすることができます。 場合は、コンパイラは、Microsoft intermediate language (MSIL) を生成する、デバッグ エンジンで、Visual Studio に統合されてもマネージ コードでプログラムをデバッグすることができます。 コンパイラは、独自のオペレーティング システムまたは別のランタイム環境を対象する場合、に、独自のデバッグ エンジンを記述する必要があります。  
  
 使用する言語のデバッグの実装の詳細については、次を参照してください。[作業の開始](../../extensibility/debugger/getting-started-with-debugger-extensibility.md)Visual Studio Debugging SDK でします。