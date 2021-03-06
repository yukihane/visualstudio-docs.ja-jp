---
title: IDiaEnumLineNumbers |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumLineNumbers interface
ms.assetid: cdf07b4f-19e4-4dcd-8af8-c2dbca586a7c
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 5fb0b457a0efef1c860be7174f012575aec64f99
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2018
---
# <a name="idiaenumlinenumbers"></a>IDiaEnumLineNumbers
データ ソースに含まれるさまざまな行番号を列挙します。  
  
## <a name="syntax"></a>構文  
  
```  
IDiaEnumLineNumbers : IUnknown  
```  
  
## <a name="methods-in-vtable-order"></a>Vtable 順序のメソッド  
 次の表は、メソッドの`IDiaEnumLineNumbers`します。  
  
|メソッド|説明|  
|------------|-----------------|  
|[IDiaEnumLineNumbers::get__NewEnum](../../debugger/debug-interface-access/idiaenumlinenumbers-get-newenum.md)|取得、 [IEnumVARIANT インターフェイス](http://msdn.microsoft.com/en-us/139e3c93-faef-4003-9079-e0e94494db3e)この列挙子のバージョン。|  
|[IDiaEnumLineNumbers::get_Count](../../debugger/debug-interface-access/idiaenumlinenumbers-get-count.md)|行番号の数を取得します。|  
|[IDiaEnumLineNumbers::Item](../../debugger/debug-interface-access/idiaenumlinenumbers-item.md)|インデックスを使用して、行番号を取得します。|  
|[IDiaEnumLineNumbers::Next](../../debugger/debug-interface-access/idiaenumlinenumbers-next.md)|列挙のシーケンス内の行番号の指定した数を取得します。|  
|[IDiaEnumLineNumbers::Skip](../../debugger/debug-interface-access/idiaenumlinenumbers-skip.md)|列挙のシーケンス内の行番号の指定した数をスキップします。|  
|[IDiaEnumLineNumbers::Reset](../../debugger/debug-interface-access/idiaenumlinenumbers-reset.md)|列挙のシーケンスを先頭にリセットします。|  
|[IDiaEnumLineNumbers::Clone](../../debugger/debug-interface-access/idiaenumlinenumbers-clone.md)|現在の列挙子と同じ列挙の状態を含む列挙子を作成します。|  
  
## <a name="remarks"></a>コメント  
  
## <a name="notes-for-callers"></a>呼び出し元のノート  
 次のメソッドのいずれかを呼び出すことによってこのインターフェイスを取得、 [IDiaSession](../../debugger/debug-interface-access/idiasession.md)インターフェイス。  
  
-   [IDiaSession::findLines](../../debugger/debug-interface-access/idiasession-findlines.md)  
  
-   [IDiaSession::findLinesByAddr](../../debugger/debug-interface-access/idiasession-findlinesbyaddr.md)  
  
-   [IDiaSession::findLinesByRVA](../../debugger/debug-interface-access/idiasession-findlinesbyrva.md)  
  
-   [IDiaSession::findLinesByVA](../../debugger/debug-interface-access/idiasession-findlinesbyva.md)  
  
-   [IDiaSession::findLinesByLinenum](../../debugger/debug-interface-access/idiasession-findlinesbylinenum.md)  
  
## <a name="example"></a>例  
 この例は、取得する方法を示します、`IDiaEnumLineNumbers`セッションからのインターフェイスです。 ここでは、例は関数の行番号の列挙を取得する方法を示しています。 (によって表される`pSymbol`)。 行番号を使用するより詳細な例については、 [IDiaLineNumber](../../debugger/debug-interface-access/idialinenumber.md)インターフェイスです。  
  
```C++  
void dumpFunctionLines( IDiaSymbol* pSymbol, IDiaSession* pSession )  
{  
    ULONGLONG length = 0;  
    DWORD isect = 0;  
    DWORD offset = 0;  
    pSymbol->get_addressSection( &isect );  
    pSymbol->get_addressOffset( &offset );  
    pSymbol->get_length( &length );  
    if ( isect != 0 && length > 0 )  
    {  
        CComPtr< IDiaEnumLineNumbers > pLines;  
        if ( SUCCEEDED( pSession->findLinesByAddr(  
                                      isect,  
                                      offset,  
                                      static_cast<DWORD>( length ),  
                                      &pLines )  
                      )  
           )  
        {  
            // Do something with the enumeration  
        }  
    }  
}  
```  
  
## <a name="requirements"></a>要件  
 ヘッダー: Dia2.h  
  
 ライブラリ: diaguids.lib  
  
 DLL: msdia80.dll  
  
## <a name="see-also"></a>関連項目  
 [インターフェイス (Debug Interface Access SDK)](../../debugger/debug-interface-access/interfaces-debug-interface-access-sdk.md)   
 [IDiaSession](../../debugger/debug-interface-access/idiasession.md)   
 [Idiasession::findlinesbylinenum](../../debugger/debug-interface-access/idiasession-findlinesbylinenum.md)   
 [Idiasession::findlinesbyrva](../../debugger/debug-interface-access/idiasession-findlinesbyrva.md)   
 [Idiasession::findlinesbyva](../../debugger/debug-interface-access/idiasession-findlinesbyva.md)   
 [Idiasession::findlines](../../debugger/debug-interface-access/idiasession-findlines.md)   
 [IDiaSession::findLinesByAddr](../../debugger/debug-interface-access/idiasession-findlinesbyaddr.md)