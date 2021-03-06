---
title: 'CA2114: メソッドのセキュリティは型のスーパーセットにします'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- MethodSecurityShouldBeASupersetOfType
- CA2114
helpviewer_keywords:
- CA2114
- MethodSecurityShouldBeASupersetOfType
ms.assetid: 663f7aa4-8be5-4bd5-be92-4e9444f07077
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 5d2fc6fb60dd837dd93de1db2758ee0e2c216850
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/26/2018
---
# <a name="ca2114-method-security-should-be-a-superset-of-type"></a>CA2114: メソッドのセキュリティは型のスーパーセットにします
|||
|-|-|
|TypeName|MethodSecurityShouldBeASupersetOfType|
|CheckId|CA2114|
|カテゴリ|Microsoft.Security|
|互換性に影響する変更点|あり|

## <a name="cause"></a>原因
 型は、宣言セキュリティおよびそのメソッドのいずれかが、同じセキュリティ操作の宣言セキュリティおよびセキュリティ アクションは[リンク確認要求](/dotnet/framework/misc/link-demands)の型によってチェックする権限は、アクセス許可のサブセットではありませんメソッドによってチェックされます。

## <a name="rule-description"></a>規則の説明
 メソッドには、同じアクションに対してメソッド レベルと型レベルの宣言セキュリティの両方を持つべきはありません。 2 つのチェックは結合はされません。メソッド レベルの要求のみが適用されます。 型のアクセス許可を要求する場合など、 `X`、アクセス許可を要求のメソッドのいずれかと`Y`、コードにアクセス許可がない`X`メソッドを実行します。

## <a name="how-to-fix-violations"></a>違反の修正方法
 操作の両方が必須であるかどうかを確認するコードを確認します。 両方のアクションが必要な場合は、メソッド レベルのアクションが、型レベルで指定したセキュリティが含まれていることを確認してください。 種類のアクセス許可を要求する場合など、 `X`、し、そのメソッドは、アクセス許可を要求する必要がありますも`Y`、メソッドが明示的に要求する必要があります`X`と`Y`です。

## <a name="when-to-suppress-warnings"></a>警告を抑制する状況
 メソッドは、型で指定されたセキュリティを必要としない場合は、この規則による警告を抑制するのには安全です。 ただし、これは通常のシナリオではありません、慎重に設計レビューの必要があります。

## <a name="example"></a>例
 次の例では、環境のアクセス許可を使用して、この規則違反の危険性を示します。 この例では、アプリケーション コードは、型に必要な権限を拒否する前にセキュリティで保護された型のインスタンスを作成します。 脅威の実際のシナリオでは、別の方法をオブジェクトのインスタンスを取得する必要があります。

 次の例では、ライブラリの要求は、型の書き込みアクセス許可し、メソッドに対する読み取りアクセス許可。

 [!code-csharp[FxCop.Security.MethodLevelSecurity#1](../code-quality/codesnippet/CSharp/ca2114-method-security-should-be-a-superset-of-type_1.cs)]

## <a name="example"></a>例
 次のアプリケーション コードでは、型レベルのセキュリティ要件を満たしていない場合でも、メソッドを呼び出すことによって、ライブラリの脆弱性を示します。

 [!code-csharp[FxCop.Security.TestMethodLevelSecurity#1](../code-quality/codesnippet/CSharp/ca2114-method-security-should-be-a-superset-of-type_2.cs)]

 この例を実行すると、次の出力が生成されます。

 **[すべてのアクセス許可]個人情報: 6/16/1964 12時 00分: 00 AM**
 **[書き込みアクセス許可がありません (の型によって要求)] の個人情報: 6/16/1964 12時 00分: 00 AM**
 **[いいえ読み取りアクセス許可 (によって要求されるメソッド)] の個人情報にアクセスできませんでした。 要求が失敗しました。**
## <a name="see-also"></a>関連項目
 [安全なコーディングのガイドライン](/dotnet/standard/security/secure-coding-guidelines)[リンク確認要求](/dotnet/framework/misc/link-demands)[データとモデリング](/dotnet/framework/data/index)