---
title: "Acceso del código en Reporting Services | Documentos de Microsoft"
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- docset-sql-devref
- reporting-services-native
ms.tgt_pltfrm: 
ms.topic: reference
applies_to:
- SQL Server 2016 Preview
helpviewer_keywords:
- code groups [Reporting Services]
- code access security [Reporting Services]
- permission sets [Reporting Services]
- evidence [Reporting Services]
- code access security [Reporting Services], about code access security
- named permission sets [Reporting Services]
ms.assetid: 97480368-1fc3-4c32-b1b0-63edfb54e472
caps.latest.revision: 30
author: sabotta
ms.author: carlasab
manager: erikre
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0eb007a5207ceb0b023952d5d9ef6d95986092ac
ms.openlocfilehash: bbb9ee191cf97b7b61e99b049faa0753034e9b9e
ms.contentlocale: es-es
ms.lasthandoff: 06/13/2017

---
# <a name="code-access-security-in-reporting-services"></a>Seguridad de acceso del código en Reporting Services
  La seguridad de acceso del código se centra en torno a estos conceptos principales: evidencia, grupos de código y conjuntos de permisos con nombre. En [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)], los componentes Administrador de informes, Diseñador de informes y Servidor de informes tienen cada uno de ellos un archivo de directiva que configura la seguridad de acceso del código para los ensamblados personalizados así como los datos, la entrega, la representación y las extensiones de seguridad. Las secciones siguientes proporcionan información general de seguridad de acceso del código. Para obtener más información sobre los temas tratados en esta sección, vea "Modelo de directiva de seguridad" en la [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] documentación del SDK.  
  
 [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] usa seguridad de acceso del código porque, aunque el servidor de informes está generado sobre tecnología [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)], hay una diferencia sustancial entre una aplicación [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] típica y el servidor de informes. Una aplicación [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] típica no ejecuta código de usuario. En cambio, [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] utiliza una arquitectura abierta y extensible que permite a los usuarios programar con los archivos de definición de informe mediante el **código** elemento del lenguaje de definición de informe y a desarrollar la funcionalidad especializada en un ensamblado personalizado para su uso en informes. Además, los programadores pueden diseñar e implementar extensiones eficaces que mejoran las capacidades del servidor de informes. Con esta eficacia y flexibilidad se hace necesario proporcionar tanta protección y seguridad como sea posible.  
  
 Los programadores de [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] pueden usar cualquier ensamblado de [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] en sus informes y llamar en modo nativo a toda la funcionalidad de ensamblados implementados en la memoria caché de ensamblados global. La única cosa que el servidor de informes puede controlar es qué permisos se proporcionan para las expresiones de informe y los ensamblados personalizados cargados. En [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)], ensamblados personalizados reciben **Execute**-únicamente permisos de forma predeterminada.  
  
## <a name="evidence"></a>Evidencia  
 La evidencia es la información que usa Common Language Runtime (CLR) para determinar una directiva de seguridad para ensamblados de código. La evidencia indica al motor en tiempo de ejecución que el código tiene una característica concreta. Entre los tipos de evidencia normales están las firmas digitales y la ubicación de un ensamblado. La evidencia también puede tener un diseño personalizado para representar otra información que sea significativa para la aplicación.  
  
 Tanto los ensamblados como los dominios de aplicación reciben permisos basándose en la evidencia. Por ejemplo, la ubicación de un ensamblado al que [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] intenta obtener acceso es una forma común de evidencia para los ensamblados sin nombres seguros. Esto se conoce como evidencia de dirección URL. La evidencia de la dirección URL para una extensión de procesamiento de datos personalizada que se implementa en un servidor de informes podría ser "C:\Archivos de programa\Microsoft SQL Server\MSRS10_50.MSSQLSERVER\Reporting Services\ReportServer\bin\Microsoft.Samples.ReportingServices.FsiDataExtension.dll". El nombre seguro o la firma digital de un ensamblado es otra forma común de evidencia. En este caso, la evidencia es la información de clave pública para un ensamblado.  
  
