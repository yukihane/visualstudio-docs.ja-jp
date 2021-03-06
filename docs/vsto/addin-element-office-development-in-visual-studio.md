---
title: '&lt;addin&gt;要素 (Visual Studio での Office 開発)'
ms.custom: ''
ms.date: 02/02/2017
ms.technology: office-development
ms.prod: visual-studio-dev15
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- application manifests [Office development in Visual Studio], <addIn> element
- addin element
- <addin> element
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 1d2ab0264452630892d492946462fbf9ad1639d0
ms.sourcegitcommit: 209c2c068ff0975994ed892b62aa9b834a7f6077
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2018
---
# <a name="ltaddingt-element-office-development-in-visual-studio"></a>&lt;addin&gt;要素 (Visual Studio での Office 開発)
  **Addin**の要素、`vstav3`名前空間には、Microsoft Office VSTO アドインおよび Visual Studio で開発したドキュメント レベルのカスタマイズに固有の情報が含まれています。  

## <a name="syntax"></a>構文  

```xml
<addIn>  
  <entryPointsCollection>  
    <entryPoints>  
      <entryPoint>  
      </entryPoint>  
    </entryPoints>  
  </entryPointsCollection>  
  <update></update>  
  <postActions>  
    <postAction>  
      <postActionData>  
      </postActionData>  
    <postAction>  
  </postActions>  
  <application>  
    <customization>  
    </customization>  
  </application  
</addIn>  
```  

## <a name="elements-and-attributes"></a>要素と属性  
 **Addin**の要素、`vstav3`名前空間には、Office ソリューションと Microsoft Office アプリケーションに関する情報が含まれています。 この要素は、名前空間 `vstav3=urn:schemas-microsoft-com:vsta.v3`に存在する必要があります。 子要素もこの名前空間に存在する必要があります。  

 `addin` 要素に属性はありません。  

 `addin` 要素には、次の子要素があります。  

