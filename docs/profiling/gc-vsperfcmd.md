---
title: GC (VSPerfCmd) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: 7c81e88b-a748-4cf5-a7a1-3429608e1b54
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 08c9de6d307b54829e2f0783cf0ff272f399de68
ms.sourcegitcommit: 046a9adc5fa6d6d05157204f5fd1a291d89760b7
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2018
---
# <a name="gc-vsperfcmd"></a>GC (VSPerfCmd)
**GC** オプションは、.NET Framework メモリ割り当てとオブジェクト有効期間データを収集できます。 **GC** オプションはサンプリング プロファイリング方法でのみ、かつ、**Launch** オプションとの併用でのみ利用できます。  
  
 **GC** オプションを使用するとき、VSPerfClrEnv **/sampleon** コマンドは必要ありません。  
  
 パラメーターが指定されていない場合、あるいは **Allocation** パラメーターが指定されている場合、.NET Framework メモリ割り当てデータのみが収集されます。 **Lifetime** パラメーターが指定されている場合、.NET Framework メモリ割り当てと .NET Framework オブジェクト有効期間データの両方が収集されます。  
  
## <a name="syntax"></a>構文  
  
```cmd  
VSPerfCmd.exe /Launch:AppName /GC[:{Allocation|Lifetime}] [Options]  
```  
  
#### <a name="parameters"></a>パラメーター  
 **Allocation**  
 既定モード。 .NET Framework メモリ割り当てデータを収集します。  
  
 **有効期間**  
 .NET Framework メモリ割り当てデータと .NET Framework オブジェクト有効期間データの両方を収集します。  
  
## <a name="required-options"></a>必須オプション  
 **GC** オプションは、**Launch** オプションと一緒に指定する場合にのみ使用できます。  
  
 **Launch:** `AppName`  
 指定したアプリケーションを起動し、サンプリング メソッドでプロファイリングを開始します。  
  
## <a name="example"></a>例  
 次の例では、アプリケーションが起動し、.NET Framework メモリ割り当てデータが収集されます。  
  
```cmd  
VSPerfCmd.exe /Launch:TestApp.exe /gc  
```  
  
## <a name="see-also"></a>参照  
 [VSPerfCmd](../profiling/vsperfcmd.md)   
 [スタンドアロン アプリケーションのプロファイリング](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [ASP.NET Web アプリケーションのプロファイリング](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [プロファイリング (サービスの)](../profiling/command-line-profiling-of-services.md)