---
title: MSSQLSERVER_2508 | Microsoft Docs
ms.custom: ''
ms.date: 04/04/2017
ms.prod: sql
ms.reviewer: ''
ms.technology: supportability
ms.topic: language-reference
helpviewer_keywords:
- 2508 (Database Engine error)
ms.assetid: c37d40e5-c665-4d66-a727-5cb845634fcc
author: MashaMSFT
ms.author: mathoma
manager: craigg
ms.openlocfilehash: eab10bb8a76a0c82ee03c19c12f907d0a117a648
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2018
ms.locfileid: "47606774"
---
# <a name="mssqlserver2508"></a>MSSQLSERVER_2508
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
  
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|SQL Server|  
|Identificador del evento|2508|  
|Origen del evento|MSSQLSERVER|  
|Componente|SQLEngine|  
|Nombre simbólico|DBCC_OUT_OF_DATE_PAGE_OR_ROW_COUNT|  
|Texto del mensaje|El recuento de %.*ls para el objeto "%.\*ls", id. de índice %d, id. de partición %I64d, id. de unidad de asignación %I64d (tipo %.\*ls) no es correcto. Ejecute DBCC UPDATEUSAGE.|  
  
## <a name="explanation"></a>Explicación  
En las versiones de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] anteriores a [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], los valores del recuento de filas por tabla y por índice, y del recuento de páginas pueden llegar a ser incorrectos. Las bases de datos que se crearon en versiones anteriores a [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] pueden contener recuentos incorrectos. DBCC CHECKDB se ha mejorado para detectar estos errores y devuelve este mensaje de advertencia cuando se encuentra el error.  
  
## <a name="user-action"></a>Acción del usuario  
Ejecute DBCC UPDATEUSAGE con el objeto o índice especificado, o con la base de datos que contiene el objeto para corregir los recuentos no válidos.  
  
