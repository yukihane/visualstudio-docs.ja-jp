---
title: ツール ウィンドウにツールバーを追加する |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- tool windows, adding toolbars
- toolbars [Visual Studio], adding to tool windows
ms.assetid: 172f64b3-87f8-4292-9c1c-65bffa2b0970
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 47ff5f69ff559ea1c08d0ae9bdd7192a257c844e
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/16/2018
---
# <a name="adding-a-toolbar-to-a-tool-window"></a>ツール ウィンドウにツールバーを追加します。
このチュートリアルでは、ツール ウィンドウにツールバーを追加する方法を示します。  
  
 ツールバーは、水平または垂直方向のストリップをコマンドにバインドされているボタンを含むです。 ツール ウィンドウのツールバーの長さは、ツールバーのドッキング場所に応じて、ツール ウィンドウの高さまたは幅と同じでは常にします。  
  
 IDE でツールバーとは異なりツール ウィンドウのツールバー必要がありますドッキングありことはできません、移動やカスタマイズします。 場合は、VSPackage は、umanaged コードで記述された、のどの辺をツールバーをドッキングできます。  
  
 ツールバーを追加する方法の詳細については、次を参照してください。[ツールバーを追加する](../extensibility/adding-a-toolbar.md)です。  
  
## <a name="prerequisites"></a>必須コンポーネント  
 Visual Studio 2015 以降、ダウンロード センターから Visual Studio SDK をインストールすることはできません。 これは Visual Studio のセットアップにオプション機能として含まれるようになりました。 また、後から VS SDK をインストールすることもできます。 より詳細な情報については 、[Visual Studio SDK のインストール](../extensibility/installing-the-visual-studio-sdk.md) に関する記事を参照してください。  
  
## <a name="creating-a-toolbar-for-a-tool-window"></a>ツール ウィンドウのツールバーの作成  
  
1.  という名前の VSIX プロジェクトを作成する`TWToolbar`という名前の両方、メニュー コマンドを含む**TWTestCommand**という名前のツール ウィンドウと**TestToolWindow**です。 詳細については、次を参照してください。[メニュー コマンドを使用して、拡張機能の作成](../extensibility/creating-an-extension-with-a-menu-command.md)と[ツール ウィンドウで、拡張機能の作成](../extensibility/creating-an-extension-with-a-tool-window.md)です。 ツール ウィンドウのテンプレートを追加する前にコマンドの項目テンプレートを追加する必要があります。  
  
2.  TWTestCommandPackage.vsct で、[シンボル] セクションを探します。 GuidTWTestCommandPackageCmdSet をという名前の GuidSymbol ノードで次のように、ツールバーとツール バー グループを宣言します。  
  
    ```xml  
    <IDSymbol name="TWToolbar" value="0x1000" />  
    <IDSymbol name="TWToolbarGroup" value="0x1050" />  
    ```  
  
3.  上部にある、`Commands`セクションで、作成、`Menus`セクションです。 追加、`Menu`ツールバーを定義する要素。  
  
    ```xml  
    <Menus>  
        <Menu guid="guidTWTestCommandPackageCmdSet" id="TWToolbar" type="ToolWindowToolbar">  
            <CommandFlag>DefaultDocked</CommandFlag>  
            <Strings>  
                <ButtonText>Test Toolbar</ButtonText>  
                <CommandName>Test Toolbar</CommandName>  
            </Strings>  
        </Menu>  
    </Menus>  
    ```  
  
     ツールバーは、サブメニューのような入れ子にすることはできません。 そのため、親を割り当てるにはありません。 またがありません、優先順位を設定するため、ユーザーがツールバーを移動できます。 通常、ツールバーの初期配置が、プログラムで定義されているが、ユーザーが後続の変更は保持します。  
  
4.  グループ セクションでは、ツールバーのコマンドを格納するグループを定義します。  
  
    ```xml  
  
    <Group guid="guidTWTestCommandPackageCmdSet" id="TWToolbarGroup" priority="0x0000">  
        <Parent guid="guidTWTestCommandPackageCmdSet" id="TWToolbar" />  
    </Group>  
    ```  
  
5.  セクションでは、ボタン、ボタンの既存の要素の親をツールバーのグループに変更して、ツールバーが表示されますようにします。  
  
    ```xml  
    <Button guid="guidTWTestCommandPackageCmdSet" id="TWTestCommandId" priority="0x0100" type="Button">  
        <Parent guid="guidTWTestCommandPackageCmdSet" id="TWToolbarGroup" />  
        <Icon guid="guidImages" id="bmpPic1" />  
        <Strings>  
            <ButtonText>Invoke TWTestCommand</ButtonText>  
        </Strings>  
    </Button>  
    ```  
  
     既定では、ツールバーには、コマンドが存在しない場合に表示されません。  
  
     新しいツールバーは、ツール ウィンドウを自動的に追加されませんが、ため、ツールバーを明示的に追加する必要があります。 これについては、次のセクションで説明します。  
  
## <a name="adding-the-toolbar-to-the-tool-window"></a>ツール ウィンドウにツールバーを追加します。  
  
1.  TWTestCommandPackageGuids.cs では、次の行を追加します。  
  
    ```csharp  
    public const string guidTWTestCommandPackageCmdSet = "00000000-0000-0000-0000-0000";  // get the GUID from the .vsct file  
    public const int TWToolbar = 0x1000;  
    ```  
  
2.  TestToolWindow.cs で次のコードを追加ステートメントを使用します。  
  
    ```csharp  
    using System.ComponentModel.Design;  
    ```  
  
3.  TestToolWindow コンス トラクターでは、次の行を追加します。  
  
    ```csharp  
    this.ToolBar = new CommandID(new Guid(TWTestCommandPackageGuids.guidTWTestCommandPackageCmdSet), TWTestCommandPackageGuids.TWToolbar);  
    ```  
  
## <a name="testing-the-toolbar-in-the-tool-window"></a>ツール ウィンドウで、ツールバーのテスト  
  
1.  プロジェクトをビルドし、デバッグを開始します。 Visual Studio の実験用インスタンスが表示されます。  
  
2.  **ビュー/その他のウィンドウ** メニューのをクリックして**テスト ToolWindow**ツール ウィンドウを表示します。  
  
     上部のツールバーのような既定のアイコン) が、タイトルのすぐ下のツール ウィンドウの左に表示されます。  
  
3.  ツールバーで、メッセージを表示するアイコンをクリックして**TWTestCommandPackage 内 TWToolbar.TWTestCommand.MenuItemCallback()**です。  
  
## <a name="see-also"></a>関連項目  
 [ツール バーの追加](../extensibility/adding-a-toolbar.md)