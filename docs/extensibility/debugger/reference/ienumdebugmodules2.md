---
title: IEnumDebugModules2 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IEnumDebugModules2
helpviewer_keywords:
- IEnumDebugModules2
ms.assetid: 4fe28074-a960-41ad-b74d-b57f04c0c0ad
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: dd3ca02776aae4a7b4cd22485eba9827f4731d5d
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/16/2018
---
# <a name="ienumdebugmodules2"></a>IEnumDebugModules2
このインターフェイスは、モジュールの一覧を列挙します。  
  
## <a name="syntax"></a>構文  
  
```  
IEnumDebugModules2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>実装についてのメモ  
 デバッグ エンジン (DE) では、プログラムに読み込まれたモジュールの一覧を表すためには、このインターフェイスを実装します。  
  
## <a name="notes-for-callers"></a>呼び出し元のノート  
 Visual Studio 呼び出し[EnumModules](../../../extensibility/debugger/reference/idebugprogram2-enummodules.md)このインターフェイスを取得します。  
  
## <a name="methods-in-vtable-order"></a>Vtable 順序のメソッド  
 次の表は、メソッドの`IEnumDebugModules2`します。  
  
|メソッド|説明|  
|------------|-----------------|  
|[次へ](../../../extensibility/debugger/reference/ienumdebugmodules2-next.md)|列挙のシーケンス内のモジュールの指定した数を取得します。|  
|[Skip](../../../extensibility/debugger/reference/ienumdebugmodules2-skip.md)|列挙のシーケンス内のモジュールの指定した数をスキップします。|  
|[リセット](../../../extensibility/debugger/reference/ienumdebugmodules2-reset.md)|列挙のシーケンスを先頭にリセットします。|  
|[複製](../../../extensibility/debugger/reference/ienumdebugmodules2-clone.md)|現在の列挙子と同じ列挙の状態を含む列挙子を作成します。|  
|[GetCount](../../../extensibility/debugger/reference/ienumdebugmodules2-getcount.md)|モジュールの数を取得します。|  
  
## <a name="remarks"></a>コメント  
 Visual Studio を更新するには、主にこのインターフェイスを使用して、**モジュール**ウィンドウです。  
  
 Visual Studio でのデバッグの目的では、プログラムはためモジュール境界を越えることがコード命令の論理シーケンスは 1 つのモジュールの一覧の必要性[IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)インターフェイスです。 一覧の最初のモジュールには、通常、関連付けられたプログラムの初期のエントリ ポイントが含まれています。  
  
## <a name="requirements"></a>要件  
 ヘッダー: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 アセンブリ: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>関連項目  
 [コア インターフェイス](../../../extensibility/debugger/reference/core-interfaces.md)   
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)   
 [EnumModules](../../../extensibility/debugger/reference/idebugprogram2-enummodules.md)