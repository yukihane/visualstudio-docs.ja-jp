---
title: Visual Studio オフライン インストールに必要な証明書をインストールする | Microsoft Docs
description: Visual Studio オフライン インストール用の証明書をインストールする方法を説明します。
ms.date: 08/30/2017
ms.technology: vs-acquisition
ms.prod: visual-studio-dev15
ms.topic: conceptual
helpviewer_keywords:
- '{{PLACEHOLDER}}'
- '{{PLACEHOLDER}}'
ms.assetid: 9750A3F3-89C7-4A8F-BA75-B0B06BD772C2
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 70d6b30f3b264e5bdffc5f9c0f36ba17e67e8a5d
ms.sourcegitcommit: 4c0bc21d2ce2d8e6c9d3b149a7d95f0b4d5b3f85
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/20/2018
---
# <a name="install-certificates-required-for-visual-studio-offline-installation"></a>Visual Studio オフライン インストールに必要な証明書をインストールする

Visual Studio は、本来、インターネットに接続されているコンピューターからインストールするように設計されています。多くのコンポーネントが定期的に更新されるためです。 しかしながら、いくつかの追加手順を踏めば、インターネットが利用できない環境で Visual Studio を展開できます。

Visual Studio セットアップ エンジンでは、信頼されているコンテンツのみがインストールされます。 そのためにセットアップ エンジンは、ダウンロードされるコンテンツの Authenticode 署名を確認し、すべてのコンテンツが信頼されていることをインストール前に検証します。 これにより、ダウンロード場所が侵害されていた場合に攻撃から環境の安全を維持します。 そのため、Visual Studio のセットアップでは、Microsoft 標準の複数のルート証明書と中間証明書がユーザーのコンピューターにインストールされて最新の状態になっている必要があります。 コンピューターが Windows Update で最新の状態に保たれている場合は、通常、署名証明書も最新の状態になっています。 コンピューターがインターネットに接続されている場合、インストールの間に、Visual Studio はファイルの署名の検証に必要な証明書を更新できます。 コンピューターがオフラインの場合は、別の方法で証明書を更新する必要があります。

## <a name="how-to-refresh-certificates-when-offline"></a>オフラインのときに証明書を更新する方法

オフライン環境で証明書をインストールまたは更新するには 3 つのオプションがあります。

### <a name="option-1---manually-install-certificates-from-a-layout-folder"></a>オプション 1 - レイアウト フォルダーから手動で証明書をインストールする

ネットワーク レイアウトを作成するときに、必要な証明書が Certificates フォルダーにダウンロードされます。 各証明書ファイルをダブルクリックし、証明書マネージャー ウィザードをクリックすることで証明書を手動でインストールできます。 パスワードを求められたら、空のままにしてください。

### <a name="option-2---distribute-trusted-root-certificates-in-an-enterprise-environment"></a>オプション 2 - エンタープライズ環境で信頼されたルート証明書を配布する

