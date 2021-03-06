---
ms.topic: include
ms.openlocfilehash: 30d3f9da291feb52674937d4b2f1b86f3efd0386
ms.sourcegitcommit: 928885ace538bef5b25961358d4f166d648f196a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2018
---
ここまでは、アプリケーションを扱う唯一の開発者であるかのようにアプリケーションのコードを実行しました。 このセクションでは、Connected Environment がチーム開発をどのように効率化するかについて説明します。
* 開発者チームが同じ開発環境で作業できるようにします。
* 各開発者が他の開発者の邪魔してしまうことを心配せずに、隔離された状態でコードを反復処理できるようにします。
* 依存関係のシミュレーションやモックの作成を行わずに、コードのコミットの前に、コードをエンド ツー エンドでテストします。

## <a name="challenges-with-developing-microservices"></a>マイクロサービスの開発に伴う課題
現時点では、このサンプル アプリケーションはそれほど複雑ではありません。 しかしながら、実際の開発では、サービスがさらに追加され開発チームが拡大すると、すぐに課題が生じます。

他の多くのサービスと対話するサービスで作業するご自分の姿を想像してみてください。

1. 開発のためにすべてをローカルで実行するのは非現実的になる可能性があります。 開発用コンピューターには、アプリ全体を実行するのに十分なリソースがないこともあります。 また、ご利用のアプリに、パブリックに到達可能である必要があるエンドポイントがある場合もあります (アプリで SaaS アプリからの webhook に応答するなど)。
1. 依存するサービスのみの実行を試みることはできますが、その場合、依存関係の完全なクロージャー (依存関係の依存関係など) を確認する必要があります。 あるいは、依存関係を扱っていなかったため、依存関係を構築し、実行する方法が簡単にはわからないという問題です。
1. 開発者には、サービスの依存関係の多くをシミュレートしたり、モックを作成したりする方法をとる者もいます。 この方法でうまくいくこともありますが、開発時にすぐにモックの管理に苦労することになる可能性があります。 また、開発環境と運用環境が非常に異なって見えるようになり、バグが知らない間に入り込む可能性もあります。
1. その結果、あらゆる種類のエンドツーエンド テストが困難になります。 実際には、統合テストはコミット後にのみ行われます。つまり、問題は開発サイクルの後半に発生します。

![](../media/microservices-challenges.png)


## <a name="work-in-a-shared-development-environment"></a>共有開発環境で作業する
Connected Environment を使用すれば、Azure で*共有* 開発環境を設定することができます。 各開発者はアプリケーションの自分の担当部分にのみに集中できます。自分のシナリオが依存する他のすべてのサービスとクラウド リソースが既に含まれている環境で*事前コミット コード*を繰り返し開発できます。 依存関係は常に最新の状態になります。開発者は運用環境を反映した方法で作業します。

## <a name="work-in-your-own-space"></a>自分のスペースで作業する
サービスのコードを開発するときに、まだチェックインの段階でなければ、多くの場合、コードは良好な状態ではありません。 それでも、繰り返し調整し、テストし、ソリューションを試します。 Connected Environment では、**スペース**という概念を導入しています。このスペースにより、チーム メンバーの邪魔をすることを心配せずに、隔離された状態で作業できます。

> [!Note]
> 続行する前に、両方のサービスの VS Code ウィンドウをすべて閉じ、サービスのそれぞれのルート フォルダーで `vsce up -d` を実行します。 (これはプレビュー限定です。)

それでは、サービスが現在実行されている箇所を詳しく見てみましょう。 `vsce list` コマンドを実行します。次のような出力が表示されます。

```
Name         Space     Chart              Ports   Updated     Access Points
-----------  --------  -----------------  ------  ----------  -------------------------
mywebapi     mainline  mywebapi-0.1.0     80/TCP  2m ago     <not attached>
webfrontend  mainline  webfrontend-0.1.0  80/TCP  1m ago     https://webfrontend-contosodev.vsce.io
```

[Space] 列には、`mainline` という名前のスペースで両方のサービスが実行されていることが表示されます。 パブリック URL を開き、Web アプリに移動するすべてのユーザーは、前に記述した、両方のサービスを介して実行されるコード パスを呼び出します。 `mywebapi` の開発を続けるとします。 開発環境を利用している他の開発者の邪魔にならない方法はあるでしょうか。 それには、自分だけのスペースを設定します。

## <a name="create-a-space"></a>スペースを作成する
`mainline` 以外のスペースで独自のバージョンの `mywebapi` を実行するには、独自のスペースを作成します。
``` 
vsce space create --name scott
```

上記の例では、私が作業しているスペースであることを同僚が確認できるように、新しいスペースに私の名前を付けましたが、これにはどのような名前を付けてもかまいません。'sprint4' や 'demo' など、内容に合わせて自由に命名できます。 

`vsce space list` コマンドを実行すると、開発環境にあるすべてのスペースが一覧表示されます。 現在選択されているスペースの隣にアスタリスク (*) が表示されます。 今回は、スペースの作成時に 'scott' という名前が自動的に選択されました。 `vsce space select` コマンドを利用し、別のスペースをいつでも選択できます。
