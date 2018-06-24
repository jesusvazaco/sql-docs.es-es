---
title: Especifique la información de origen (Asistente para dimensiones) | Documentos de Microsoft
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- analysis-services
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- sql12.asvs.dimensionwizard.dimensionmaintable.f1
ms.assetid: 0538b490-5185-49e1-a783-4ce3539a0de5
caps.latest.revision: 26
author: Minewiskan
ms.author: owend
manager: mblythe
ms.openlocfilehash: 1543e73d06d6adaf70f78a5c6c13fdcd748f467a
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2018
ms.locfileid: "36104348"
---
# <a name="specify-source-information-dimension-wizard"></a>Especificar información de origen (Asistente para dimensiones)
  Use la página **Seleccionar la tabla de dimensiones principal** para seleccionar la vista del origen de datos, la tabla de dimensiones principal, las columnas de clave y la columna de nombre de miembro para la dimensión que se va a crear.  
  
 **Para abrir al Asistente para dimensiones**  
  
-   En [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], en el **Explorador de soluciones**, haga clic con el botón derecho en la carpeta **Dimensiones** para un proyecto de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] y, luego, haga clic en **Nueva dimensión**.  
  
## <a name="options"></a>Opciones  
 **vista del origen de datos**  
 Seleccione una vista del origen de datos.  
  
 **Tabla principal**  
 Seleccione una tabla en la vista de origen de datos seleccionada para utilizarla como tabla principal para la dimensión.  
  
 **Columnas de clave**  
 Seleccione las columnas de clave de la tabla especificada en **Tabla principal** para obtener el atributo clave de la dimensión.  
  
> [!NOTE]  
>  Se puede seleccionar más de una columna. Si la tabla contiene una clave principal compuesta, seleccione todas las columnas incluidas en la clave principal compuesta. El orden de las columnas de clave es importante.  
  
 **Columna de nombre**  
 Seleccione la columna de la tabla especificada en **Tabla principal** que proporciona los nombres de los miembros para la dimensión. Cuando se usa una clave compuesta, se debe especificar una columna de nombre. Para crear una columna de nombre para una clave compuesta, recomendamos que cree un cálculo con nombre en la vista del origen de datos que concatena las columnas de clave especificadas. Cuando se usa una clave única, la columna de nombre es opcional.  
  
## <a name="see-also"></a>Vea también  
 [Asistente de dimensiones (Ayuda F1)](dimension-wizard-f1-help.md)   
 [Dimensiones &#40;Analysis Services - datos multidimensionales&#41;](multidimensional-models-olap-logical-dimension-objects/dimensions-analysis-services-multidimensional-data.md)   
 [Dimensiones en modelos multidimensionales](multidimensional-models/dimensions-in-multidimensional-models.md)  
  
  