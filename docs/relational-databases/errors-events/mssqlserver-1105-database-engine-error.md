---
title: MSSQLSERVER_1105 | Microsoft Docs
ms.custom: ''
ms.date: 04/04/2017
ms.prod: sql
ms.reviewer: ''
ms.technology: supportability
ms.topic: language-reference
helpviewer_keywords:
- 1105 (Database Engine error)
ms.assetid: e7f4ad02-8c7f-4bb9-9781-2c86253f2138
author: MashaMSFT
ms.author: mathoma
manager: craigg
ms.openlocfilehash: b8f09ee8dfbee7b7cf92b7ac4ebc56532408a18e
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2018
ms.locfileid: "47706153"
---
# <a name="mssqlserver1105"></a>MSSQLSERVER_1105
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
  
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|SQL Server|  
|Identificador del evento|1105|  
|Origen del evento|MSSQLSERVER|  
|Componente|SQLEngine|  
|Nombre simbólico|NO_MORE_SPACE_IN_FG|  
|Texto del mensaje|No se pudo asignar espacio para el objeto '%.*ls'%.\*ls de la base de datos '%.\*ls' porque el grupo de archivos '%.\*ls' está lleno. Elimine archivos innecesarios, quite objetos del grupo de archivos, agregue archivos adicionales al grupo de archivos o establezca la opción de crecimiento automático para los archivos existentes en el grupo de archivos con el fin de crear espacio en el disco.|  
  
## <a name="explanation"></a>Explicación  
No hay espacio en disco disponible en un grupo de archivos.  
  
## <a name="user-action"></a>Acción del usuario  
Las siguientes acciones pueden crear espacio disponible en el grupo de archivos:  
  
-   Active el crecimiento automático.  
  
-   Agregue más archivos al grupo de archivos.  
  
-   Libere espacio en disco quitando índices o tablas que ya no sean necesarios.  
  
-   Para obtener más información, vea el tema "Solucionar problemas de espacio en disco insuficiente para datos" en los Libros en pantalla de SQL Server.  
  
> [!NOTE]  
> Cuando un índice se encuentra en varios archivos, **ALTER INDEX REORGANIZE** puede devolver el error 1105 si uno de los archivos está lleno. El proceso de reorganización se bloquea cuando el proceso trata de mover filas al archivo que está lleno. Para solucionar esta limitación, realice una operación **ALTER INDEX REBUILD** en lugar de **ALTER INDEX REORGANIZE** o incremente el límite de crecimiento de los archivos que estén llenos.  
  
