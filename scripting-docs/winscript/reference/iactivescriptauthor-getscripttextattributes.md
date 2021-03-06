---
title: "IActiveScriptAuthor::GetScriptTextAttributes |Microsoft ドキュメント"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- IActiveScriptAuthor.GetScriptTextAttributes
apilocation:
- scrobj.dll
helpviewer_keywords:
- IActiveScriptAuthor::GetScriptTextAttributes
ms.assetid: a53451de-cc5c-4b53-8e5f-81e196364caf
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 6aa96623b4356f0a3d17c8b2631840953dac2d51
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2017
---
# <a name="iactivescriptauthorgetscripttextattributes"></a>IActiveScriptAuthor::GetScriptTextAttributes
スクリプト ブロックのテキスト属性を返します。  
  
## <a name="syntax"></a>構文  
  
```  
HRESULT GetScriptTextAttributes(  
    LPCOLESTR        pszCode,  
    ULONG            cch,  
    LPCOLESTR        pszDelimiter,  
    DWORD            dwFlags,  
    SOURCE_TEXT_ATTR *pattr);  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pszCode`  
 [size_is で (`cch`)]、スクリプト ブロックのテキスト。 この文字列は null 終端ではありません。  
  
 `cch`  
 [in]使用するサイズ、`pszCode`と`pattr`パラメーター。  
  
 `pszDelimiter`  
 [in]スクリプトの終わり区切り記号のアドレス。 ときに`pszCode`解析は、テキストのストリームからホスト通常 (など、2 つ単一引用符)、区切り記号を使用してスクリプトレットの末尾を検出します。 スクリプト ブロックの末尾を識別する区切り記号がない場合は、このパラメーターを NULL に設定します。  
  
 `dwFlags`  
 [in]スクリプト ブロックのテキスト属性に関連付けられているフラグです。 次の値の組み合わせが可能です。  
  
|定数|値|説明|  
|--------------|-----------|-----------------|  
|GETATTRTYPE_DEPSCAN|0x0001|SOURCETEXT_ATTR_IDENTIFIER 属性を持つ識別子を特定し、SOURCETEXT_ATTR_MEMBERLOOKUP 属性を持つドット演算子を識別します。|  
|GETATTRFLAG_THIS|0x0100|SOURCETEXT_ATTR_THIS 属性を持つ現在のオブジェクトを識別します。|  
|GETATTRFLAG_HUMANTEXT|0x8000|SOURCETEXT_ATTR_HUMANTEXT 属性を持つ文字列のコンテンツおよびコメントのテキストを識別します。|  
  
 `pattr`  
 [入力、出力、size_is (`cch`)]、スクリプト ブロックのコードの色の情報です。  
  
## <a name="return-value"></a>戻り値  
 `HRESULT`。 有効な値を次の表に示しますが、これ以外にもあります。  
  
|値|説明|  
|-----------|-----------------|  
|`S_OK`|メソッドが成功しました。|  
  
## <a name="remarks"></a>コメント  
  
## <a name="see-also"></a>関連項目  
 [IActiveScriptAuthor インターフェイス](../../winscript/reference/iactivescriptauthor-interface.md)   
 [SOURCE_TEXT_ATTR 列挙型](../../winscript/reference/source-text-attr-enumeration.md)