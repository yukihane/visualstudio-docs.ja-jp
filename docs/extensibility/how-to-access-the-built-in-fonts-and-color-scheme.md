---
title: '方法: 組み込みのフォントおよび画面の配色にアクセス |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- fonts, accessing built-in
- font and color control [Visual Studio SDK], categories
- colors, accessing built-in schemes
ms.assetid: 6905845e-e88e-4805-adcf-21da39108ec7
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 5f72640369152b03ef86383fda1162b1cfbacba8
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-access-the-built-in-fonts-and-color-scheme"></a>方法: 組み込みのフォントと配色へのアクセス
Visual Studio 統合開発環境 (IDE) では、エディター ウィンドウに関連付けられているフォントおよび色のスキームがします。 このスキームを通じてアクセスできる、<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView>インターフェイスです。

 組み込みのフォントおよびカラー スキームを使用するのには、VSPackage 必要があります。

-   既定のフォントおよび色のサービスで使用するカテゴリを定義します。

-   既定のフォントおよび色のサーバーに、カテゴリを登録します。

-   IDE をアドバイスする特定のウィンドウでは、組み込みの表示項目とカテゴリを使用して、<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextEditorPropertyCategoryContainer>と<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextEditorPropertyContainer>インターフェイスです。

 IDE では、ウィンドウのハンドルとして、結果として得られるカテゴリを使用します。 カテゴリの名前に表示されます、**設定の表示:**ドロップダウン ボックスで、**フォントおよび色**プロパティ ページ。

### <a name="to-define-a-category-using-built-in-fonts-and-colors"></a>組み込みのフォントおよび色を使用してカテゴリを定義するには

1.  任意の GUID を作成します。

     この GUID を使用して、カテゴリを一意に識別**です。** このカテゴリには、IDE の既定のフォントおよび色の仕様が再利用します。

    > [!NOTE]
    >  フォントおよびカラーのデータを取得するときに、<xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorEvents>またはその他のインターフェイスでは、Vspackage この GUID を使用して組み込まれている情報を参照します。

2.  カテゴリの名前は、IDE で表示されるときに、必要に応じてローカライズできるように、ファイル内で、VSPackage のリソース (.rc)、文字列テーブルに追加する必要があります。

     詳細については、次を参照してください。[を追加または削除文字列](/cpp/windows/adding-or-deleting-a-string)です。

### <a name="to-register-a-category-using-built-in-fonts-and-colors"></a>組み込みのフォントおよび色を使用してカテゴリを登録するには

1.  次の場所にレジストリ エントリのカテゴリの特殊な型を作成します。

     [Hklm \software\microsoft \Visual Studio\\*\<Visual Studio version >*\FontAndColors\\*\<カテゴリ >*]

     *\<カテゴリ >*カテゴリのローカライズされていない名前を指定します。

2.  ストック フォントと配色 4 つの値を使用するレジストリを作成します。

    |名前|型|データ|説明|
    |----------|----------|----------|-----------------|
    |カテゴリ|REG_SZ|GUID|ストック フォントおよびカラー スキームを格納するカテゴリを識別する任意の GUID です。|
    |Package|REG_SZ|GUID|{F5E7E71D-1401-11D1-883B-0000F87579D2}<br /><br /> この GUID は、既定のフォントと色の構成を使用するすべての Vspackage を使用します。|
    |NameID|REG_DWORD|ID|VSPackage のローカライズ可能なカテゴリ名のリソース ID です。|
    |ToolWindowPackage|REG_SZ|GUID|VSPackage の実装の GUID、<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView>インターフェイスです。|

### <a name="to-initiate-the-use-of-system-provided-fonts-and-colors"></a>システム標準のフォントおよび色の使用を開始するには

1.  インスタンスを作成、<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextEditorPropertyCategoryContainer>ウィンドウの実装と初期化の一部としてインターフェイスです。

2.  呼び出す、<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextEditorPropertyCategoryContainer.GetPropertyCategory%2A>のインスタンスを取得するメソッド、<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextEditorPropertyContainer>現在に対応するインターフェイス<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView>インスタンス。

3.  呼び出す<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextEditorPropertyContainer.SetProperty%2A>2 回クリックします。

    -   1 回呼び出す`VSEDITPROPID_ViewGeneral_ColorCategory`を引数として。

    -   1 回呼び出す`VSEDITPROPID_ViewGeneral_FontCategory`を引数として。

     これにより、設定し、ウィンドウのプロパティとして既定のフォントおよび色のサービスを公開します。

## <a name="example"></a>例
 次の例では、組み込みのフォントおよび色の使用を開始します。

```cpp
CComVariant vt;
CComQIPtr<IVsTextEditorPropertyCategoryContainer> spPropCatContainer(m_spView);
if (spPropCatContainer != NULL){
    CComPtr<IVsTextEditorPropertyContainer> spPropContainer;
    if (SUCCEEDED(spPropCatContainer->GetPropertyCategory(GUID_EditPropCategory_View_MasterSettings,
                                                          &spPropContainer))){
        CComVariant vt;CComVariant VariantGUID(bstrGuidText);
        spPropContainer->SetProperty(VSEDITPROPID_ViewGeneral_FontCategory, VariantGUID);
        spPropContainer->SetProperty(VSEDITPROPID_ViewGeneral_ColorCategory, VariantGUID);
    }
}
```

## <a name="see-also"></a>関連項目

- [フォントおよび色を使用します。](../extensibility/using-fonts-and-colors.md)
- [フォントとテキスト彩色の色の情報を取得します。](../extensibility/getting-font-and-color-information-for-text-colorization.md)
- [ストアドのフォントおよび色の設定にアクセスします。](../extensibility/accessing-stored-font-and-color-settings.md)
- [フォントと色の概要](../extensibility/font-and-color-overview.md)