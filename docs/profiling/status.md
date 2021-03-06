---
title: Status | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: ba656fa4-ef9d-4d8c-a3b6-739c3b5d23ae
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 4b1e39743b8e3e6602961dfec693d5dc92c0ee63
ms.sourcegitcommit: 046a9adc5fa6d6d05157204f5fd1a291d89760b7
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2018
---
# <a name="status"></a>Status
VSPerfCmd.exe の **Status** オプションでは、プロファイラーの状態、および現在プロファイルを実行中の任意のプロセスに関する情報を表示します。  
  
 コマンド ラインで指定するオプションは **Status** オプションのみにする必要があります。 状態を表示するには、VSPerfCmd.exe の **Start** オプションを使用してプロファイラーを初期化しておく必要があります。  
  
## <a name="syntax"></a>構文  
  
```cmd  
VSPerfCmd.exe /Status  
```  
  
#### <a name="parameters"></a>パラメーター  
 なし  
  
## <a name="remarks"></a>コメント  
 **Status** オプションでは、プロファイラーに関して、次の状態情報を表示します。  
  
 **出力ファイル名**  
 現在のプロファイラー データ ファイルのパスとファイル名。  
  
 **コレクション モード**  
 SAMPLE または TRACE  
  
 **最大プロセス**  
 同時にプロファイルできる最大プロセス数と、現在アクティブなプロセス数。  
  
 **最大スレッド**  
 同時にプロファイルできる最大スレッド数。  
  
 **バッファー数**  
 プロファイル データの書き込み専用のメモリ バッファー数。  
  
 **バッファー サイズ**  
 メモリ バッファーのサイズ (バイト単位)。  
  
 **Status** オプションでは、現在プロファイルされている各プロセスに関して、次の状態情報を表示します。  
  
 **Process**  
 プロファイルされているプロセスの名前。  
  
 **プロセス ID**  
 プロセスのシステム ID。  
  
 **Num スレッド**  
 現在実行中のスレッド数。  
  
 **開始/停止数**  
 このプロセスに対するデータ収集を制御するプライマリ内部プロファイラー カウント。 データを収集するには、このカウントが 1 である必要があります。 開始/停止数は、プロファイラー API、および VSPerfCmd オプションである **GlobalOn**、**GlobalOff**、**ProcessOn**、**ProcessOff**、**ThreadOn**、および **ThreadOff** によって操作できます。  
  
 **保留/再開数**  
 このプロセスに対するデータ収集を制御するセカンダリ内部プロファイラー カウント。 データを収集するには、このカウントが 0 以下である必要があります。 **保留/再開**数は、プロファイラー API によってのみ操作できます。  
  
 **監視するアクセス権を伴うユーザー**  
 プロファイラーにアクセスできるユーザーの名前を一覧表示します。 VSPerfCmd.exe の **Admin** オプションを使用して、追加ユーザーにアクセスを許可できます。  
  
## <a name="see-also"></a>参照  
 [VSPerfCmd](../profiling/vsperfcmd.md)   
 [スタンドアロン アプリケーションのプロファイリング](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [ASP.NET Web アプリケーションのプロファイリング](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [プロファイリング (サービスの)](../profiling/command-line-profiling-of-services.md)