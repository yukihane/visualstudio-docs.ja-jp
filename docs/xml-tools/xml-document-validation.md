---
title: XML エディターで XML ドキュメントの検証
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-xml-tools
ms.topic: conceptual
ms.assetid: abb353bd-6c4a-4978-b03b-a8c245bbfb55
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 31fd55358023e0ec3b11fbb048bdfa2b240b1859
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/26/2018
---
# <a name="xml-document-validation"></a>XML ドキュメントの検証

XML エディターは、ユーザーが入力するときに XML 1.0 の構文をチェックし、データの検証も実行します。 エディターは、ドキュメント型定義 (DTD) やスキーマを使用して検証を行うことができます。 XML 1.0 の整形式のエラーは、赤色の波下線で強調表示されます。 青色の波下線は、DTD またはスキーマの検証に基づいたセマンティック エラーを示します。 エラーの一覧には、それぞれのエラーに関連するエントリが示されます。 マウスを波下線の上に置くことで、エラー メッセージを表示させることもできます。

 検証で使用されるスキーマの検索は、コンパイル済みのスキーマの `targetNamespace` と、要素の xmlns 宣言とを照合して行われます。 コンパイル済みのスキーマが読み込まれる場所を、優先度の高い順に次に示します。

-   指定されたファイル名から、**スキーマ**ドキュメントのプロパティ ウィンドウのフィールドです。

-   インラインのスキーマまたは DTD。

-   外部 DTD または `xsd:schemaLocation` および `xsd:noNamespaceSchemaLocation` 属性。

-   "x-schema" XDR スキーマ名前空間 URI。

スキーマに空でない対象名前空間がある場合は、次に示す場所でスキーマが検索されることもあります。

-   スキーマを含む他のエディター ウィンドウ。

-   現在のソリューション内にあるスキーマ。

-   スキーマ キャッシュ ディレクトリ内にあるスキーマ。

## <a name="xslt-files"></a>XSLT ファイル
 XSLT ファイルの編集時には、スキーマ キャッシュ内に置かれている xslt.xsd ファイルが検証に使用されます。 検証エラーは、青色の波下線で表示されます。 XSLT コンパイラによるエラーは、赤色の波下線で示されます。

## <a name="xml-schema-xsd-files"></a>XML スキーマ (XSD) ファイル
 XML スキーマ ファイルの編集時には、スキーマ キャッシュ内に置かれている xsdschema.xsd ファイルが検証に使用されます。 検証エラーは、青色の波下線で表示されます。 コンパイル エラーも赤色の波下線で示されます。

## <a name="see-also"></a>関連項目

- [XML エディター](../xml-tools/xml-editor.md)