## <a name="code-groups"></a>Grupos de código  
 Un grupo de código es una agrupación lógica de código que tiene una condición concreta para la pertenencia. Todos los códigos que cumplen la condición de pertenencia se incluyen en el grupo. Los administradores configuran una directiva de seguridad administrando los grupos de código y sus conjuntos de permisos asociados.  
  
 Una condición de pertenencia para un grupo de código se basa en la evidencia. Por ejemplo, una pertenencia de dirección URL para un grupo de código se basa en la evidencia de dirección URL. Common Language Runtime (CLR) usa características de identificación como la evidencia de dirección URL para describir el código y para determinar si se cumple la condición de pertenencia de un grupo. Por ejemplo, si la condición de pertenencia de un grupo de código es el "código del ensamblado C:\Archivos de programa\Microsoft SQL Server\MSRS10_50.MSSQLSERVER\Reporting Services\ReportServer\bin\Microsoft.Samples.ReportingServices.FsiDataExtension.dll", el motor en tiempo de ejecución examina la evidencia para determinar si el código proviene de dicha ubicación. Un ejemplo de una entrada de configuración para este tipo de grupo de código podría ser similar al siguiente:  
  
```  
<CodeGroup class="UnionCodeGroup"  
   version="1"  
   PermissionSetName="FullTrust"  
   Name="MyCodeGroup"  
   Description="Code group for my data processing extension">  
      <IMembershipCondition class="UrlMembershipCondition"  
         version="1"  
         Url="C:\Program Files\Microsoft SQL Server\MSRS10_50.MSSQLSERVER\Reporting Services\ReportServer\bin\Microsoft.Samples.ReportingServices.FsiDataExtension.dll"  
       />  
</CodeGroup>  
```  
  
 Debería trabajar con su administrador del sistema o su experto de implementación de aplicaciones para determinar el tipo de seguridad de acceso del código y los grupos de código que requieren sus extensiones de [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] o ensamblados personalizados.  
  
## <a name="named-permission-sets"></a>Conjuntos de permisos con nombre  
 Un conjunto de permisos con nombre es un conjunto de permisos que los administradores pueden asociar a un grupo de código. La mayoría de los conjuntos de permisos con nombre están formados al menos por un permiso, un nombre y una descripción para el conjunto de permisos. Los administradores pueden usar los conjuntos de permisos con nombre para establecer o modificar la directiva de seguridad para grupos de código. Con un conjunto de permisos con nombre se pueden asociar varios grupos de código. El CLR proporciona conjuntos de permisos con nombre integrados; entre éstos se encuentran **nada**, **ejecución**, **Internet**, **intranet local**, **todo**, y **FullTrust**.  
  
> [!NOTE]  
>  Las extensiones personalizadas de datos, entrega, representación y seguridad en [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] debe ejecutarse en el **FullTrust** conjunto de permisos. Trabaje con su administrador del sistema para agregar el grupo de código y las condiciones de pertenencia adecuados para sus extensiones de [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].  
  
 Puede asociar sus propios niveles personalizados de permisos para los ensamblados personalizados que usa con informes. Por ejemplo, si desea permitir a un ensamblado el acceso a un archivo concreto, puede crear un nuevo conjunto de permisos con acceso de E/S de archivo concreto y, a continuación, asignar el conjunto de permisos a su grupo de código. El conjunto de permisos siguiente permite el acceso de solo lectura al archivo MyFile.xml:  
  
```  
<PermissionSet class="NamedPermissionSet"  
   version="1"  
   Name="MyNewFilePermissionSet"  
   Description="A special permission set that grants read access to my file.">  
    <IPermission class="FileIOPermission"  
       version="1"  
       Read="C:\MyFile.xml"/>  
    <IPermission class="SecurityPermission"  
       version="1"  
       Flags="Assertion, Execution"/>  
</PermissionSet>  
```  
  
 Un grupo de código al que concede este conjunto de permisos podría tener un aspecto similar al siguiente:  
  
```  
<CodeGroup class="UnionCodeGroup"  
   version="1"  
   PermissionSetName="MyNewFilePermissionSet"  
   Name="MyNewCodeGroup"  
   Description="A special code group for my custom assembly.">  
   <IMembershipCondition class="UrlMembershipCondition"  
      version="1"  
      Url="C:\Program Files\Microsoft SQL Server\MSRS10_50.MSSQLSERVER\Reporting Services\ReportServer\bin\MyCustomAssembly.dll"/>  
</CodeGroup>  
```  
  
## <a name="see-also"></a>Vea también  
 [Proteger desarrollo &#40; Reporting Services &#41;](../../../reporting-services/extensions/secure-development/secure-development-reporting-services.md)  
  
  