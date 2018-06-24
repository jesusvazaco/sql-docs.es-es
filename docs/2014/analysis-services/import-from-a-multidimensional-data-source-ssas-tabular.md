---
title: Importar datos de un origen de datos multidimensionales (SSAS Tabular) | Documentos de Microsoft
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- analysis-services
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7f0793ea-a4c7-42e9-b722-2164a454ebca
caps.latest.revision: 12
author: Minewiskan
ms.author: owend
manager: mblythe
ms.openlocfilehash: 6ad945994bda3f9198d3e686a3ce52ea02f496fb
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2018
ms.locfileid: "36103208"
---
# <a name="import-from-a-multidimensional-data-source-ssas-tabular"></a>Importar datos de un origen de datos multidimensionales (SSAS tabular)
  Puede usar una base de datos de cubo de Analysis Services como origen de datos para un modelo tabular. Para importar datos de un cubo de Analysis Services, debe definir una consulta MDX para seleccionar los datos que desea importar.  
  
 Cualquier dato contenido en una base de datos de SQL Server Analysis Services se puede importar en un modelo. Puede extraer todo el contenido o parte de una dimensión, u obtener segmentos y agregados del cubo, como la suma de ventas, mes a mes, durante el año actual, etc. No obstante, debería tener presente que todos los datos que se importan de un cubo pierden la información de estructura jerárquica. Por consiguiente, si define una consulta que recupera medidas a lo largo de varias dimensiones, los datos se importarán con cada dimensión en una columna independiente.  
  
 Los cubos de Analysis Services deben ser de la versión SQL Server 2005, SQL Server 2008, SQL Server 2008 R2, [!INCLUDE[ssSQL11](../includes/sssql11-md.md)]o [!INCLUDE[ssSQL14](../includes/sssql14-md.md)].  
  
### <a name="to-import-data-from-an-analysis-services-cube"></a>Para importar datos de un cubo de Analysis Services  
  
1.  En [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], haga clic en el menú **Modelo** y, a continuación, haga clic en **Importar desde el origen de datos**.  
  
2.  En la página **Conectarse a un origen de datos** , seleccione **Microsoft Analysis Services**y, a continuación, haga clic en **Siguiente**.  
  
3.  Siga los pasos en el Asistente para la importación de tablas. Podrá especificar una consulta MDX en la página de **Especificar una consulta MDX** . Para usar el Diseñador de consultas MDX, haga clic en **Diseño**en la página Especificar una consulta MDX.  
  
## <a name="see-also"></a>Vea también  
 [Importar datos &#40;SSAS Tabular&#41;](import-data-ssas-tabular.md)   
 [Orígenes de datos compatibles &#40;SSAS Tabular&#41;](tabular-models/data-sources-supported-ssas-tabular.md)  
  
  