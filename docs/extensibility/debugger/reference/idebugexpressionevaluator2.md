---
title: IDebugExpressionEvaluator2 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- IDebugExpressionEvaluator2 interface
ms.assetid: cebe649f-1c77-4d33-854f-30d4f00eceb4
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 3b4fc704475c35e9fcd07bba260eb3de9626fe2d
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/16/2018
---
# <a name="idebugexpressionevaluator2"></a>IDebugExpressionEvaluator2
> [!IMPORTANT]
>  Visual Studio 2015 では、式エバリュエーターを実装するには、この方法は推奨されなくなりました。 CLR 式エバリュエーターを実装する方法の詳細についてを参照してください[CLR 式エバリュエーター](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators)と[マネージ式エバリュエーターのサンプル](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample)です。  
  
 式エバリュエーター (EE) の拡張のバージョンを表します。  
  
## <a name="syntax"></a>構文  
  
```  
IDebugExpressionEvaluator2 : IDebugExpressionEvaluator  
```  
  
## <a name="notes-for-implementers"></a>実装についてのメモ  
 このインターフェイスは、式エバリュエーターで実装されます。  
  
## <a name="methods"></a>メソッド  
 メソッドだけでなく、 [IDebugExpressionEvaluator](../../../extensibility/debugger/reference/idebugexpressionevaluator.md)インターフェイス、このインターフェイスは、次のメソッドを実装します。  
  
|メソッド|説明|  
|------------|-----------------|  
|[GetService](../../../extensibility/debugger/reference/idebugexpressionevaluator2-getservice.md)|一意の識別子を指定されたサービス オブジェクトを取得します。|  
|[PreloadModules](../../../extensibility/debugger/reference/idebugexpressionevaluator2-preloadmodules.md)|指定されたシンボル プロバイダーによって指定されたモジュールを再度読み込みます。|  
|[SetCallback](../../../extensibility/debugger/reference/idebugexpressionevaluator2-setcallback.md)|デバッガー エンジン (DE) を使用してメトリックの設定を読み取る、コールバック インターフェイスを指定するには、式エバリュエーター (EE) を有効にします。|  
|[SetCorPath](../../../extensibility/debugger/reference/idebugexpressionevaluator2-setcorpath.md)|デバッガーで読み込まれる共通言語ランタイム (CLR) へのパスを設定します。|  
|[SetIDebugIDECallback](../../../extensibility/debugger/reference/idebugexpressionevaluator2-setidebugidecallback.md)|式エバリュエーターを初期化中にコールバックを渡すためにデバッグ エンジンを有効にします。|  
|[終了](../../../extensibility/debugger/reference/idebugexpressionevaluator2-terminate.md)|停止し、式エバリュエーターをクリーンアップします。|  
  
## <a name="requirements"></a>要件  
 ヘッダー: Ee.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 アセンブリ: Microsoft.VisualStudio.Debugger.Interop.dll