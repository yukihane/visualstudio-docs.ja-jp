---
title: コード マップの参照および再配置
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.progression.dgmlgraph.layouthelp
- vs.progression.graphdocument
- vs.progression.dgmlgraph.message.notUlt.noexpandgroup
- vs.progression.colorsetpicker
- vs.progression.iconsetpicker
helpviewer_keywords:
- Visual Studio Ultimate, dependency graphs
- code visualization [Visual Studio ALM]
- graph documents, browsing
- Visual Studio ALM, dependency graphs
- code visualization
- Visual Studio ALM, graph documents
- Visual Studio Ultimate, graph documents
- dependency graphs, browsing
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.technology: vs-ide-modeling
ms.openlocfilehash: b88a74b3b3d943b7a063bd61fff99aee9cb25cff
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/26/2018
---
# <a name="browse-and-rearrange-code-maps"></a>コード マップの参照および再配置
コード マップ上のアイテムを再配置して、読みやすさとパフォーマンスを向上させます。

 ソリューション内の基本コードに影響を与えずに、コード マップをカスタマイズすることができます。 この機能は、重要なコード要素に重点を置きたいときや、コードに関するアイデアをやりとりするときに便利です。 たとえば、興味のある領域を強調表示するために、マップ上のコード要素を選択してフィルター処理すること、コード要素とリンクのスタイルを変更すること、コード要素を非表示または削除すること、プロパティ、カテゴリ、またはグループを使用してコード要素を整理することができます。

 **必要条件**

-   コード マップを作成するには、Visual Studio Enterprise が必要です。

-   Visual Studio Professional でコード マップを表示して、制限付きでコード マップを編集することができます。

##  <a name="ManageLargeGraphs"></a> コード マップを使用開始します。
 コード マップを作成 (を参照してください[ソリューション間の依存関係をマップする](../modeling/map-dependencies-across-your-solutions.md)詳細)。 マップを生成する [完了] をクリックするまで待機したくない場合、**キャンセル**生成処理を停止するには、いつでもリンクします。 ただし、この操作を実行した場合、従属関係とリンクの詳細をすべて確認することはできません。

 マップを生成した後、コードの確認に関する以下のヒントを実行します。

