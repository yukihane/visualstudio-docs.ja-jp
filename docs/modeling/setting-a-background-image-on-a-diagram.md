---
title: ダイアグラムへの背景イメージの設定
ms.date: 11/04/2016
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.technology: vs-ide-modeling
ms.openlocfilehash: 6b81bfcf0be55236b9b9321a4f04a8dd03f8e3ab
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/26/2018
---
# <a name="setting-a-background-image-on-a-diagram"></a>ダイアグラムへの背景イメージの設定
[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] Visualization and Modeling SDK では、カスタム コードを使用して生成されるデザイナーの背景イメージを設定できます。

## <a name="setting-the-background-image"></a>背景イメージの設定

#### <a name="to-set-a-background-image-for-a-generated-designer"></a>生成されるデザイナーの背景イメージを設定するには

1.  図の背景として使用するイメージ ファイルを、現在のプロジェクトの Dsl\Resources ディレクトリにコピーします。

2.  **ソリューション エクスプ ローラー**Dsl\Resources フォルダーを右クリックしをポイントし、**追加**、クリックして**既存項目の**します。

3.  **既存項目の追加** ダイアログ ボックスで、Dsl\Resources フォルダーを参照します。

4.  **ファイルの種類**一覧で、クリックして**イメージ ファイル**です。

5.  ディレクトリにコピーした画像ファイルをクリックし、クリックして**追加**です。

6.  Dsl を右クリックし、をクリックして**プロパティ**Dsl プロジェクトのプロパティを開きます。

7.  **リソース** タブで、をクリックして**このプロジェクトに既定のリソース ファイルが含まれていません。作成するのにはここをクリックします。**

8.  画像をドラッグして、リソース ファイルをイメージ ファイルを追加**ソリューション エクスプ ローラー**リソース ウィンドウに表示します。

9. ［ファイル］ メニューを開き、プロジェクトのプロパティを保存するオプションをクリックします。

10. ファイル Dsl\Properties\Resources.resx が存在しており、その下に Resources.Designer.cs ファイルがあることを確認します。

11. Resources.Designer.cs が不足している場合は、ファイル Resources.resx をクリックしてで**ソリューション エクスプ ローラー**です。

12. **プロパティ**ウィンドウで、設定、`Custom Tool`プロパティを`ResXFileCodeGenerator`です。

13. **ソリューション エクスプ ローラー**Dsl プロジェクトを右クリックしをポイントし、**追加**、 をクリック**新しいフォルダー**です。

14. 名前のフォルダー**カスタム**です。

15. カスタム フォルダーを右クリックし、[**追加**、] をクリック**新しい項目の**します。

16. **新しい項目の追加** ダイアログ ボックスで、**テンプレート**一覧で、クリックして**コード ファイル**です。

17. **名前**ボックスに、入力`BackgroundImage.cs`、 をクリック**追加**です。

18. 次のコードを BackgroundImage.cs ファイルにコピーし、名前空間、図クラス名、およびイメージ ファイル リソース名を調整します。

     "MyDiagramClass" を、Dsl\GeneratedCode\Diagrams.cs で定義されている図の部分クラスの名前に置き換えます。 Dsl\GeneratedCode\Diagrams.cs ファイルから正しい名前空間を取得することもできます。

    ```
    using System;
    using Microsoft.VisualStudio.Modeling.Diagrams;

    // Fix the namespace:
    namespace Fabrikam.MyLanguage
    {
      // Fix the Diagram Class name - get it from GeneratedCode\Diagram.cs

      public partial class Language29Diagram
      {
        protected override void InitializeInstanceResources()
        {
          // Fix the Resources namespace and the Image resource name:
          ImageField backgroundField = new ImageField("background",
              Fabrikam.MyLanguage.Properties.Resources.MyPicture);

          backgroundField.DefaultFocusable = false;
          backgroundField.DefaultSelectable = false;
          backgroundField.DefaultVisibility = true;
          backgroundField.DefaultUnscaled = false;

          shapeFields.Add(backgroundField);

          backgroundField.AnchoringBehavior
            .SetTopAnchor(AnchoringBehavior.Edge.Top, 0.01);
          backgroundField.AnchoringBehavior
            .SetLeftAnchor(AnchoringBehavior.Edge.Left, 0.01);
          backgroundField.AnchoringBehavior
            .SetRightAnchor(AnchoringBehavior.Edge.Right, 0.01);
          backgroundField.AnchoringBehavior
            .SetBottomAnchor(AnchoringBehavior.Edge.Bottom, 0.01);

          base.InitializeInstanceResources();
        }
      }
    }
    ```

     プログラム コードを使用してモデルをカスタマイズする方法の詳細については、次を参照してください。[を移動すると、プログラム コードでモデルを更新する](../modeling/navigating-and-updating-a-model-in-program-code.md)です。

## <a name="see-also"></a>関連項目

- [シェイプとコネクタの定義](../modeling/defining-shapes-and-connectors.md)
- [テキストおよびイメージ フィールドのカスタマイズ](../modeling/customizing-text-and-image-fields.md)
- [プログラム コードにおけるモデル内の移動およびモデルの更新](../modeling/navigating-and-updating-a-model-in-program-code.md)
- [ドメイン固有言語をカスタマイズするコードの記述](../modeling/writing-code-to-customise-a-domain-specific-language.md)

[!INCLUDE[modeling_sdk_info](includes/modeling_sdk_info.md)]
