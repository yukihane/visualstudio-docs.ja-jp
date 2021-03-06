---
title: IDebugExpressionEvaluator::Parse |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugExpressionEvaluator::Parse
helpviewer_keywords:
- IDebugExpressionEvaluator::Parse method
ms.assetid: e6e31b3a-63a7-4293-bcda-267eb78dffb6
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 2a10a65564682b5c82350eb5c22af3f217a3a993
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/16/2018
---
# <a name="idebugexpressionevaluatorparse"></a>IDebugExpressionEvaluator::Parse
このメソッドは、式の文字列を解析された式に変換します。  
  
## <a name="syntax"></a>構文  
  
```cpp  
HRESULT Parse(   
   LPCOLESTR                upstrExpression,  
   PARSEFLAGS               dwFlags,  
   UINT                     nRadix,  
   BSTR*                    pbstrError,  
   UINT*                    pichError,  
   IDebugParsedExpression** ppParsedExpression  
);  
```  
  
```csharp  
int Parse(  
   string                     upstrExpression,   
   enum_PARSEFLAGS            dwFlags,   
   uint                       nRadix,   
   out string                 pbstrError,   
   out uint                   pichError,   
   out IDebugParsedExpression ppParsedExpression  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `upstrExpression`  
 [in]式の文字列を解析できません。  
  
 `dwFlags`  
 [in]コレクション[PARSEFLAGS](../../../extensibility/debugger/reference/parseflags.md)式の解析方法を決定する定数。  
  
 `nRadix`  
 [in]任意の数値情報を解釈するために使用する基数。  
  
 `pbstrError`  
 [out]人間が判読できるテキストとして、エラーを返します。  
  
 `pichError`  
 [out]式の文字列で、エラーの先頭の文字の位置を返します。  
  
 `ppParsedExpression`  
 [out]解析された式を返します、 [IDebugParsedExpression](../../../extensibility/debugger/reference/idebugparsedexpression.md)オブジェクト。  
  
## <a name="return-value"></a>戻り値  
 成功した場合を返します`S_OK`、それ以外のエラー コードを返します。  
  
## <a name="remarks"></a>コメント  
 このメソッドは、実際の値ではなく、解析された式を生成します。 解析の式が評価する準備ができてつまり、値に変換します。  
  
## <a name="see-also"></a>関連項目  
 [IDebugExpressionEvaluator](../../../extensibility/debugger/reference/idebugexpressionevaluator.md)   
 [IDebugParsedExpression](../../../extensibility/debugger/reference/idebugparsedexpression.md)   
 [PARSEFLAGS](../../../extensibility/debugger/reference/parseflags.md)