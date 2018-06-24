---
title: ¿Qué&#39;s nuevos en el generador de informes para SQL Server 2014 | Documentos de Microsoft
ms.custom: ''
ms.date: 05/24/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- reporting-services-native
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8223c19b-4b0d-4b1d-a042-9a726c18e708
caps.latest.revision: 13
author: douglaslM
ms.author: douglasl
manager: mblythe
ms.openlocfilehash: 8bf08740110d2b7517a692e0c7a7f53351767d54
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2018
ms.locfileid: "36203568"
---
# <a name="what39s-new-in-report-builder-for-sql-server-2014"></a>¿Qué&#39;s nuevos en el generador de informes para SQL Server 2014
  [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] presenta diversas características de [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)].  
  
 Para obtener información sobre las características de esta versión para otros [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] productos y tecnologías, vea [What's New en SQL Server 2014](../sql-server/what-s-new-in-sql-server-2016.md).  
  
> [!TIP]  
>  Para obtener la información y los recursos más recientes con respecto a las nuevas características de esta versión, vea [Información adicional sobre las novedades de SQL Server Reporting Services (SSRS)](http://go.microsoft.com/fwlink/?LinkId=207147).  
  
##  <a name="ExcelRenderer"></a> Representador de Excel para Microsoft Excel 2007-2010 y Microsoft Excel 2003  
 La extensión de representación de Excel de [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)], nueva en [!INCLUDE[ssSQL11](../includes/sssql11-md.md)], procesa un informe como un documento de Excel compatible con [!INCLUDE[ofprexcel](../includes/ofprexcel-md.md)] 2007-2010, así como con [!INCLUDE[ofprexcel](../includes/ofprexcel-md.md)] 2003, gracias al Paquete de compatibilidad de Microsoft Office para formatos de archivos de Word, Excel y PowerPoint instalado. El formato es Office Open XML y la extensión de los archivos es .xlsx.  
  
 Esta extensión de representación de Excel elimina las limitaciones de la versión anterior, compatible con Excel 2003. A continuación se indican las mejoras de la extensión de representación:  
  
-   Número máximo de filas por hoja de cálculo: 1.048.576.  
  
-   Número máximo de columnas por hoja de cálculo: 16.384.  
  
-   Número de colores permitido en una hoja de cálculo: aproximadamente 16 millones (color de 24 bits).  
  
-   La compresión ZIP proporciona archivos menores.  
  
 Para obtener más información, vea [Exportar a Microsoft Excel &#40;Generador de informes y SSRS&#41;](report-builder/exporting-to-microsoft-excel-report-builder-and-ssrs.md).  
  
##  <a name="WordRenderer"></a> Representador de Word para Microsoft Word 2007-2010 y Microsoft Word 2003  
 La extensión de representación de Word de [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)], nueva en [!INCLUDE[ssSQL11](../includes/sssql11-md.md)], procesa un informe como un documento de Word compatible con [!INCLUDE[ofprword](../includes/ofprword-md.md)] 2007-2010, así como con [!INCLUDE[ofprword](../includes/ofprword-md.md)] 2003, gracias al Paquete de compatibilidad de [!INCLUDE[msCoName](../includes/msconame-md.md)] Office para formatos de archivos de Word, Excel y PowerPoint instalado. El formato es Office Open XML y la extensión de los archivos es .docx.  
  
 Además de hacer que las características nuevas de Word 2007-2010 estén disponibles en los informes exportados, los archivos *.docx de los informes exportados suelen ser menores. Los informes exportados mediante el representador de Word suelen ser mucho menores que los mismos informes exportados mediante el representador de Word 2003.  
  
 Para obtener más información, vea [Exportar a Microsoft Word &#40;Generador de informes y SSRS&#41;](report-builder/exporting-to-microsoft-word-report-builder-and-ssrs.md).  
  
## <a name="see-also"></a>Vea también  
 [Generador de informes en SQL Server 2014](report-builder/report-builder-in-sql-server-2016.md)  
  
  