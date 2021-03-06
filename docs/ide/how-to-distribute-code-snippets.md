---
title: '方法: コード スニペットを配布する'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- code snippets, distributing
ms.assetid: 5f717abd-e167-47ae-818c-6b0bae100ceb
author: gewarren
ms.author: gewarren
manager: douge
dev_langs:
- VB
ms.workload:
- multiple
ms.openlocfilehash: 1841dc30fce8e3799191ff9e2d91b94c7d8ac96b
ms.sourcegitcommit: fe5a72bc4c291500f0bf4d6e0778107eb8c905f5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
---
# <a name="how-to-distribute-code-snippets"></a>方法: コード スニペットを配布する

コード スニペットは友人に配布することができます。友人はコード スニペット マネージャーを使用して、そのスニペットを自分のコンピューターにインストールできます。 ただし、配布するスニペットが複数ある場合や、スニペットをより広範に配布する場合は、スニペット ファイルを Visual Studio 拡張機能に含めると、Visual Studio ユーザーはこれをインストールできます。

Visual Studio 拡張機能を作成するには、Visual Studio SDK をインストールする必要があります。 [Visual Studio のダウンロード](https://www.visualstudio.com/downloads/)で、Visual Studio のインストールと一致する VSSDK のバージョンを見つけます。

## <a name="set-up-the-extension"></a>拡張機能を設定する

この手順では、「[チュートリアル: コード スニペットを作成する](../ide/walkthrough-creating-a-code-snippet.md)」で作成したのと同じ Hello World コード スニペットを使います。 *.snippet* のテキストは用意されているため、前の手順に戻ってコード スニペットを作成する必要はありません。

1.  **TestSnippet** という新しい VSIX プロジェクトを作成します  (**[ファイル]** > **[新規作成]** > **[プロジェクト]** > **[Visual C#] (または [Visual Basic])** > **[拡張]**)。

2.  **TestSnippet** プロジェクトで新しい XML ファイルを追加し、*VBCodeSnippet.snippet* という名前を付けます。 内容を次のコードに置き換えます。

    ```xml
    <?xml version="1.0" encoding="utf-8"?>
    <CodeSnippets
        xmlns="http://schemas.microsoft.com/VisualStudio/2005/CodeSnippet">
      <CodeSnippet Format="1.0.0">
        <Header>
          <Title>Hello World VB</Title>
          <Shortcut>HelloWorld</Shortcut>
          <Description>Inserts code</Description>
          <Author>MSIT</Author>
          <SnippetTypes>
            <SnippetType>Expansion</SnippetType>
            <SnippetType>SurroundsWith</SnippetType>
          </SnippetTypes>
        </Header>
        <Snippet>
          <Code Language="VB">
            <![CDATA[Console.WriteLine("Hello, World!")]]>
          </Code>
        </Snippet>
      </CodeSnippet>
    </CodeSnippets>
    ```

### <a name="set-up-the-directory-structure"></a>ディレクトリ構造を設定する

1.  **ソリューション エクスプローラー**でプロジェクト ノードを選択し、フォルダーを追加します。その名前は、**コード スニペット マネージャー**でスニペットに付けるのと同じ名前にします。 ここでは、**HelloWorldVB** になります。

2.  *.snippet* ファイルを *HelloWorldVB* フォルダーに移動します。

3.  **ソリューション エクスプローラー**で *.snippet* ファイルを選び、**[プロパティ]** ウィンドウで **[ビルド アクション]** を **[コンテンツ]** に、**[出力ディレクトリにコピー]** を **[常にコピーする]** に、**[VSIX に含める]** を **[true]** に、それぞれ設定します。

### <a name="add-the-pkgdef-file"></a>.pkgdef ファイルを追加する

1.  *HelloWorldVB* フォルダーにテキスト ファイルを追加し、*HelloWorldVB.pkgdef* という名前を付けます。 このファイルは、レジストリにキーを追加するために使用します。 ここでは、新しいキーを以下に追加します。

     `HKCU\Software\Microsoft\VisualStudio\15.0\Languages\CodeExpansions\Basic`

2.  ファイルに次の行を追加します。

    ```txt
    // Visual Basic
    [$RootKey$\Languages\CodeExpansions\Basic\Paths]
    "HelloWorldVB"="$PackageFolder$"
    ```

    このキーを調べると、さまざまな言語を指定する方法が分かります。

3.  **ソリューション エクスプローラー**で *.pkgdef* ファイルを選び、**[プロパティ]** ウィンドウで **[ビルド アクション]** を **[コンテンツ]** に、**[出力ディレクトリにコピー]** を **[常にコピーする]** に、**[VSIX に含める]** を **[true]** に、それぞれ設定します。

4.  VSIX マニフェストに *.pkgdef* ファイルを資産として追加します。 **source.extension.vsixmanifest** ファイルで、*[資産]* タブに移動し、**[新規]** をクリックします。

5.  **[新しい資産の追加]** ダイアログ ボックスで、**[型]** を **Microsoft.VisualStudio.VsPackage** に、**[ソース]** を **[ファイル システム上のファイル]** に、**[パス]** を **[HelloWorldVB.pkgdef]** (ドロップダウン リストに表示される) に、それぞれ設定します。

### <a name="test-the-snippet"></a>スニペットをテストする

1.  これで、コード スニペットが Visual Studio の実験用インスタンスで動作することを確認できるようになりました。 実験用インスタンスとは、コードの記述に使用する Visual Studio とは異なる、Visual Studio のもう 1 つのコピーです。 これを使用することにより、開発環境に影響を与えずに、拡張機能を処理することができます。

2.  プロジェクトをビルドし、デバッグを開始します。 Visual Studio の 2 番目のインスタンスが表示されます。

3.  実験用インスタンスで、**[ツール]、[コード スニペット マネージャー]** の順に移動し、**[言語]** を **[基本]** に設定します。 フォルダーの 1 つとして *HelloWorldVB* が表示されるはずです。そのフォルダーを展開すると *HelloWorldVB* スニペットを表示できます。

4.  スニペットをテストします。 実験用インスタンスで、Visual Basic プロジェクトを開き、コード ファイルのいずれかを開きます。 コードの任意の場所にカーソルを置いて右クリックし、コンテキスト メニューで **[スニペットの挿入]** を選びます。

5.  フォルダーの 1 つとして *HelloWorldVB* が表示されるはずです。 これをダブルクリックします。 **[スニペットの挿入: HelloWorldVB >]** ポップアップが表示されます。ここに **[HelloWorldVB]** ドロップダウン リストが表示されます。 **[HelloWorldVB]** ドロップダウン リストをクリックします。 次の行がファイルに追加されます。

    ```vb
    Console.WriteLine("Hello, World!")
    ```

## <a name="see-also"></a>関連項目

- [コード スニペット](../ide/code-snippets.md)