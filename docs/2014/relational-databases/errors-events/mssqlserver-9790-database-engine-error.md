---
title: MSSQLSERVER_9790 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 9790 (Database Engine error)
ms.assetid: 83fd379f-5deb-4f97-8cb4-282e3d3fed94
author: MashaMSFT
ms.author: mathoma
manager: craigg
ms.openlocfilehash: 5747a13e60182596610f25dd4ed1243670ff5018
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/02/2018
ms.locfileid: "48151187"
---
# <a name="mssqlserver9790"></a>MSSQLSERVER_9790
    
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|SQL Server|  
|Identificador del evento|9790|  
|Origen del evento|MSSQLSERVER|  
|Componente|SQLEngine|  
|Nombre simbólico|SB3_XMIT_ERROR_ENTRANCE_BROKER_SINGLE_USER|  
|Texto del mensaje|No se puede enrutar el mensaje entrante. La base de datos del sistema MSDB que contiene la información de enrutamiento está en modo SINGLE USER.|  
  
## <a name="explanation"></a>Explicación  
 Se produjo un error al intentar clasificar un mensaje recibido fuera de la conexión porque la base de datos MSDB estaba en modo SINGLE USER.  
  
## <a name="user-action"></a>Acción del usuario  
 Cambie MSDB para que esté en modo MULTI USER con el comando ALTER DATABASE.  
  
  
