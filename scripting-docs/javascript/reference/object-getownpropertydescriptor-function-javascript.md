---
title: "Object.getOwnPropertyDescriptor 関数 (JavaScript) |Microsoft ドキュメント"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- getOwnPropertyDescriptor method [JavaScript]
ms.assetid: 8f0e1c90-c4f9-44c4-bf76-726bacecbc14
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: dd147d567fc4d8a39d7a251d55772c40518e7a26
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2017
---
# <a name="objectgetownpropertydescriptor-function-javascript"></a>Object.getOwnPropertyDescriptor 関数 (JavaScript)
指定されたオブジェクトの own プロパティ記述子を取得します。 own プロパティ記述子は、オブジェクトで直接定義され、オブジェクトのプロトタイプから継承されない記述子です。  
  
## <a name="syntax"></a>構文  
  
```  
Object.getOwnPropertyDescriptor(object, propertyname)  
```  
  
## <a name="parameters"></a>パラメーター  
 `object`  
 必須です。 プロパティを格納するオブジェクト。  
  
 `propertyname`  
 必須です。 プロパティの名前。  
  
## <a name="return-value"></a>戻り値  
 プロパティの記述子。  
  
## <a name="remarks"></a>コメント  
 `Object.getOwnPropertyDescriptor` 関数を使用すると、プロパティの属性を記述する記述子オブジェクトを取得できます。  
  
 [Object.defineProperty 関数](../../javascript/reference/object-defineproperty-function-javascript.md)を追加またはプロパティを変更するために使用します。  
  
## <a name="data-property-example"></a>データ プロパティの例  
 次の例では、データ プロパティ記述子を取得し、それを使用してプロパティを読み取り専用にします。  
  
```JavaScript  
// Create a user-defined object.  
var obj = {};  
  
// Add a data property.  
obj.newDataProperty = "abc";  
  
// Get the property descriptor.  
var descriptor = Object.getOwnPropertyDescriptor(obj, "newDataProperty");  
  
// Change a property attribute.  
descriptor.writable = false;  
Object.defineProperty(obj, "newDataProperty", descriptor);  
  
```  
  
 プロパティ属性を一覧表示するには、この例に次のコードを追加します。  
  
```JavaScript  
// Get the descriptor from the object.  
var desc2 = Object.getOwnPropertyDescriptor(obj, "newDataProperty");  
  
// List the descriptor attributes.  
for (var prop in desc2) {  
    document.write(prop + ': ' + desc2[prop]);  
    document.write("<br />");  
}  
  
// Output:  
// value: abc  
// writable: false  
// enumerable: true  
// configurable: true  
```  
  
## <a name="requirements"></a>要件  
 すべての機能は、[!INCLUDE[jsv9text](../../javascript/includes/jsv9text-md.md)] でサポートされます。  
  
 [!INCLUDE[jsv58textspecific](../../javascript/reference/includes/jsv58textspecific-md.md)] は DOM オブジェクトをサポートしますが、ユーザー定義オブジェクトはサポートされません。 `enumerable` 属性と `configurable` 属性は、指定できますが使用されません。  
  
## <a name="see-also"></a>関連項目  
 [ドキュメント オブジェクト モデル プロトタイプ、パート 2: アクセサー (get アクセス操作子と set アクセス操作子) のサポート](http://msdn.microsoft.com/library/dd229916\(v=VS.85\).aspx)   
 [Object.defineProperty 関数](../../javascript/reference/object-defineproperty-function-javascript.md)