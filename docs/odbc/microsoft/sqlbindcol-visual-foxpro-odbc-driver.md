---
title: SQLBindCol (controlador ODBC de Visual FoxPro) | Documentos de Microsoft
ms.custom: 
ms.date: 01/19/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- drivers
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SQLBindCol function [ODBC], Visual FoxPro ODBC Driver
ms.assetid: 984d6605-39ba-4d33-ac94-22625bfa6107
caps.latest.revision: 5
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: 8f08ffe2a80f89040dc148543c2b3a3985b76eca
ms.contentlocale: es-es
ms.lasthandoff: 09/09/2017

---
# <a name="sqlbindcol-visual-foxpro-odbc-driver"></a>SQLBindCol (controlador ODBC de Visual FoxPro)
> [!NOTE]  
>  Este tema contiene información específica del controlador ODBC de Visual FoxPro. Para obtener información general acerca de esta función, vea el tema correspondiente en [referencia de la API de ODBC](../../odbc/reference/syntax/odbc-api-reference.md).  
  
 Soporte técnico: completo  
  
 Conformidad de la API de ODBC: Nivel de núcleo  
  
 Asigna espacio de almacenamiento para una columna de resultados y especifica el tipo del resultado. Cuando [SQLFetch](../../odbc/microsoft/sqlfetch-visual-foxpro-odbc-driver.md) o [SQLExtendedFetch](../../odbc/microsoft/sqlextendedfetch-visual-foxpro-odbc-driver.md) es llama, el controlador coloca los datos para todas las columnas enlazadas en las ubicaciones asignadas. Vea [SQLGetTypeInfo](../../odbc/microsoft/sqlgettypeinfo-visual-foxpro-odbc-driver.md) para la asignación entre los tipos de datos ODBC y Visual FoxPro.  
  
 Para obtener más información, consulte [SQLBindCol](../../odbc/reference/syntax/sqlbindcol-function.md) en el *referencia del programador de ODBC*.