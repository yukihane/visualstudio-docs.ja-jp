---
title: AssignProjectConfiguration タスク | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
- jsharp
ms.assetid: 09633a0b-8f6f-4aba-8058-7cb4d13ce2c0
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: d771117829ab8ef37ea495b4862ffa492e686770
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/19/2018
---
# <a name="assignprojectconfiguration-task"></a>AssignProjectConfiguration タスク
このタスクは、構成文字列の一覧を受け入れ、それらを指定されたプロジェクトに割り当てます。  
  
## <a name="task-parameters"></a>タスク パラメーター  
 `AssignProjectConfiguration` タスクのパラメーターの説明を次の表に示します。  
  
|パラメーター|説明|  
|---------------|-----------------|  
|`SolutionConfigurationContents`|省略可能な `string` 型の出力パラメーターです。<br /><br /> 各プロジェクトのプロジェクト構成を含む XML 文字列が含まれます。 構成は、指定したプロジェクトに割り当てられます。|  
|`DefaultToVcxPlatformMapping`|省略可能な `string` 型の出力パラメーターです。<br /><br /> ほとんどのタイプで使用されるプラットフォーム名から .vcxproj ファイルで使用される<br /><br /> プラットフォーム名へのマッピングのセミコロン区切りのリストが含まれます。<br /><br /> 例:<br /><br /> `"AnyCPU=Win32;X86=Win32;X64=X64"`|  
|`VcxToDefaultPlatformMapping`|Optional<br /><br /> `string` 出力パラメーターです。<br /><br /> .vcxproj プラットフォーム名からほとんどのタイプで使用されるプラットフォーム名へのマッピングのセミコロン区切りのリストが含まれます。<br /><br /> 例:<br /><br /> `"Win32=AnyCPU;X64=X64"`|  
|`CurrentProjectConfiguration`|省略可能な `string` 型の出力パラメーターです。<br /><br /> 現在のプロジェクトの構成が含まれます。|  
|`CurrentProjectPlatform`|省略可能な `string` 型の出力パラメーターです。<br /><br /> 現在のプロジェクトのプラットフォームが含まれます。|  
|`OnlyReferenceAndBuildProjectsEnabledInSolutionConfiguration`|省略可能な `bool` 型の出力パラメーターです。<br /><br /> プロジェクト構成で無効になっている場合でも、参照を構築する必要があることを示すフラグが含まれます。|  
|`ShouldUnsetParentConfigurationAndPlatform`|省略可能な `bool` 型の出力パラメーターです。<br /><br /> 親の構成およびプラットフォームの設定を解除する必要があるかどうかを示すフラグが含まれます。|  
|`OutputType`|省略可能な `string` 型の出力パラメーターです。<br /><br /> プロジェクトの出力の種類が含まれます。|  
|`ResolveConfigurationPlatformUsingMappings`|省略可能な `bool` 型の出力パラメーターです。<br /><br /> 渡されたプロジェクト参照の構成およびプラットフォームを解決するためにビルドで既定のマッピングを使用する必要があるかどうかを示すフラグが含まれます。|  
|`AssignedProjects`|省略可能な <xref:Microsoft.Build.Framework.ITaskItem>`[]` 型の出力パラメーターです。<br /><br /> 解決済み参照パスのリストが含まれます。|  
|`UnassignedProjects`|省略可能な <xref:Microsoft.Build.Framework.ITaskItem>`[]` 型の出力パラメーターです。<br /><br /> 出力の事前解決リストを使用して解決できなかったプロジェクト参照項目のリストが含まれます。|  
  
## <a name="remarks"></a>コメント  
 上記のパラメーター以外に、このタスクは <xref:Microsoft.Build.Tasks.TaskExtension> クラスからパラメーターを継承します。このクラス自体は、<xref:Microsoft.Build.Utilities.Task> クラスから継承されます。 これらの追加のパラメーターの一覧とその説明については、「 [TaskExtension Base Class](../msbuild/taskextension-base-class.md)」を参照してください。  
  
## <a name="see-also"></a>参照  
 [タスク](../msbuild/msbuild-tasks.md)   
 [Task Reference (タスク リファレンス)](../msbuild/msbuild-task-reference.md)