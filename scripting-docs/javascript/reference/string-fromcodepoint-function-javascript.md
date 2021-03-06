---
title: "String.fromCodePoint 関数 (JavaScript) |Microsoft ドキュメント"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 7c4c057b-c67a-4b10-afdd-4f75c7c5988c
caps.latest.revision: "3"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 0905b392606bec9fb59b08a04129ce30cb013db1
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2017
---
# <a name="stringfromcodepoint-function-javascript"></a>String.fromCodePoint 関数 (JavaScript)
Unicode UTF-16 コード ポイントに関連付けられた文字列を返します。  
  
## <a name="syntax"></a>構文  
  
```  
String.fromCodePoint(...codePoints);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `...codePoints`  
 必須です。 1 つ以上の UTF-16 コード ポイント値を指定する rest パラメーター。  
  
## <a name="remarks"></a>コメント  
 この関数は、`...codePoints` が有効な UFT-16 コード ポイントではない場合には `RangeError` 例外をスローします。  
  
## <a name="example"></a>例  
 次の例は、`fromCodePoint` 関数の使用法を示しています。  
  
```JavaScript  
var str1 = String.fromCodePoint(0x20BB7);  
var str2 = String.fromCodePoint(98);  
var str3 = String.fromCodePoint(97, 98, 99);  
  
if(console && console.log) {  
    console.log(str1);  
    console.log(str2);  
    console.log(str3);  
}  
  
// Output:  
// 𠮷  
// b  
// abc   
```  
  
## <a name="requirements"></a>要件  
 [!INCLUDE[jsv12](../../javascript/reference/includes/jsv12-md.md)]