### <a name="entrypoints"></a>entryPoints  
 必須。 **EntryPoints**要素については、「 [ &#60;entryPoints&#62;要素&#40;Visual Studio での Office 開発&#41;](../vsto/entrypoints-element-office-development-in-visual-studio.md)です。  

### <a name="update"></a>更新  
 必須。 **更新**要素については、「 [&#60;更新&#62;要素&#40;Visual Studio での Office 開発&#41;](../vsto/update-element-office-development-in-visual-studio.md)です。  

### <a name="postactions"></a>postActions  
 任意。 **PostActions**要素については、「 [ &#60;postActions&#62;要素&#40;Visual Studio での Office 開発&#41;](../vsto/postactions-element-office-development-in-visual-studio.md)です。  

### <a name="application"></a>アプリケーション  
 必須。 **アプリケーション**要素については、「 [&#60;アプリケーション&#62;要素&#40;Visual Studio での Office 開発&#41;](../vsto/application-element-office-development-in-visual-studio.md)です。  

## <a name="document-level-customization-example"></a>ドキュメント レベルのカスタマイズの例  

### <a name="description"></a>説明  
 次のコード例を示しています、 **addin**ドキュメント レベルの Office ソリューションを使用して配置されている要素[!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)]です。 このコード例に示されている例の一部である[Office ソリューション用アプリケーション マニフェスト](../vsto/application-manifests-for-office-solutions.md)です。  

### <a name="code"></a>コード  

```xml
<vstav3:addIn   
  xmlns:vstav3="urn:schemas-microsoft-com:vsta.v3">  
  <vstav3:entryPointsCollection>  
    <vstav3:entryPoints>  
      <vstav3:entryPoint   
        class="ContosoExcelWorkbook.ThisWorkbook">  
        <assemblyIdentity   
          name="ContosoExcelWorkbook"   
          version="1.0.0.0"   
          language="neutral"   
          processorArchitecture="msil" />  
      </vstav3:entryPoint>  
      <vstav3:entryPoint   
        class="ContosoExcelWorkbook.Sheet1">  
        <assemblyIdentity   
          name="ContosoExcelWorkbook"   
          version="1.0.0.0"   
          language="neutral"   
          processorArchitecture="msil" />  
      </vstav3:entryPoint>  
      <vstav3:entryPoint   
        class="ContosoExcelWorkbook.Sheet2">  
        <assemblyIdentity   
          name="ContosoExcelWorkbook"   
          version="1.0.0.0"   
          language="neutral"   
          processorArchitecture="msil" />  
      </vstav3:entryPoint>  
      <vstav3:entryPoint   
        class="ContosoExcelWorkbook.Sheet3">  
        <assemblyIdentity   
          name="ContosoExcelWorkbook"   
          version="1.0.0.0"   
          language="neutral"   
          processorArchitecture="msil" />  
      </vstav3:entryPoint>  
    </vstav3:entryPoints>  
  </vstav3:entryPointsCollection>  
  <vstav3:update   
    enabled="true">  
    <vstav3:expiration   
      maximumAge="7"   
      unit="days" />  
  </vstav3:update>  
  <vstav3:application>  
    <vstov4:customizations   
      xmlns:vstov4="urn:schemas-microsoft-com:vsto.v4">  
      <vstov4:customization>  
        <vstov4:document   
          solutionId="73e" />  
      </vstov4:customization>  
    </vstov4:customizations>  
  </vstav3:application>  
</vstav3:addIn>  
```  

## <a name="vsto-add-in-example"></a>VSTO アドインの例  

### <a name="description"></a>説明  
 次のコード例を示しています、 **addin**要素を使用して配置されているアプリケーション レベルの Office ソリューションで[!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)]です。 このコード例に示されている例の一部である[Office ソリューション用アプリケーション マニフェスト](../vsto/application-manifests-for-office-solutions.md)です。  

### <a name="code"></a>コード  

```xml
<vstav3:addIn   
  xmlns:vstav3="urn:schemas-microsoft-com:vsta.v3">  
  <vstav3:entryPointsCollection>  
    <vstav3:entryPoints>  
      <vstav3:entryPoint   
        class="ContosoOutlookAddIn.ThisAddIn">  
        <assemblyIdentity   
          name="ContosoOutlookAddIn"   
          version="1.0.0.0"   
          language="neutral"   
          processorArchitecture="msil" />  
      </vstav3:entryPoint>  
    </vstav3:entryPoints>  
  </vstav3:entryPointsCollection>  
  <vstav3:update   
    enabled="true">  
    <vstav3:expiration   
      maximumAge="7"   
      unit="days" />  
  </vstav3:update>  
  <vstav3:application>  
    <vstov4:customizations   
      xmlns:vstov4="urn:schemas-microsoft-com:vsto.v4">  
      <vstov4:customization>  
        <vstov4:appAddIn   
          application="Outlook"   
          loadBehavior="3"   
          keyName="ContosoOutlookAddIn">  
          <vstov4:friendlyName>  
            ContosoOutlookAddIn  
          </vstov4:friendlyName>  
          <vstov4:description>  
            ContosoOutlookAddIn - Outlook VSTO Add-in   
            created with Visual Studio Tools for Office  
          </vstov4:description>  
          <vstov4:formRegions>  
            <vstov4:formRegion  
                name="OutlookAddIn1.FormRegion1">  
              <vstov4:messageClass name="IPM.Note" />  
              <vstov4:messageClass name="IPM.Contact" />  
              <vstov4:messageClass name="IPM.Appointment" />  
            </vstov4:formRegion>  
          </vstov4:formRegions>  
        </vstov4:appAddIn>  
      </vstov4:customization>  
    </vstov4:customizations>  
  </vstav3:application>  
</vstav3:addIn>  
```  

## <a name="see-also"></a>関連項目  
 [Office ソリューション用アプリケーション マニフェスト](../vsto/application-manifests-for-office-solutions.md)   
 [Office ソリューション用配置マニフェストします。](../vsto/deployment-manifests-for-office-solutions.md)   
 [ClickOnce アプリケーション マニフェスト](/visualstudio/deployment/clickonce-application-manifest)  
