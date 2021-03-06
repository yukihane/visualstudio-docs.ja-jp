---
title: Visual Studio でのロード テストのしきい値違反| Microsoft Docs
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- load tests, threshold violations
ms.assetid: 0126d7b7-0538-4ea9-9046-6556654b3b9d
author: gewarren
ms.author: gewarren
manager: douge
ms.technology: vs-ide-test
ms.openlocfilehash: 6acb9eec16107134dc03765da82008a01b599e4b
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-analyze-threshold-violations-using-the-counters-panel-in-load-test-analyzer"></a>方法: ロード テスト アナライザーのカウンター パネルを使用して、しきい値違反を分析する

[カウンター] パネルは、ロード テストが実行中か、ロード テスト結果を分析しているとき、ロード テスト アナライザーにグラフ ビューおよびテーブル ビューで表示されます。 「[ロード テスト アナライザーのグラフ ビューでのテスト結果の分析](../test/analyze-load-test-results-in-the-graphs-view.md)」、「[ロード テスト アナライザーのテーブル ビューでのロード テスト結果とエラーの分析](../test/analyze-load-test-results-and-errors-in-the-tables-view.md)」、および「[方法: ロード テストの結果にアクセスして分析する](../test/how-to-access-load-test-results-for-analysis.md)」を参照してください。

 しきい値違反は、特定のパフォーマンス カウンターに関連付けられ、パフォーマンス カウンターがしきい値を上回ったこと、または下回ったことを示します。 [カウンター] パネルのアイコンがしきい値違反を示します。

 ![[カウンター] パネルのコンピューター ノード](../test/media/ltest_compnode.png "LTest_CompNode")

 しきい値違反を示すアイコンは、違反が発生したカウンターが存在するツリー ノードからルートまで反映されます。 また、ツリーが折りたたまれていて表示されないカウンターに関する違反の警告もアイコンに表示されます。 このアイコンの例は、前の図の [カウンター] パネル内にある**コンピューター ノード**に示されています。

 アイコンは以下のいずれかです。

 ![しきい値違反なし](../test/media/icon_ltest_1.gif "Icon_LTest_1") しきい値違反なし。

 ![最後の間隔における重大なしきい値違反](../test/media/icon_ltest_2.gif "Icon_LTest_2") 重大なしきい値違反が最後の間隔で発生した。

 ![以前の間隔における重大なしきい値違反](../test/media/icon_ltest_3.gif "Icon_LTest_3") 重大なしきい値違反が以前の間隔で発生した。

 ![最後の間隔における警告しきい値違反](../test/media/icon_ltest_4.gif "Icon_LTest_4") 警告しきい値違反が最後の間隔で発生した。

 ![以前の間隔における警告しきい値違反](../test/media/icon_ltest_5.gif "Icon_LTest_5") 警告しきい値違反が前の間隔で発生した。

## <a name="to-analyze-threshold-violations-in-the-counters-panel"></a>[カウンター] パネルのしきい値違反を分析するには

1.  ロード テストの完了後またはテスト結果の読み込み後、ロード テスト アナライザーのツール バーの **[グラフ]** または **[テーブル]** を選択します。

     [カウンター] パネルがグラフ ビューまたはテーブル ビューで表示されます。

2.  [カウンター] パネルが表示されない場合、ツール バーの **[カウンター パネルの表示]** を選択します。

     しきい値違反が発生しているすべてのノードで、上記のいずれかのアイコンが表示されます。

3.  前の "しきい値違反が発生している [カウンター] パネルのコンピューター ノード" というタイトルの図に示すように、**コンピューター** ノードなど、しきい値アイコンを含むノードを展開します。 しきい値違反が発生したパフォーマンス カウンターが見つかるまで、ノードを展開します。 たとえば、この図では、**Microsoft Virtual Machine の失敗したバス ネットワーク アダプター**の失敗したインスタンスが示されています。

4.  (省略可能) しきい値違反が発生したパフォーマンス カウンターを右クリックし、次のいずれかのオプションを選択します。

    -   **[グラフにカウンターを表示]**: グラフ ビューで、パフォーマンス カウンターが追加され、選択したグラフで強調表示されます。 詳細については、「[方法: グラフにカウンターを追加および削除する](../test/how-to-add-and-delete-counters-on-graphs-in-load-test-results.md)」を参照してください。

        > [!NOTE]
        > グラフ ビューでは、しきい値違反アイコンもグラフ上に表示されます。 しきい値アイコンは、グラフ上のしきい値違反が発生したデータ ポイントの隣に表示されます。 このように表示するには、ツール バーの **[凡例の表示]** ドロップダウンを選択し、**[しきい値の違反をグラフに表示]** を選択します。

    -   **[凡例にカウンターを表示]**: 凡例で、パフォーマンス カウンターが追加および選択されます。 詳細については、「[グラフ ビューの凡例を使用したロード テストの分析](../test/use-the-graphs-view-legend-to-analyze-load-tests.md)」を参照してください。

    -   **[グラフの追加]**:

    1.  **[グラフ名の入力]** ダイアログ ボックスが表示されます。

    2.  **[グラフ名]** テキスト ボックスに新しいグラフの名前を入力し、**[OK]** を選択します。

    3.  (省略可能) パフォーマンス カウンターを再度右クリックし、**[グラフにカウンターを表示]** を選択します。

         詳細については、[カスタム グラフを作成する方法](../test/how-to-create-custom-graphs-in-load-test-results.md)に関するページを参照してください。

5.  (省略可能) 完了したロード テスト結果のしきい値違反を分析する場合、グラフ ビューのズーム機能の使用を検討してください。 詳細については、「[方法: グラフの領域にズーム インする](../test/how-to-zoom-in-on-a-region-of-the-graph-in-load-test-results.md)」を参照してください。

    > [!TIP]
    > ロード テストの実行中にしきい値違反が検出された場合、[しきい値の違反です] というリンクがロード テスト アナライザーのステータス バーに表示され、違反の数が示されます。 このリンクを選択すると、テーブル ビューの **[しきい値]** テーブルにすべてのしきい値違反を表示できます。

## <a name="see-also"></a>関連項目

- [グラフ ビューおよびテーブル ビューでのカウンター パネルの使用](../test/counters-panel-in-load-test-analyzer.md)
- [ロード テストの結果の分析](../test/analyze-load-test-results-using-the-load-test-analyzer.md)