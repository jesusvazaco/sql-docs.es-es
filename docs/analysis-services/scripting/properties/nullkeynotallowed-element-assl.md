---
title: Elemento NullKeyNotAllowed (ASSL) | Documentos de Microsoft
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- analysis-services
- docset-sql-devref
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- NullKeyNotAllowed Element
apilocation:
- http://schemas.microsoft.com/analysisservices/2003/engine
apitype: Schema
applies_to:
- SQL Server 2016 Preview
f1_keywords:
- NullKeyNotAllowed
helpviewer_keywords:
- NullKeyNotAllowed element
ms.assetid: 4ece99eb-954b-4da1-add4-dd9efd5fff0a
caps.latest.revision: 35
author: Minewiskan
ms.author: owend
manager: erikre
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: 834a0e3728c99d41db1e7871e2c95eec96d1b922
ms.contentlocale: es-es
ms.lasthandoff: 09/01/2017

---
# <a name="nullkeynotallowed-element-assl"></a>Elemento NullKeyNotAllowed (ASSL)
  Determina cómo el [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] motor de procesamiento controla un error de clave null detectado durante el procesamiento.  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
  
<ErrorConfiguration>  
   ...  
   <NullKeyNotAllowed>...</NullKeyNotAllowed>  
   ...  
</ErrorConfiguration>  
```  
  
## <a name="element-characteristics"></a>Características de los elementos  
  
|Característica|Descripción|  
|--------------------|-----------------|  
|Tipo y longitud de los datos|String (enumeración)|  
|Valor predeterminado|*ReportAndContinue*|  
|Cardinalidad|0-1: Elemento opcional que puede aparecer solo una vez.|  
  
## <a name="element-relationships"></a>Relaciones del elemento  
  
|Relación|Elemento|  
|------------------|-------------|  
|Elemento primario|[ErrorConfiguration](../../../analysis-services/scripting/objects/errorconfiguration-element-assl.md)|  
|Elementos secundarios|Ninguno|  
  
## <a name="remarks"></a>Comentarios  
 Los errores de clave NULL se producen cuando se encuentra un valor NULL en una columna de clave en la que no se permiten valores NULL, lo que provoca que se descarte el registro durante el procesamiento. Sin embargo, este error se produce solo si la [NullProcessing](../../../analysis-services/scripting/properties/nullprocessing-element-assl.md) (elemento) para la **DataItem** antecesor de la **ErrorConfiguration** elemento primario se establece en  *Error*.  
  
 El valor de este elemento se limita a una de las cadenas enumeradas en la tabla siguiente.  
  
|Valor|Description|  
|-----------|-----------------|  
|*IgnoreError*|El procesamiento omite el error y continúa.|  
|*ReportAndContinue*|El procesamiento notifica el error y continúa.|  
|*ReportAndStop*|El procesamiento informa del error y se detiene.|  
  
 La enumeración que corresponde a los valores permitidos para **NullKeyNotAllowed** en el objeto de Analysis Management Objects (AMO) es el modelo <xref:Microsoft.AnalysisServices.ErrorOption>.  
  
## <a name="see-also"></a>Vea también  
 [ErrorConfiguration, elemento &#40; ASSL &#41;](../../../analysis-services/scripting/objects/errorconfiguration-element-assl.md)  
  
  