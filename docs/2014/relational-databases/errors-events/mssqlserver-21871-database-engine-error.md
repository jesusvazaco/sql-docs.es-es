---
title: MSSQLSERVER_21871 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 21871 (Database Engine error)
ms.assetid: d3215378-9282-444f-a18b-00b96fd0133d
author: MashaMSFT
ms.author: mathoma
manager: craigg
ms.openlocfilehash: 832ee3caa23a034f1c228d01ff8ec2ceda32de06
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/02/2018
ms.locfileid: "48151030"
---
# <a name="mssqlserver21871"></a>MSSQLSERVER_21871
    
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|SQL Server|  
|Identificador del evento|21871|  
|Origen del evento|MSSQLSERVER|  
|Componente|SQLEngine|  
|Nombre simbólico|SQLErrorNum21871|  
|Texto del mensaje|El publicador %s de la base de datos %s no ha sido redirigido.|  
  
## <a name="explanation"></a>Explicación  
 `sp_validate_replica_hosts_as_publishers` comprueba la tabla MSredirected_publishers de la base de datos de distribución para una entrada para el publicador identificado y la base de datos del publicador.  `sp_validate_replica_hosts_as_publishers` devuelve el error 21871 cuando no se encuentra ninguna entrada.  
  
## <a name="user-action"></a>Acción del usuario  
 `sp_validate_replica_hosts_as_publishers` solo es relevante para los publicadores redirigidos. Si la base de datos del publicador es miembro de un grupo de disponibilidad, use el procedimiento almacenado `sp_redirect_publisher` para asociar el publicador y la base de datos del publicador con el nombre de escucha de grupo de disponibilidad del grupo de disponibilidad.  
  
  