-   コード内の自然な依存関係クラスターを確認します。 マップ ツールバーで、次のように選択します。**レイアウト**、**クイック クラスター**![クイック クラスター ボタンのグラフ ツールバーを](../modeling/media/quickclustersicon.gif "QuickClustersIcon")です。 参照してください[レイアウトを変更するマップ](#Selecting)です。

     ![依存関係グラフ&#45;クイック クラスター レイアウト](../modeling/media/dependencygraph_quickclusters.png "DependencyGraph_QuickClusters")

-   関連するノードをグループ化することで、マップをさらに小さい領域に整理します。 これらのグループを折りたたみ、グループ間の依存関係のみが示されるようにします。これは、自動的に表示されます。 参照してください[グループ ノード](#OrganizeGroups)です。

-   フィルターを使ってマップを簡略化し、興味のある種類のノードやリンクだけに注目できるようにします。 参照してください[ノードおよびリンクのフィルター](#FilterNodes)です。

-   大きなマップのパフォーマンスを最大にします。 参照してください[ソリューション間の依存関係をマップする](../modeling/map-dependencies-across-your-solutions.md)詳細についてはします。たとえば、有効にする**ビルドのスキップ**マップのツールバー、マップの項目を更新するときに、Visual Studio では、ソリューションをリビルドしないようにします。

##  <a name="Selecting"></a> マップのレイアウトを変更します。

|**目的**|**次の手順を実行します。**|
|------------|-----------------------------|
|グラフ全体の依存関係のフローを特定の方向に配置します。 これは、コードのアーキテクチャ レイヤーを確認するのに役立ちます。|マップ ツールバーで、次のように選択します。**レイアウト**、をクリックします。<br /><br /> -   **上下に向かってから**![上下 グラフ ボタンから](../modeling/media/topbottomgraphbutton.gif "TopBottomGraphButton")<br />-   **下から上へ**![下上 グラフ ボタンから](../modeling/media/bottomtopgraphbutton.gif "BottomTopGraphButton")<br />-   **左右からに向かって**![左右のレイアウト ボタンから](../modeling/media/leftrightgraphbutton.gif "LeftRightGraphButton")<br />-   **右から左へ**![右左 グラフ ボタンから](../modeling/media/rightleftgraphbutton.gif "RightLeftGraphButton")|
|コード内のクラスターの自然な依存関係を確認します。最も依存度の高いノードはクラスターの中心付近にあり、最も依存度の低いノードはそれらのクラスターの外側にあります。|マップ ツールバーで、次のように選択します。**レイアウト**、し**クイック クラスター**![クイック クラスター ボタンのグラフ ツールバーを](../modeling/media/quickclustersicon.gif "QuickClustersIcon")です。|
|マップ上の 1 つまたは複数のノードを選択します。|ノードをクリックして選択します。 選択するか複数のノードの選択を解除、保持**CTRL**ながらをクリックします。<br /><br /> キーボードの使用: キーを押します**タブ**ピリオドで区切られたフォーカス四角形を移動したり、ノードをキーを押して、方向キーを使用して、または**領域**をオンにします。 キーを押して**CTRL** + **領域**を複数選択してまたはノードを選択解除します。|
|マップ上で特定のノードを移動します。|ノードをドラッグして移動します。 その他のノードとリンクの場所に、ノードをドラッグすると、押したを移動する、 **SHIFT**キー。<br /><br /> キーボードの使用: 保持**CTRL**方向キーを押します。|
|マップ上の他のノードやグループとは独立して、グループ内のレイアウトを変更します。|ノードを選択して、ショートカット メニューを開きます。 選択**レイアウト**とレイアウト スタイルを選択します。<br /><br /> または<br /><br /> ノードを選択して展開し、子ノードを表示します。 グループのポップアップ ツールバーを表示して再度開きますノード タイトルをクリックして、**グループのレイアウト スタイルを変更する**![依存関係グラフ&#45;グループ ツールバー&#45;レイアウト](../modeling/media/dependencygraph_grouptoolbar.gif "DependencyGraph_GroupToolbar")  ボックスの一覧です。 ツリー レイアウトを選択**クイック クラスター**、または**リスト ビュー** (するグループのコンテンツに整列一覧)。<br /><br /> 参照してください[グループ ノード](#OrganizeGroups)詳細についてはします。|
|マップ内のアクションを元に戻します。|キーを押して**CTRL** + **Z**か、Visual Studio を使用して**を元に戻す**コマンド。|

##  <a name="Explore"></a> マップを参照します。

|**目的**|**次の手順を実行します。**|
|------------|-----------------------------|
|マップをスキャンします。|マウスを使って、マップを任意の方向にドラッグします。<br /><br /> または<br /><br /> 保持**SHIFT**水平方向にスクロールするマウス ホイールを回転します。 保持**shift キーを押し** + **CTRL**水平方向にスクロールするマウス ホイールを回転します。|
|グラフを拡大または縮小します。|マウス ホイールを回します。<br /><br /> または<br /><br /> 使用して、**ズーム**コード マップ ツールバーでドロップダウン リスト。<br /><br /> または<br /><br /> キーボード ショートカットを使います。 拡大するにキーを押します**CTRL + SHIFT + です。** (ピリオド) を押します。 キーを押してズーム アウトするに**ctrl キーを押しながら shift キーを押しながら、** (コンマ)。|
|マウスを使って特定の領域をズームインします。|マウスの右ボタンをクリックしたまま、対象の領域を四角形で囲みます。|
|マップのサイズを変更してウィンドウに合わせます。|選択**に合わせて大きさ**から、**ズーム**コード マップ ツールバーのリスト。<br /><br /> または<br /><br /> クリックして、**に合わせてズーム**アイコン![マップ ツールバーのズーム アイコン](../modeling/media/almcodemapzoomicon.png "ALMCodeMapZoomIcon")コード マップ ツールバーでします。 キーボードの使用: キーを押して**CTRL +0** (ゼロ)。|
|マップ上のノードを名前で検索します。 **ヒント:** マップ上の項目についてのみ有効です。 ソリューション内ではなく、マップにアイテムを検索するでこれらを見つけ**ソリューション エクスプ ローラー**、し、マップにドラッグします。 (選択内容をドラッグするか、ツールバー、ソリューション エクスプ ローラー をクリックして**コード マップに表示**)。|1.選択、**検索**アイコン![マップ ツールバーで、検索アイコン](../modeling/media/almcodemapfindicon.png "ALMCodeMapFindIcon")コード マップ ツールバーで (キーボード: キーを押して**ctrl キーを押しながら F**) を表示するにはマップの右上隅の検索ボックス。<br />2.項目の名前とキーを押して入力**返す**か「拡大鏡」アイコンをクリックします。 マップの選択としたときに、検索条件に一致する最初の項目が表示されます。<br />3.検索をカスタマイズするには、ドロップダウン リストを開き、検索オプションを選択します。 オプションは、**次を検索**、**前を検索**、および**すべて選択**です。 次に、[検索] ボックスの横にある対応するボタンをクリックします。<br />     ![検索オプションのドロップダウン&#45;一覧を下](../modeling/media/almcodemapssearchdropdown.png "ALMCodeMapsSearchDropDown")<br />     または、キーボードを使用して: キーを押します**F3**を次に一致するノードを選択または**shift キーを押しながら F3**を前の一致するノードを選択します。<br />4.検索テキスト ボックスの下のアイコンをクリックして、検索語句の処理方法を指定するオプションのいずれかを選択します。<br />     ![一致オプションを検索](../modeling/media/almcodemapssearchmatchicons.png "ALMCodeMapsSearchMatchIcons")<br />     オプションは、左から順に、大文字と小文字を区別して検索、完全に一致する単語だけを検索、.NET の正規表現の構文を使用して検索、囲まれた項目と一致する項目が表示されるようにグループを自動的に展開する、となっています。 **重要:** それらのグループが既に展開している場合にのみ、折りたたまれたグループで一致を検索する検索ボックスを使用することができます。 これらの一致を検索し、親グループを自動的に展開するには、検索ボックスでこのオプションを選択します。|
|選択されていないノードをすべて選択します。|選択したノードのショートカット メニューを開きます。 選択**選択**、**反転**です。|
|選択したノードにリンクしている追加のノードを選択します。|選択したノードのショートカット メニューを開きます。 選択**選択**とこれらのいずれか。<br /><br /> -選択したノードに直接リンクしている追加のノードを選択するには**入力依存関係**です。<br />-選択したノードから直接リンクしているその他のノードを選択するには**出力依存関係**です。<br />- 直接リンク、選択したノードから他のノードを選択するには**両方**です。<br />-選択したノードとリンクしているすべてのノードを選択するには**接続しているサブグラフ**です。<br />-選択したノードのすべての子を選択するには**子**です。|

##  <a name="FilterNodes"></a> フィルター ノードおよびリンク

|**目的**|**次の手順を実行します。**|
|------------|-----------------------------|
|フィルター パネルを表示または非表示にします。|選択、**フィルター**コード マップ ツールバーでボタンをクリックします。 フィルター パネルは既定では、ソリューション エクスプローラー ウィンドウでタブ付きページとして表示されます。|
|マップに表示されるノードの種類をフィルター処理します。|設定またはに対応するチェック ボックスをオフに、**コード要素**フィルター ペインで、ボックスの一覧です。|
|マップに表示されるリンクの種類をフィルター処理します。|設定またはに対応するチェック ボックスをオフに、**リレーションシップ**フィルター ペインで、ボックスの一覧です。|
|マップ上のテスト プロジェクト ノードを表示または非表示にします。|オンまたはオフ、**テスト資産**のチェック ボックスを **[その他]** フィルター ペインで、ボックスの一覧です。|

 マップの [凡例] パネルに表示されるアイコンには、一覧の設定が反映されます。 または、[凡例] パネルを非表示にをクリックして、**凡例**コード マップ ツールバーでボタンをクリックします。

##  <a name="Inspect"></a> ノードおよびリンクを調べます
 コード マップには以下の種類のリンクが表示されます。

-   個々のリンクは、2 つのノード間の 1 つの関係を表します。

-   グループ間リンクは、異なるグループの 2 つのノード間の 1 つの関係を表します。

-   集約リンクは、2 つのグループ間で同じ方向を指すすべての関係を表します。

> [!TIP]
>  既定では、マップには選択したノードのグループ間リンクのみが表示されます。 グループ間の集約されたリンクを非表示には、この動作を変更する をクリックして**レイアウト**コードにツールバーをマップし、選択**詳細**、し**すべてのグループ間リンクの表示**または**すべてグループ間リンクを非表示に**です。 参照してください[非表示または表示するノードとリンク](#HidingShowing)詳細についてはします。

|**目的**|**次の手順を実行します。**|
|------------|-----------------------------|
|ノードまたはリンクの詳細を参照します。|マウス ポインターをノードまたはリンクの上に移動して、ツールヒントを表示します。<br /><br /> 集約されたリンクのツールヒントには、そのリンクが表す個々の依存関係が一覧表示されます。<br /><br /> または<br /><br /> ノードまたはリンクのショートカット メニューを開きます。 選択**編集**、**プロパティ**です。|
|グループの内容を表示または非表示にします。|、グループを展開するには、するにはノードのショートカット メニューを開き**グループ**、**展開**です。<br />     または<br />     マウス ポインターをノード上に移動して、シェブロン (下向き矢印) ボタンを表示します。 このボタンをクリックすると、グループが展開されます。 キーボードの使用: 選択したグループを閉じたりするには、キーを押して、 **PLUS**キー (**+**) または**マイナス**キー (**-**).<br />、グループを折りたたむには、するにはノードのショートカット メニューを開き**グループ**、**折りたたむ**です。<br />     または<br />     マウス ポインターをグループ上に移動して、シェブロン (上向き矢印) ボタンを表示します。 このボタンをクリックすると、グループが折りたたまれます。<br />すべてのグループを展開するを押して**CTRL** + **A**をすべてのノードを選択します。 マップのショートカット メニューを開き**グループ**、**展開**です。 **注:** このコマンドは使用に適さないマップまたはメモリの問題により生成されるすべてのグループを展開する場合は使用できません。 必要な詳細レベルにのみマップを展開することをお勧めします。<br />すべてのグループを折りたたむには、先には、ノードまたはマップのショートカット メニューを開きます。 選択**グループ**、**すべて折りたたむ**です。|
|名前空間、型、またはメンバーのコード定義を確認します。|ノードのショートカット メニューを開き**定義へ移動**です。<br /><br /> - または -<br /><br /> ノードをダブルクリックします。 展開したグループの場合、そのグループのヘッダーをダブルクリックします。<br /><br /> - または -<br /><br /> ノードとキーを押して選択**F12**です。<br /><br /> 例えば:<br /><br /> -1 つのクラスを含む名前空間、クラスのコード ファイルが開きそのクラスの定義が表示されます。 それ以外の場合に、**シンボルの検索結果**ウィンドウのコード ファイルの一覧が表示されます。 **注:** と Visual Basic の名前空間でこのタスクを実行すると、名前空間の分離コード ファイルは開きません。 この問題は、Visual Basic の名前空間が含まれる選択したノードのグループに対してこのタスクを実行するときにも発生します。 この問題を回避するには、手動で名前空間の背後にあるコード ファイルを参照するか、選択項目から名前空間のノードを除外します。<br />クラスまたは部分クラスでは、そのクラスのコード ファイルが開き、クラス定義が表示されます。<br />-メソッド、親クラスのコード ファイルが開き、メソッドの定義が表示されます。|
|集約リンクに参加する依存関係と項目を調べます。|興味し、選択内容のショートカット メニューを開き、リンクを選択します。 選択**寄与するリンクを表示する**または**寄与する新しいコード マップ上のリンクを表示する**です。<br /><br /> Visual Studio で、リンクの両端にグループが展開され、リンクに参加する項目と依存関係のみが表示されます。 **注:** 部分的なグループ内の項目間の依存関係を調べると、この動作を参照してください可能性があります。 <ul><li>これらのリンクがまだ存在する場合でも、あなたが検査に参加しない項目へのリンクは、マップから消失します。</li><li>部分的なグループの項目へのリンクを調べ、後で同じ項目への別のリンクを調べるとします。 この 2 番目の調査の際に、対象となる部分的なグループには、最初の調査の項目のみが表示されます。 リンクと最初の調査に参加しませんでしたが、2 番目の調査に参加する対象のアイテムは表示されません。</li></ul> グループから消失したアイテムを表示するには、次のように選択します**子の再フェッチ**![子の再フェッチ アイコン](../modeling/media/dependencygraph_deletednodesicon.png "DependencyGraph_DeletedNodesIcon") (ことを示しますのすべてのメンバー、。グループ マップに表示)。 試すこともできます、操作を元に戻す (キーボード: キーを押して**CTRL + Z**) し、新しいマップへの依存関係を確認します。|
|異なるグループの複数ノード間の依存関係を調べます。|グループのすべての子が表示されるように、グループを展開します。 目的のすべてのノード (子を含む) を選択します。 マップに、選択したノード間のグループ間リンクが表示されます。<br /><br /> グループ内のすべてのノードを選択する押し**SHIFT**とそのグループを囲む四角形を描画するときにマウスの左ボタンです。 マップ上のすべてのノードを選択するキーを押して**CTRL**+**A**です。 **ヒント:** 常に、グループ間リンクを表示するには、選択**レイアウト**、マップ ツールバーで、**詳細**、**すべてのグループ間リンクの表示**です。|
|ノードまたはリンクの参照先の項目を確認する。|ノードのショートカット メニューを開き**すべての参照の検索**です。 **注:** される場合にのみ適用されるこの、`Reference`ノードまたはリンクの属性が設定マップの .dgml ファイルにします。 ノードまたはリンクからアイテムへの参照を追加するを参照してください。 [DGML ファイルを編集してカスタマイズ コードがマップ](../modeling/customize-code-maps-by-editing-the-dgml-files.md)です。|

##  <a name="HidingShowing"></a> ノードおよびリンクを表示または非表示
 ノードを非表示にすると、そのノードはレイアウト アルゴリズムに加わらないままになります。 既定では、グループ間リンクは非表示です。 グループ間リンクは、グループにまたがってノードを接続する個々のリンクです。 グループを折りたたむと、すべてのグループ間リンクが、グループ間の単一リンクにまとめられます。 グループを展開し、グループ内のノードを選択すると、グループ間リンクが表示されて、そのグループ内の依存関係が示されます。

> [!CAUTION]
>  Visual Studio Enterprise で生成したマップを、Visual Studio Professional を使用するユーザーと共有する前に、他のユーザーが表示できるようにするノードやグループ間リンクを再表示しておく必要があります。 そうしない場合、これらのユーザーはそれらの項目を再表示できなくなります。

### <a name="to-hide-or-show-nodes"></a>ノードの表示/非表示を切り替えるには

|**目的**|**次の手順を実行します。**|
|------------|-----------------------------|
|選択したノードを非表示にします。|1.非表示にするノードを選択します。<br />2.選択したノードまたはマップのショートカット メニューを開きます。 選択**選択**、**選択されている非表示**です。|
|選択されていないノードを非表示にします。|1.表示したままにしておくノードを選択します。<br />2.選択したノードまたはマップのショートカット メニューを開きます。 選択**選択**、**非表示の選択を解除**です。|
|非表示のノードを表示します。|、グループ内のすべての隠しノードを表示するにはまず、グループが展開を確認します。 ショートカット メニューを開き**選択**、**子の再表示**です。<br />     または<br />     クリックして、**子の再表示**![子の再表示アイコン](../modeling/media/dependencygraph_filtericon_hiddennodes.gif "DependencyGraph_FilterIcon_HiddenNodes") (これは、表示される場合にのみ、グループの左上隅のアイコン非表示の子ノード)。<br />、すべての隠しノードを表示するにはマップまたはノードのショートカット メニューを開き**選択**、**すべて再表示**です。|

### <a name="to-hide-or-show-links"></a>リンクの表示/非表示を切り替えるには

|**目的**|**マップ、ツールバーのレイアウトをクリックして、詳細**|
|------------|----------------------------------------------------------------------|
|グループ間リンクを常時表示します。|**すべてのグループ間リンクを表示する**です。 これにより、グループ間の集約されたリンクは非表示になります。|
|グループ間リンクを常時非表示にします。|**すべてのグループ間リンクを非表示にします。**|
|選択したノードのグループ間リンクのみを表示します。|**選択したノードでのグループ間リンクを表示します。**|
|すべてのリンクを非表示にします。|**すべてのリンクを非表示に**です。 リンクを再び表示するには、上記のオプションのいずれかを選択します。|

##  <a name="OrganizeGroups"></a> グループ ノード

|**目的**|**次の手順を実行します。**|
|------------|-----------------------------|
|コンテナー ノードをグループ ノードまたはリーフ ノードとして表示します。|リーフ ノードとコンテナー ノードを表示する: ノードを選択して、ショートカット メニューを開き、選択すると、および選択**グループ**、**に変換するリーフ**です。<br /><br /> グループ ノードとコンテナー ノードを表示する: ノードを選択して、ショートカット メニューを開き、選択すると、および選択**グループ**、**のグループへの変換**です。|
|グループ内のレイアウトを変更します。|グループの選択で、ショートカット メニューを開き、**レイアウト**、レイアウト スタイルを選択するとします。<br /><br /> または<br /><br /> 1.グループを選択し、そのグループが展開されているかどうかを確認します。<br />2.グループ ヘッダーをもう一度クリックすると、グループ ツールバーが表示されます。<br />     ![依存関係グラフ&#45;グループ ツールバー](../modeling/media/dependencygraph_group.png "DependencyGraph_Group")<br />3.開く、**グループのレイアウト スタイルを変更する**リスト![依存関係グラフ&#45;グループ ツールバー&#45;レイアウト](../modeling/media/dependencygraph_grouptoolbar.gif "DependencyGraph_GroupToolbar")を選択し、レイアウト スタイルが必要です。<br /><br /> **リスト ビュー**リストに、グループのメンバーを並べ替えます。 **既定のグラフ**マップの既定のレイアウトにグループのレイアウトをリセットします。 その他のオプションでは、次を参照してください。[レイアウトを変更するマップ](#Selecting)です。|
|ノードをグループに追加します。|ノードをグループにドラッグします。<br /><br /> ノードをドラッグするときに、Visual Studio では、ノードを移動していることを示すインジケーターが表示されます。<br /><br /> ノードをグループ外にドラッグすることもできます。|
|ノードをグループ ノード以外に追加します。|ノードを目的のノードにドラッグします。 ノードをグループに追加することで、ターゲット ノードをグループに変換することもできます。|
|選択したノードをグループ化します。|1.グループ化するノードを選択します。 選択した最後のノードの上に、ポップアップ ツールバーが表示されます。<br />     ![依存関係のグラフ ツールバー](../modeling/media/depedencygraph_toolbar.png "DepedencyGraph_Toolbar")<br />2.ツールバーで、4 つ目のアイコンを選択**、選択したノードをグループ化**(ノードを展開してある場合は 4 つのアイコンではなく 5)。 キーを押して、新しいグループの名前を入力**返す**です。<br />     または<br />     グループ化するノードを選択して、選択した項目のショートカット メニューを開きます。 選択**グループ**、**親グループの追加**、キーを押して、新しいグループの名前を入力**返す**です。<br /><br /> グループ名は変更できます。 グループのショートカット メニューを開き**編集**、**プロパティ**を Visual Studio プロパティ ウィンドウを開きます。 **ラベル**プロパティ、必要に応じてグループの名前を変更します。|
|グループを削除します。|削除する対象の 1 つまたは複数のグループを選択します。 選択内容のショートカット メニューを開き**グループ**、**グループの削除**です。|
|親グループからノードを削除します。|移動するノードを選択します。 選択内容のショートカット メニューを開き**グループ**、**親から削除**です。 これにより、祖父母グループまでのノード、または祖父母グループがない場合はグループの外側までのノードが削除されます。<br /><br /> または<br /><br /> ノードを選択し、グループからドラッグして外します。|

##  <a name="AddRemoveNodesLinks"></a> 追加、削除、またはノード、リンク、およびコメントの名前を変更
 マップに表示される項目の数を増減させることで、マップをドリル ダウンしたり単純化したりすることができます。 また、アイテムの名前を変更したり、項目にコメントを追加することもできます。

> [!CAUTION]
>  Visual Studio Ultimate を使用して作成したマップを、Visual Studio Professional を使用するユーザーと共有する場合、他のユーザーが表示できるようにするノードは、前もってマップに表示可能に設定しておく必要があります。 そうしない場合、これらのユーザーは削除されたコード要素を取得できなくなります。

### <a name="add-a-node-for-a-code-element"></a>コード要素に対するノードの追加

|**目的**|**次の手順を実行します。**|
|------------|-----------------------------|
|現在のマウス ポインターの位置に、新しいジェネリック ノードを追加します。|1.マウス ポインターを移動、場所にマップのキーを押して、新しいコード要素を配置する**挿入**です。<br />     または<br />     マップのショートカット メニューを開き**編集**、**追加**、**汎用ノード**です。<br />2.キーを押して、新しいノードの名前を入力**返す**です。|
|現在のマウス ポインターの位置に、特定の種類のコード要素ノードを追加します。|1.新しいコード要素を配置する、マップ上の場所にマウス ポインターを移動して、マップのショートカット メニューを開きます。<br />2.選択**編集**、**追加**、ノードの種類を選択します。<br />3.キーを押して、新しいノードの名前を入力**返す**です。|
|ジェネリック型または特定の型のコード要素ノードをグループに追加します。|1.グループ ノードを選択して、ショートカット メニューを開きます。<br />2.選択**編集**、**追加**、ノードの種類を選択します。<br />3.キーを押して、新しいノードの名前を入力**返す**です。|
|既存のノードと同じ種類のノードを追加し、既存のノードからリンクを追加します。|1.コード要素を選択します。 その上にポップアップ ツールバーが表示されます。<br />     ![依存関係のグラフ ツールバー](../modeling/media/depedencygraph_toolbar.png "DepedencyGraph_Toolbar")<br />2.ツールバーで、2 番目のアイコンを選択**このノードと同じカテゴリのノードを作成し、新しいリンクを追加して**です。<br />3.新しいコード要素を配置するマップ上の場所を選択して、マウスの左ボタンをクリックします。<br />4.キーを押して、新しいノードの名前を入力**返す**です。|
|フォーカスがある既存のコード要素からリンクされている、新しいジェネリック ノードを追加します。|1.キーボードを使用して、キーを押して**タブ**コード要素からのリンクにフォーカスがある、(ピリオドで区切られた四角形) までです。<br />2.キーを押して**Alt**+**挿入**です。<br />3.キーを押して、新しいノードの名前を入力**返す**です。|
|フォーカスのある既存のコード要素からリンクされている、新しいジェネリック ノードを追加します。|1.キーボードを使用して、キーを押して**タブ**コード要素へのリンクにフォーカスがある、(ピリオドで区切られた四角形) までです。<br />2.キーを押して**Alt**+**Shift**+**挿入**です。<br />3.キーを押して、新しいノードの名前を入力**返す**です。|

|**コード要素を追加するには**|**次の手順を実行します。**|
|----------------------------------|-----------------------------|
|ソリューション内のコード要素。|1.コード要素を検索**ソリューション エクスプ ローラー**です。 使用して、**ソリューション エクスプ ローラー**検索ボックスまたは、ソリューションを参照します。 **ヒント:** 型またはメンバーに依存しているコード要素を検索するには、型またはのメンバーのショートカット メニューを開き**ソリューション エクスプ ローラー**です。 目的の関係を選択します。 **ソリューション エクスプ ローラー**指定した依存関係を持つコード要素のみが表示されます。<br />2.マップ画面に目的のコード要素をドラッグします。 クラス ビューまたはオブジェクト ブラウザーからコード要素をドラッグすることもできます。<br />     または<br />     **ソリューション エクスプ ローラー**、コード要素をマップするを選択します。 次に、**ソリューション エクスプ ローラー**ツールバーで、をクリックして**コード マップに表示**です。<br /><br /> 既定では、新しいコード要素の親コンテナーの階層がマップに表示されます。 使用して、**親を含める**この動作を変更するコード マップ ツールバーでボタンをクリックします。 オフにすると、コード要素だけがマップに追加されます。 この動作を 1 つだけのドラッグを反転し、アクション、プレス アンド ホールドをドロップする、 **CTRL**キー コード要素をマップにドラッグします。<br /><br /> Visual Studio は、選択項目の中の最上位レベルのコード項目に対してコード要素を追加します。 コード要素にその他のコード要素が含まれているかどうかを確認するには、コード要素にマウス ポインターを移動して、シェブロン (下向き矢印) を表示します。 シェブロンをクリックして、コード要素を展開します。 すべてのコード要素を展開するには、キーを押して**CTRL**+**A**すべての要素を選択する、マップのショートカット メニューを開き**グループ**、**展開**. すべてのグループを展開することで、使用できないマップの問題やメモリ不足の問題が発生する場合、このコマンドは使用できません。|
|マップにコード要素に関連するコード要素を表示します。|クリックして、 **関連表示**コード マップ ツールバーでボタンをクリックし、興味のある関連する項目の種類を選択します。<br /><br /> または<br /><br /> コード要素のショートカット メニューを開きます。 いずれかを選択、**を表示しています.** 興味のあるリレーションシップの種類に応じてメニュー上の項目。 たとえば、現在の項目が参照している項目、現在の項目を参照する項目、クラスの基本と派生型、メソッドの呼び出し元、および含んでいるクラス、名前空間、アセンブリなどを確認できます。<br /><br /> 詳細については、次を参照してください。[ここ](../modeling/map-dependencies-across-your-solutions.md)です。|
|コンパイルされた .NET アセンブリ (.dll または .exe) またはバイナリ。|Visual Studio の外部から、アセンブリまたはバイナリをマップにドラッグします。<br /><br /> エクスプローラーからドラッグできるのは、エクスプローラーと Visual Studio を同じユーザー アクセス制御 (UAC: User Access Control) アクセス許可レベルで実行している場合のみです。 たとえば、UAC がオンになっていて、Visual Studio を管理者として実行している場合、エクスプローラーはドラッグ操作をブロックします。|

###  <a name="AddNodes"></a>
##### <a name="add-a-link-between-existing-code-elements"></a>既存のコード要素間にリンクを追加する

1.  ソース コード要素を選択します。 コード要素の上にツールバーが表示されます。

     ![依存関係のグラフ ツールバー](../modeling/media/depedencygraph_toolbar.png "DepedencyGraph_Toolbar")

2.  ツールバーで、最初のアイコンを選択**作成の新しいリンクをこのノードから [次へ] をクリックするノード**です。

3.  対象のコード要素をクリックします。 2 つのコード要素間にリンクが表示されます。

 \- または -

1.  マップ上でソース コード要素を選択します。

2.  マウスがインストールされている場合、マップの範囲外に、マウス ポインターを移動します。

3.  コード要素のショートカット メニューを開き**編集**、**追加**、**ジェネリック リンク**です。

4.  Tab キーを押して、リンクのターゲット コード要素を選択します。

5.  **RETURN**キーを押します。

###  <a name="AddComments"></a>
##### <a name="add-a-comment-to-an-existing-node-on-the-map"></a>マップ上の既存のノードにコメントを追加する

1.  コード要素を選択します。 その上にツールバーが表示されます。

     ![依存関係のグラフ ツールバー](../modeling/media/depedencygraph_toolbar.png "DepedencyGraph_Toolbar")

2.  ツールバーで、3 番目のアイコンを選択**選択したノードに新しいリンクを持つ新しいコメント ノードを作成**です。

     \- または -

     コード要素のショートカット メニューを開き**編集**、**新しいコメント**です。

3.  コメントを入力します。 新しい行に入力するキーを押して**shift キーを押し** + **返す**です。

##### <a name="add-a-comment-to-the-map-itself"></a>マップ自体にコメントを追加する

1.  マップのショートカット メニューを開き**編集**、**新しいコメント**です。

2.  コメントを入力します。 新しい行に入力するキーを押して**shift キーを押し** + **返す**です。

###  <a name="RenameNodes"></a>
##### <a name="rename-a-code-element-or-link"></a>コード要素またはリンク名を変更する

1.  名前を変更するコード要素またはリンクを選択します。

2.  キーを押して**F2**、または、ショートカット メニューを開き**編集**、**の名前を変更**です。

3.  マップで編集ボックスが表示されたら、コード要素またはリンクの名前を変更します。

     \- または -

4.  ショートカット メニューを開き**編集**、**プロパティ**です。

5.  編集、**ラベル**Visual Studio プロパティ ウィンドウでプロパティです。

##### <a name="remove-a-code-element-or-link-from-the-map"></a>マップからコード要素またはリンクを削除します。

1.  コード要素またはリンクとキーを押して選択、**削除**キー。

     \- または -

     コード要素またはリンクのショートカット メニューを開き**編集**、**削除**です。

2.  要素またはリンクが、グループの一部である場合、**子の再フェッチ**ボタン![子の再フェッチ アイコン](../modeling/media/dependencygraph_deletednodesicon.png "DependencyGraph_DeletedNodesIcon")グループ内に表示されます。 このボタンをクリックすると、足りない要素とリンクが再フェッチされます。

-   基本コードに影響を与えずに、マップからコード要素を削除できます。 コード要素を削除すると、その定義は、DGML (.dgml) ファイルから削除されます。

-   DGML を編集したり、未定義のコード要素を追加したり、旧バージョンの Visual Studio を使用したりして作成したマップは、この機能をサポートしません。

##### <a name="flag-a-code-element-for-follow-up"></a>フォロー アップ用にコード要素にフラグを設定する

1.  フォローアップ用にフラグを設定するコード要素またはリンクを選択します。

2.  ショートカット メニューを開き**編集**、**フラグの設定**です。

-   既定では、コード要素は赤の背景色で表示されます。 検討してください[コメントを追加する](#AddComments)適切なフォロー アップ情報を使用しています。

-   要素の背景色を変更または選択して、フラグをオフに**編集**、**その他のフラグの色**です。

##  <a name="ChangeStyleCodeOrLink"></a> コード要素またはリンクのスタイルを変更します。
 事前定義されたアイコンと色を使って、コード要素のアイコン、およびコード要素とリンクの色を変更できます。 たとえば、色を選択することで、特定のカテゴリまたは特定のプロパティを持つコード要素およびリンクを強調して表示できます。 これにより、マップの特定の領域を識別し、目立たせることができます。 マップの .dgml ファイルを編集することによってカスタム アイコンおよび色を指定できます。参照してください[DGML ファイルを編集してカスタマイズ コードがマップ](../modeling/customize-code-maps-by-editing-the-dgml-files.md)です。

#### <a name="to-apply-a-predefined-color-or-icon-to-code-elements-or-links-with-a-certain-category-or-property"></a>特定のカテゴリまたは特定のプロパティを持つコード要素やリンクに定義済みの色またはアイコンを適用するには

1.  マップ ツールバーで、次のように選択します。**凡例**です。

2.  **凡例**ボックスで、一覧で、コード要素のカテゴリまたはプロパティが既に表示されてかどうかを参照してください。

3.  一覧に、カテゴリまたはプロパティを含まない場合は、選択**+** で、**凡例**を選択すると、ボックス、**ノード プロパティ**、**ノード カテゴリ**、**プロパティ リンク**、または**リンク カテゴリ**です。 次に、プロパティまたはカテゴリを選択します。 カテゴリまたはプロパティに表示されるよう、**凡例**ボックス。

    > [!NOTE]
    >  作成し、コード要素をカテゴリまたはプロパティを割り当てる、マップの .dgml ファイルを編集することができます。参照してください[DGML ファイルを編集してカスタマイズ コードがマップ](../modeling/customize-code-maps-by-editing-the-dgml-files.md)です。

4.  **凡例**ボックス、またはを変更する、カテゴリまたは追加したプロパティの横のアイコンをクリックします。

5.  次の表を使用して、変更するスタイルを選択します。

    |**変更するには**|**Choose**|
    |-----------------------|----------------|
    |背景色|**背景**|
    |外枠の色|**線**|
    |テキストの色 (結果を表示するのには文字"f"が表示されます)|**前景色**|
    |アイコン|**アイコン**|

     **カラー設定ピッカー**または**アイコン セット ピッカー**色やアイコンを選択するためのダイアログ ボックスが表示されます。

6.  **カラー設定ピッカー**または**アイコン セット ピッカー**  ダイアログ ボックスで、次のいずれかの操作を行います。

    |**適用する、**|**次の手順を実行します。**|
    |--------------------|-----------------------------|
    |色またはアイコンのセット|開く、**の色を選択**(または**アイコン**)**設定** ボックスの一覧です。 色またはアイコンのセットを選択します。|
    |特定の色またはアイコン|カテゴリまたはプロパティ値のリストを開きます。 色またはアイコンを選択します。|

    > [!NOTE]
    >  再配置、削除、または内のスタイルを一時的に無効化、**凡例**ボックス。 参照してください[[凡例] ボックスの編集](#ModifyLegend)です。

##  <a name="ModifyLegend"></a> [凡例] ボックスを編集します。
 再配置、削除、または内のスタイルを一時的に無効化、**凡例**ボックス。

1.  スタイルのショートカット メニューを開き、**凡例**ボックス。

2.  次のいずれかのタスクを実行します。

    |**目的**|**Choose**|
    |------------|----------------|
    |コード要素の無効化|**無効化**|
    |コード要素の削除|**削除**|
    |アイテムを上へ移動する|**上へ移動します。**|
    |コード要素を下へ移動|**下へ移動します。**|

##  <a name="CopyLegend"></a> 1 つのマップから別のスタイルをコピーします。

1.  確認、**凡例**ソース マップにボックスが表示されます。 マップ ツールバーで、表示されていない場合、クリックして**凡例**です。

2.  ショートカット メニューを開き、**凡例**ボックス。 選択**凡例のコピー**です。

3.  ターゲット マップに凡例を貼り付けます。

##  <a name="MergeMaps"></a> コード マップをマージします。
 マップ間でコード要素をコピーして貼り付けることで、マップをマージできます。 コード要素の識別子が一致する場合、コード要素の貼り付けはマージ操作と同様に機能します。 このタスクを簡単にするためには、視覚化するすべてのアセンブリとバイナリを同じフォルダー内に配置することで、各アセンブリまたはバイナリの完全パスが、マージする各マップに対して同じになるようにします。

 また、それらのアセンブリやバイナリをドラッグして、そのフォルダーから同じマップへドラッグすることもできます。

## <a name="see-also"></a>関連項目

- [ソリューション間の依存関係をマップする](../modeling/map-dependencies-across-your-solutions.md)
- [コード マップを使用してアプリケーションをデバッグする](../modeling/use-code-maps-to-debug-your-applications.md)
- [コード マップ アナライザーを使用して潜在的な問題を検索する](../modeling/find-potential-problems-using-code-map-analyzers.md)
- [DGML ファイルを編集してコード マップをカスタマイズする](../modeling/customize-code-maps-by-editing-the-dgml-files.md)
- [Directed Graph Markup Language (DGML) リファレンス](../modeling/directed-graph-markup-language-dgml-reference.md)
