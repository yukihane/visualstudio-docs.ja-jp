---
title: "R Tools for Visual Studio のインストール | Microsoft Docs"
ms.custom: 
ms.date: 6/29/2017
ms.prod: visual-studio-dev15
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-r
ms.tgt_pltfrm: 
ms.devlang: r
ms.topic: article
ms.assetid: 3ff60292-1b88-4ee9-b2b2-edd957f1a519
caps.latest.revision: 1
author: kraigb
ms.author: kraigb
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 712cc780388acc5e373f71d51fc8f1f42adb5bed
ms.openlocfilehash: 8e35c82a5f8583a609e9fccbacb0b27d9c3eac8f
ms.contentlocale: ja-jp
ms.lasthandoff: 07/12/2017

---

# <a name="how-to-install-r-tools-for-visual-studio"></a>R Tools for Visual Studio のインストール方法

このトピックの内容

- [サポートされている Visual Studio のバージョン](#supported-versions-of-visual-studio)
- [Visual Studio 2017 での RTVS のインストール](#installing-rtvs-in-visual-studio-2017)
- [Visual Studio 2015 での RTVS のインストール](#installing-rtvs-in-visual-studio-2015)
- [オフライン インストール](#offline-installation-of-visual-studio-and-rtvs)

> [!Note]
> R Tools をインストールすると、「[オプション](options.md#data-scientist-layout)」トピックで説明したように、最適化されたデータ科学レイアウト用に Visual Studio を構成できます。

## <a name="supported-versions-of-visual-studio"></a>サポートされている Visual Studio のバージョン

R Tools for Visual Studio (RTVS) は、[Visual Studio 2017](https://www.visualstudio.com/downloads/) および [Visual Studio 2015 Update 3 (以降)](http://go.microsoft.com/fwlink/?LinkId=691129) 両方の Community、Professional、および Enterprise の各エディションでサポートされています (直接ダウンロード)。 

Visual Studio Test Professional や SQL Server Management Studio などの製品に含まれている Visual Studio Shell しかない場合、RTVS はインストールされません。 Visual Studio Shell には RTVS に必要なコンポーネントがありません。


## <a name="installing-rtvs-in-visual-studio-2017"></a>Visual Studio 2017 での RTVS のインストール

1. Visual Studio インストーラーを実行します。 (Visual Studio がまだインストールされていない場合は、「[ダウンロード](https://www.visualstudio.com/downloads/)」を参照してください)。Windows 7 の場合、Visual Studio バージョン *15.2 ビルド 26430.12* 以降を表示するには、インストーラーを更新する必要があります。

2. [**データ サイエンスと分析のアプリケーション**] ワークロードを選択します。

    ![VS2017 の [データ サイエンスと分析のアプリケーション] ワークロード](media/installation-data-science-workload.png)

3. 同じワークロード名で、右側にその他のオプションを設定します。 既定では、このワークロードには F# と Python のサポートが含まれていることに注意してください。 R の場合、少なくとも **[R 言語サポート]**、**[R 開発ツールのランタイム サポート]**、および **[Microsoft R クライアント]** を選択する必要があります。

RTVS は次の場所にインストールされます。 `%ProgramFiles(x86)%\Microsoft Visual Studio\<version>\<edition>Common7\IDE\Extensions\Microsoft\R Tools for Visual Studio` ここで、`<version>` は、通常 `2017` で、`<edition>` は `Community`、`Professional`、または `Enterprise` です。

## <a name="installing-rtvs-in-visual-studio-2015"></a>Visual Studio 2015 での RTVS のインストール

Visual Studio 2015 では、R インタープリターと R Tools を個別にインストールする必要があります。

### <a name="install-an-r-interpreter"></a>R インタープリターをインストールする

RTVS には、次の 1 つ以上のソースから R 3.2.1 以降のバージョンの 64 ビット版のインストールが必要です。

* [Microsoft R Open](https://mran.microsoft.com/download/)
* [Microsoft R Client](https://msdn.microsoft.com/microsoft-r/r-client-get-started)
* [CRAN R](https://cran.r-project.org/bin/windows/base/)

Microsoft R Open と CRAN R はどちらも複数の side-by-side バージョンを許可しています。 ただし、Microsoft R Client は、1 つのバージョンのみをサポートし、インストールされている最新バージョンを常に使用します。

### <a name="install-the-r-tools"></a>R Tools のインストール

[https://aka.ms/rtvs-current](https://aka.ms/rtvs-current) から最新の RTVS をダウンロードします。 RTVS は Visual Studio の適切なバージョンを確認し、R インタープリターがまだインストールされていない場合は、インストールの支援も行います。

RTVS は次の場所にインストールされます。`%ProgramFiles(x86)%\Microsoft Visual Studio 14\Common7\IDE\Extensions\Microsoft\R Tools for Visual Studio`

## <a name="offline-installation-of-visual-studio-and-rtvs"></a>Visual Studio と RTVS のオフライン インストール

オフライン インストールは、インターネットに接続されていないコンピューターに適しています。

1. 次の指示に従って、お使いの Visual Studio のバージョンのオフライン インストーラーを作成します。 

    - [Visual Studio 2017](../install/create-an-offline-installation-of-visual-studio.md)
    - [Visual Studio 2015](https://msdn.microsoft.com/library/mt706497.aspx)

1. オフラインの RTVS インストーラーは、[https://aka.ms/rtvs-current-zip](https://aka.ms/rtvs-current-zip) と [https://aka.ms/rtvs-remote-zip](https://aka.ms/rtvs-remote-zip) からダウンロードします。 

1. オフライン インストーラーから Visual Studio と RTVS をインストールします。

## <a name="see-also"></a>関連項目

- [R の概要](getting-started-with-r.md)
- [R Tools のサンプル プロジェクト](getting-started-samples.md)
- [ヘルプ情報の入手](getting-started-help.md)
- [オプションの設定](options.md)
