---
title: Elemento DiagnosticInformation (ssbdiagnose) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
helpviewer_keywords:
- XML output file format [ssbdiagnose], diagnosticinformation element
- diagnosticinformation element
- ssbdiagnose
ms.assetid: 0cfda544-542c-4cf4-86d2-8031c91b10f6
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: 55da8efd6ee5b330e259ed78bdd152720403f310
ms.sourcegitcommit: 334cae1925fa5ac6c140e0b2c38c844c477e3ffb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/13/2018
ms.locfileid: "53367877"
---
# <a name="diagnosticinformation-element-ssbdiagnose"></a>Elemento DiagnosticInformation (ssbdiagnose)
  El elemento **DiagnosticInformation** contiene todos los elementos que incluyen la información de diagnóstico generada por la utilidad. **DiagnosticInformation** es el elemento raíz de un archivo de salida XML **ssbdiagnostic** .  
  
## <a name="syntax"></a>Sintaxis  
  
```  
  
<DiagnosticInformation>   
    ...   
</DiagnosticInformation>  
```  
  
## <a name="element-attributes"></a>Atributos del elemento  
  
|Attribute|Descripción|  
|---------------|-----------------|  
|`None`|N/D|  
  
## <a name="element-characteristics"></a>Características de los elementos  
  
|Característica|Descripción|  
|--------------------|-----------------|  
|**Tipo y longitud de los datos**|Ninguno.|  
|**Valor predeterminado**|Ninguno.|  
|**Repetición**|Una vez por archivo de salida XML **ssbdiagnose** .|  
  
## <a name="element-relationships"></a>Relaciones del elemento  
  
|Relación|Elementos|  
|------------------|--------------|  
|**Elemento primario**|Ninguno.|  
|**Elementos secundarios**|[Elemento Banner &#40;ssbdiagnose&#41;](banner-element-ssbdiagnose.md)<br /><br /> [Elemento Issue &#40;ssbdiagnose&#41;](issue-element-ssbdiagnose.md)|  
  
## <a name="remarks"></a>Comentarios  
 Para obtener más información acerca de los espacios de nombres XML, vea el artículo sobre [espacios de nombres en un documento XML](https://go.microsoft.com/fwlink/?LinkId=7341) en [!INCLUDE[msCoName](../../includes/msconame-md.md)] MSDN Library.  
  
## <a name="see-also"></a>Vea también  
 [Utilidad ssbdiagnose &#40;Service Broker&#41;](ssbdiagnose-utility-service-broker.md)  
  
  
