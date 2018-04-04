---
title: '方法: Visual Studio でロード テスト結果をリポジトリにインポートする | Microsoft Docs'
ms.date: 10/19/2016
ms.topic: article
helpviewer_keywords:
- results, load test
- load test results, importing
- Load Test Results Repository
- load tests, importing results
ms.assetid: a955b3d2-c8ad-40dd-8ea3-9f1a271e1eed
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-ide-test
ms.openlocfilehash: 1d9f94641fe3249e6aa36b01b408abd66781b81f
ms.sourcegitcommit: 900ed1e299cd5bba56249cef8f5cf3981b10cb1c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2018
---
# <a name="how-to-import-load-test-results-into-a-repository"></a>方法: ロード テスト結果をリポジトリにインポートする

ロード テストを実行すると、実行中に収集された情報がロード テストの結果リポジトリに保存されます。 ロード テストの結果リポジトリには、パフォーマンス カウンター データとエラー情報が含まれています。 詳細については、「[ロード テストの結果リポジトリ内のロード テストの結果の管理](../test/manage-load-test-results-in-the-load-test-results-repository.md)」を参照してください。

 ロード テストの結果をロード テスト エディターで管理するには、**[ロード テストの結果を開いて管理]** ダイアログ ボックスを使用します。 このダイアログ ボックスでは、ロード テストの結果を表示、インポート、エクスポート、および削除できます。

## <a name="to-import-results-into-a-repository"></a>結果をリポジトリにインポートするには

1.  Web パフォーマンスとロード テストのプロジェクトから、ロード テストを開きます。

2.  埋め込みツール バーの **[結果を開いて管理]** をクリックします。

     **[ロード テストの結果を開いて管理]** ダイアログ ボックスが表示されます。

3.  **[ロード テストの結果を検索するコントローラー名を入力]** でコントローラーを選択します。 ローカル コンピューターに保存された結果にアクセスする場合は、**[\<ローカル>]** を選択します。

     ロード テストの結果が使用可能な場合は、**[ロード テストの結果]** 一覧に表示されます。 この一覧の列は、**[時間]**、**[期間]**、**[ユーザー]**、**[成果]**、**[テスト]**、**[説明]** です。 **[テスト]** にはテストの名前が表示され、**[説明]** にはテストを実行する前に入力した説明が表示されます。

4.  **[インポート]** を選択します。

     **[ロード テストの結果のインポート]** ダイアログ ボックスが表示されます。

5.  **[ファイル名]** ボックスにアーカイブ テスト結果ファイルの名前を入力し、**[開く]** を選択します。

     \- または

     ファイルを参照し、**[開く]** を選択します。

    > [!NOTE]
    > ここで指定したアーカイブ テスト結果ファイルは、エクスポートによって作成されたものであることが必要です。

     結果がインポートされ、**[ロード テストの結果]** 一覧に表示されます。

## <a name="see-also"></a>関連項目

- [ロード テストの結果リポジトリ内のロード テストの結果の管理](../test/manage-load-test-results-in-the-load-test-results-repository.md)
- [ロード テストの結果の分析](../test/analyze-load-test-results-using-the-load-test-analyzer.md)
- [方法: ロード テスト結果をリポジトリからエクスポートする](../test/how-to-export-load-test-results-from-a-repository.md)