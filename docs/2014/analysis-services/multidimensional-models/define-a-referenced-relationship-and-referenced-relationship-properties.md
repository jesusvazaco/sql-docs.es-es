---
title: Definir relaciones referenciadas y propiedades de las relaciones referenciadas | Documentos de Microsoft
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- analysis-services
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- referenced dimension relationship
- relationships [Analysis Services], referenced dimensions
ms.assetid: 5bb44b41-635b-4398-8fe9-0bfbb142553e
caps.latest.revision: 12
author: Minewiskan
ms.author: owend
manager: mblythe
ms.openlocfilehash: 845ec8020ece6d253d4c025b960081a801123a0c
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2018
ms.locfileid: "36203060"
---
# <a name="define-a-referenced-relationship-and-referenced-relationship-properties"></a>Definir relaciones referenciadas y propiedades de las relaciones referenciadas
  Una relación de dimensión de referencia se define en la pestaña **Uso de dimensiones** del Diseñador de cubos. La relación de dimensión de referencia se define al especificar lo siguiente:  
  
-   La dimensión intermedia con la que se va a combinar. Puede ser una dimensión normal u otra dimensión de referencia.  
  
-   Un atributo de dimensión de referencia que defina el nivel mínimo en el que la dimensión está disponible para la agregación con respecto al grupo de medida.  
  
-   El atributo (clave externa) de la dimensión intermedia que corresponde al atributo de dimensión de referencia.  
  
 Tenga en cuenta que la columna que vincula la dimensión de referencia con la tabla de hechos, que suele ser el atributo clave de la dimensión de referencia, también debe ser definida como un atributo en la dimensión intermedia. Cuando cree una cadena de dimensiones de referencia, comience por crear la relación normal entre la primera dimensión de la cadena y el grupo de medida. A continuación, cree cada relación referenciada adicional en orden. Una relación referenciada solo se puede realizar para una dimensión que tenga una relación existente con el grupo de medida.  
  
 Cuando se crea una relación de dimensión de referencia, el vínculo del atributo de dimensión se materializa de forma predeterminada. El materializar un vínculo del atributo de dimensión hace que, durante el procesamiento, el valor del vínculo entre la tabla de hechos y la dimensión de referencia de cada fila se materialice, o almacene, en la estructura MOLAP de la dimensión. Esto tendrá un efecto poco importante en el rendimiento del proceso y en los requisitos de almacenamiento, pero mejorará el rendimiento de la consulta.  
  
 En una dimensión de referencia, la granularidad se especifica mediante la identificación del atributo que define la relación entre una dimensión de referencia y el grupo de medida correspondiente a la tabla principal de la dimensión. Cuando se encadenan varias dimensiones de referencia, las referencias definen la relación de la dimensión más externa al grupo de medida.  
  
  