---
title: IDebugProperty2::SetValueAsReference |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugProperty2::SetValueAsReference
helpviewer_keywords:
- IDebugProperty2::SetValueAsReference method
ms.assetid: 341b1b89-4ab8-4e1c-abe2-fb955df5c6b0
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 4f8d871e6193835b51336a48355fde78fe95e103
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/16/2018
---
# <a name="idebugproperty2setvalueasreference"></a>IDebugProperty2::SetValueAsReference
指定された参照の値には、このプロパティの値を設定します。  
  
## <a name="syntax"></a>構文  
  
```cpp  
HRESULT SetValueAsReference(  
   IDebugReference2** rgpArgs,  
   DWORD              dwArgCount,  
   IDebugReference2*  pValue,  
   DWORD              dwTimeout  
);  
```  
  
```csharp  
int SetValueAsReference(  
   IDebugReference2[] rgpArgs,  
   uint               dwArgCount,  
   IDebugReference2   pValue,  
   uint               dwTimeout  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `rgpArgs`  
 [in]マネージ コード プロパティ set アクセス操作子に渡す引数の配列。 プロパティ set アクセス操作子が引数を受け取らない場合、またはこの[IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)オブジェクトは、このようなプロパティ setter を参照しない`rgpArgs`null 値にする必要があります。 このパラメーターは、通常、null 値です。  
  
 `dwArgCount`  
 [in]引数の数、`rgpArgs`配列。  
  
 `pValue`  
 [in]形式で、参照、 [IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md)オブジェクトを使用してこのプロパティを設定する値にします。  
  
 `dwTimeout`  
 [in]時間をミリ秒単位で、値を設定するためです。 一般的な値は`INFINITE`します。 これは、すべての可能な評価が実行できる時間の長さに影響します。  
  
## <a name="return-value"></a>戻り値  
 成功した場合を返します`S_OK`です。 それ以外の場合にエラーを返しますコードは、通常、次のいずれか。  
  
|Error|説明|  
|-----------|-----------------|  
|`E_SETVALUEASREFERENCE_NOTSUPPORTED`|参照から値を設定することはできません。|  
|`E_SETVALUE_VALUE_CANNOT_BE_SET`|このプロパティは、メソッドを参照すると、値を設定できません。|  
|`E_SETVALUE_VALUE_IS_READONLY`|値は読み取り専用と、設定することはできません。|  
|`E_NOTIMPL`|メソッドは実装されていません。|  
  
## <a name="see-also"></a>関連項目  
 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)   
 [IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md)