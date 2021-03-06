---
title: TargetCLR | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: f9732480-287f-40f1-a4ff-b112e143b940
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 5f8ea5bd3f1ec16f6deeae8365cc90541bc8b958
ms.sourcegitcommit: 046a9adc5fa6d6d05157204f5fd1a291d89760b7
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2018
---
# <a name="targetclr"></a>TargetCLR
**TargetCLR** オプションでは、アプリケーションに複数のバージョンの CLR (共通言語ランタイム) が読み込まれている場合に、プロファイリングを行う CLR のバージョンを指定します。  
  
 既定では、[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] プロファイル ツールはアプリケーションによって読み込まれる最初の CLR のバージョンを対象とします。  
  
## <a name="syntax"></a>構文  
  
```cmd  
VSPerfCmd.exe {/Launch:AppName | /Attach:PID} /TargetCLR[:ClrVersion] [Options]   
```  
  
#### <a name="parameters"></a>パラメーター  
 `ClrVersion`  
 CLR のバージョン番号。 **vN.N.NNNNN** のバージョン形式を使用します。  
  
## <a name="required-options"></a>必須オプション  
 **TargetCLR** オプションは、**Launch** オプションまたは **Attach** オプションと共に指定する場合にのみ使用できます。  
  
 **Launch:** `AppName`  
 指定したアプリケーションを起動し、プロファイリングを開始します。  
  
 **Attach:** `PID`  
 指定したプロセスのプロファイリングを開始します。  
  
## <a name="example"></a>例  
 この例では、TargetCLR オプションを使用して、CLR バージョン 4.0.11003 がプロファイリングされることを確認します。  
  
```cmd  
VSPerfCmd.exe /Start:Sample /Output:TestApp.exe.vsp  
VSPerfCmd.exe /Launch:TestApp.exe /TargetCLR:v4.0.11003  
```