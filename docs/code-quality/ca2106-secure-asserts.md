---
title: 'CA2106: アサートをセキュリティで保護します'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2106
- SecureAsserts
helpviewer_keywords:
- CA2106
- SecureAsserts
ms.assetid: 91feb36e-6e2c-436c-8272-5aee31f77e98
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 5863f4d8ca4db47f7e537f0b1abc5eb280434c80
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/26/2018
---
# <a name="ca2106-secure-asserts"></a>CA2106: アサートをセキュリティで保護します
|||
|-|-|
|TypeName|SecureAsserts|
|CheckId|CA2106|
|カテゴリ|Microsoft.Security|
|互換性に影響する変更点|あり|

## <a name="cause"></a>原因
 メソッドによってアクセス許可がアサートされますが、呼び出し元に対してセキュリティ チェックが実行されていません。

## <a name="rule-description"></a>規則の説明
 セキュリティ チェックを実行せずにセキュリティ アクセス許可をアサートすると、悪用される可能性があるセキュリティの弱点がコード内に残る場合があります。 セキュリティ アクセス許可がアサートされたときに、セキュリティのスタック ウォークが停止します。 呼び出し元に対してセキュリティ チェックを実行せずに、アクセス許可をアサートする場合、呼び出し元直接コードを実行されません、アクセス許可を使用します。 セキュリティ チェックは有害な方法で、アサートを使用できないことがわかっている場合のみで許容せずにアサートします。 呼び出すコードは、無害である場合は影響を与えません。 アサートを使用するか、ユーザーが任意の情報を呼び出すコードに渡すことはできません。

## <a name="how-to-fix-violations"></a>違反の修正方法
 この規則違反を修正するには、メソッド、またはその宣言型セキュリティの要求を追加します。

## <a name="when-to-suppress-warnings"></a>警告を抑制する状況
 セキュリティを慎重確認した後のみ、この規則による警告を抑制します。

## <a name="see-also"></a>関連項目
 <xref:System.Security.CodeAccessPermission.Assert%2A?displayProperty=fullName> [安全なコーディングのガイドライン](/dotnet/standard/security/secure-coding-guidelines)