最新のルート証明書がないオフラインのコンピューターの場合、管理者が「[信頼されたルートおよび許可されない証明書を構成する](https://technet.microsoft.com/library/dn265983.aspx)」の指示に従って更新できます。

### <a name="option-3---install-certificates-as-part-of-a-scripted-deployment-of-visual-studio"></a>オプション 3 - Visual Studio のスクリプト化された展開の一部として証明書をインストールする

オフライン環境でクライアント ワークステーションへの Visual Studio の配置をスクリプトにしている場合は、以下の手順に従う必要があります。

1. [証明書マネージャー ツール](/dotnet/framework/tools/certmgr-exe-certificate-manager-tool) (certmgr.exe) をインストール共有 (たとえば \\server\share\vs2017) にコピーします。 certmgr.exe は Windows 自体には含まれませんが、[Windows SDK](https://developer.microsoft.com/windows/downloads/windows-10-sdk) の一部として利用できます。

2. 次のコマンドでバッチ ファイルを作成します。

   ```cmd
   certmgr.exe -add -c certificates\manifestSignCertificates.p12 -n "Microsoft Code Signing PCA 2011" -s -r LocalMachine CA

   certmgr.exe -add -c certificates\manifestSignCertificates.p12 -n "Microsoft Root Certificate Authority" -s -r LocalMachine root

   certmgr.exe -add -c certificates\manifestCounterSignCertificates.p12 -n "Microsoft Time-Stamp PCA 2010" -s -r LocalMachine CA

   certmgr.exe -add -c certificates\manifestCounterSignCertificates.p12 -n "Microsoft Root Certificate Authority" -s -r LocalMachine root

   certmgr.exe -add -c certificates\vs_installer_opc.SignCertificates.p12 -n "Microsoft Code Signing PCA" -s -r LocalMachine CA

   certmgr.exe -add -c certificates\vs_installer_opc.SignCertificates.p12 -n "Microsoft Root Certificate Authority" -s -r LocalMachine root
   ```

3. バッチ ファイルをクライアントに配置します。 このコマンドは、管理者特権のプロセスから実行する必要があります。

## <a name="what-are-the-certificates-files-in-the-certificates-folder"></a>Certificates フォルダー内の証明書ファイルの内容

このフォルダー内にある 3 つの .P12 ファイルのそれぞれに、中間証明書とルート証明書が含まれます。 Windows Update で最新の状態になっているほとんどのシステムでは、これらの証明書は既にインストールされています。

* **ManifestSignCertificates.p12** に含まれるもの:
    * 中間証明書: **Microsoft コード署名 PCA 2011**
        * 不要。 存在する場合、一部のシナリオでパフォーマンスが向上します。
    * ルート証明書: **Microsoft ルート証明機関 2011**
        * 最新の Windows 更新プログラムがインストールされていない Windows 7 Service Pack 1 システムで必要。
* **ManifestCounterSignCertificates.p12** に含まれるもの:
    * 中間証明書: **Microsoft タイムスタンプ PCA 2010**
        * 不要。 存在する場合、一部のシナリオでパフォーマンスが向上します。
    * ルート証明書: **Microsoft ルート証明機関 2010**
        * 最新の Windows 更新プログラムがインストールされていない Windows 7 Service Pack 1 システムで必要。
* **Vs_installer_opc.SignCertificates.p12** に含まれるもの:
    * 中間証明書: **Microsoft コード署名 PCA**
        * すべてのシステムに必要。 Windows Update からすべての更新プログラムが適用されているシステムにはこの証明書がない場合があることに注意してください。
    * ルート証明書: **Microsoft ルート証明機関**
        * 必須。 この証明書は、Windows 7 以降を実行するシステムに付属しています。

## <a name="why-are-the-certificates-from-the-certificates-folder-not-installed-automatically"></a>Certificates フォルダーから証明書が自動的にインストールされません。

署名がオンライン環境で検証されるとき、Windows API が利用されて証明書がシステムにダウンロードされ、追加されます。 このプロセスで、証明書が信頼できることと管理者設定で許可されることが確認されます。 ほとんどのオフライン環境では、この検証プロセスを実行できません。 証明書を手動でインストールすると、証明書が信頼できること、および組織のセキュリティ ポリシーを満たすことを確認できます。

## <a name="checking-if-certificates-are-already-installed"></a>証明書が既にインストールされているかどうかを確認する

以下の手順はインストール システムをチェックする方法の 1 つです。
1. **mmc.exe** を実行します。<br/>
  a.  [ファイル] をクリックし、**[スナップインの追加と削除]** を選択します。<br/>
  b.  **[証明書]** をダブルクリックし、**[コンピューター アカウント]** を選択して、**[次へ]** をクリックします。<br/>
  c. **[ローカル コンピューター]** を選択し、**[完了]** をクリックして、**[OK]** をクリックします。<br/>
  d. **[証明書 (ローカル コンピューター)]** を展開します。<br/>
  e. **[信頼されたルート証明機関]** を展開し、**[証明書]** を選択します。<br/>
    * この一覧で必要なルート証明書を確認します。<br/>

   f. **[中間証明機関]** を展開し、**[証明書]** を選択します。<br/>
    * この一覧で必要な中間証明書を確認します。<br/>

2. [ファイル] をクリックし、**[スナップインの追加と削除]** を選択します。<br/>
  a.  **[証明書]** をダブルクリックし、**[ユーザー アカウント]** を選択して、**[完了]**、**[OK]** の順にクリックします。<br/>
  b.  **[証明書 - 現在のユーザー]** を展開します。<br/>
  c. **[中間証明機関]** を展開し、**[証明書]** を選択します。<br/>
    * この一覧で必要な中間証明書を確認します。<br/>

証明書名が **[発行先]** 列にない場合は、インストールする必要があります。  中間証明書が **[現在のユーザー]** 中間証明書ストアのみにある場合、その中間証明書はログインしているユーザーだけが使用できます。 他のユーザー用にインストールが必要な場合があります。

## <a name="install-visual-studio"></a>Visual Studio のインストール

証明書をインストールしたら、「Visual Studio 2017 のネットワーク インストールを作成する」ページの「[ネットワーク インストールから展開する](create-a-network-installation-of-visual-studio.md#deploying-from-a-network-installation)」の指示に従うことで、Visual Studio の展開を続けることができます。

## <a name="get-support"></a>サポートを受ける

ときには、問題が発生してしまうことがあります。 Visual Studio のインストールが失敗した場合は、「[Troubleshooting Visual Studio 2017 installation and upgrade issues (Visual Studio 2017 のインストールとアップグレードの問題のトラブルシューティング)](troubleshooting-installation-issues.md)」ページをご覧ください。 トラブルシューティングの手順でも解決しない場合は、ライブ チャットでインストールの支援を依頼してください (英語のみ)。 詳細については、[Visual Studio のサポート ページ](https://www.visualstudio.com/vs/support/#talktous)をご覧ください。

他のいくつかのサポート オプションを次に示します。

* Visual Studio インストーラーおよび Visual Studio IDE の両方に表示される [[問題の報告]](../ide/how-to-report-a-problem-with-visual-studio-2017.md) ツールから、製品の問題を Microsoft に報告できます。
* [UserVoice](https://visualstudio.uservoice.com/forums/121579) で、製品に関する提案を投稿できます。
* [Visual Studio 開発者コミュニティ](https://developercommunity.visualstudio.com/)で製品の問題を追跡したり、回答を検索したりできます。
* [Gitter コミュニティの Visual Studio に関するスレッド](https://gitter.im/Microsoft/VisualStudio)で、Microsoft や他の Visual Studio 開発者と情報を交換することもできます。 (このオプションでは [GitHub](https://github.com/) アカウントが必要になります)。

## <a name="see-also"></a>関連項目

* [Visual Studio のインストール](install-visual-studio.md)
* [Visual Studio 管理者ガイド](visual-studio-administrator-guide.md)
* [コマンド ライン パラメーターを使用して Visual Studio をインストールする](use-command-line-parameters-to-install-visual-studio.md)
* [Visual Studio のワークロードとコンポーネント ID](workload-and-component-ids.md)
