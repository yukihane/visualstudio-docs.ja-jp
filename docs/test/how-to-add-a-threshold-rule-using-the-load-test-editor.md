---
title: Visual Studio でロード テスト用のしきい値規則を追加する | Microsoft Docs
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- load tests, monitoring
- load tests, thresholds
- load tests, analyzing
- thresholds in load tests
ms.assetid: 3d8fac8f-426f-4155-9ced-f7cd4c79792c
author: gewarren
ms.author: gewarren
manager: douge
ms.technology: vs-ide-test
ms.openlocfilehash: 9ee9f8c5ca052c101c5013f7fb2341efdc9cdfa1
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-add-a-threshold-rule-using-the-load-test-editor"></a>方法: ロード テスト エディターを使用してしきい値規則を追加する

ロード テストのしきい値規則は、パフォーマンス カウンターの値を定数値または別のパフォーマンス カウンターの値と比較します。

## <a name="to-add-a-threshold-rule"></a>しきい値規則を追加するには

1.  ロード テストを開きます。

2.  ロード テスト エディターで、**[カウンター セット]** ノードを展開します。

3.  [カウンター セット] のいずれかで、**[カウンター カテゴリ]** のいずれかを展開します。 たとえば、**[LoadTest:Scenario]** を選択します。 ノードを展開します。

4.  カウンターのいずれか、たとえば **[LoadTest:Scenario]** の **[User Load]** を右クリックします。 **[しきい値規則の追加]** を選択します。

     **[しきい値規則の追加]** ダイアログ ボックスが表示されます。

5.  [定数の比較] および [カウンターの比較] の 2 種類の規則から選択します。 適切な種類を選択し、値を設定します。

    > [!NOTE]
    > **[しきい値を超えたときに警告]** プロパティは、しきい値を上回ると問題であることを示す場合は **True** に、しきい値を下回ると問題であることを示す場合は **False** に設定します。

## <a name="see-also"></a>関連項目

- [しきい値規則違反の分析](../test/analyze-threshold-rule-violations-in-load-tests.md)
- [ロード テストでのコンピューターのカウンター セットとしきい値規則の指定](../test/specify-counter-sets-and-threshold-rules-for-load-testing.md)
- [ロード テストの結果の分析](../test/analyze-load-test-results-using-the-load-test-analyzer.md)
- [ロード テストでのコンピューターのカウンター セットとしきい値規則の指定](../test/specify-counter-sets-and-threshold-rules-for-load-testing.md)