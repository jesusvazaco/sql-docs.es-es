---
title: MSSQLSERVER_9524 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- database-engine
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- 9524 (Database Engine error)
ms.assetid: 12da7931-e124-4466-889c-046f1b7b7bfd
caps.latest.revision: 9
author: craigg-msft
ms.author: craigg
manager: jhubbard
ms.openlocfilehash: 8b64e4226d34c1e4541c1bac064e644c69491311
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2018
ms.locfileid: "36200354"
---
# <a name="mssqlserver9524"></a>MSSQLSERVER_9524
    
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|SQL Server|  
|Identificador del evento|9254|  
|Origen del evento|MSSQLSERVER|  
|Componente|SQLEngine|  
|Nombre simbólico|XMLERR_INVALID_COLUMNSET_XML|  
|Texto del mensaje|El contenido XML proporcionado no tiene el formato XML requerido para conjuntos de columnas dispersas.|  
  
## <a name="explanation"></a>Explicación  
 Se ha intentado modificar un conjunto de columnas. El contenido XML de un conjunto de columnas debe satisfacer las restricciones de formato correspondientes. El formato general de un conjunto de columnas es el siguiente:  
  
 `<column_name_1>value1</column_name_1><column_name_2>value2</column_name_2>...`  
  
 Para obtener más información sobre conjuntos de columnas, vea el tema "Usar conjuntos de columnas" en los Libros en pantalla de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].  
  
## <a name="user-action"></a>Acción del usuario  
 Corrija el formato del contenido XML del conjunto de columnas en la instrucción.  
  
  