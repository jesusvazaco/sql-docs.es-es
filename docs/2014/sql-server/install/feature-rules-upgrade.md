---
title: Característica reglas (actualización) | Microsoft Docs
ms.custom: ''
ms.date: 05/24/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- database-engine
ms.topic: conceptual
ms.assetid: 653b15db-a984-4b4b-b224-81b0285b099b
author: mashamsft
ms.author: mathoma
manager: craigg
ms.openlocfilehash: 998ff700a63274c2a57f7e3dc9d6981b2e43bb53
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/02/2018
ms.locfileid: "48193123"
---
# <a name="feature-rules-upgrade"></a>Reglas de características (actualización)
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Programa de instalación valida la configuración del equipo antes de que finalice la operación de instalación. Durante la instalación de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , el sistema analiza el equipo donde se instalará [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y comprueba si existen condiciones que impidan una correcta operación de instalación de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] . Antes de que el programa de instalación inicie el Asistente para actualización, recupera el estado de cada elemento. A continuación, compara el resultado con las condiciones necesarias y proporciona instrucciones para evitar problemas de bloqueo.  
  
 La comprobación de la configuración del sistema genera un informe que contiene una descripción breve de cada regla ejecutada y el estado de ejecución. El informe de comprobación de configuración del sistema se encuentra en % programfiles %\\[!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]\120\Setup Bootstrap\Log\\< aaaammdd_hhmm >\\.  
  
 Antes de ejecutar la operación de instalación, revise los temas siguientes:  
  
1.  [Requisitos de hardware y software para instalar SQL Server 2014](hardware-and-software-requirements-for-installing-sql-server.md)  
  
2.  [Características compatibles con las ediciones de SQL Server 2014](../../../2014/getting-started/features-supported-by-the-editions-of-sql-server-2014.md)  
  
3.  [Consideraciones de seguridad para una instalación de SQL Server](../../../2014/sql-server/install/security-considerations-for-a-sql-server-installation.md)  
  
4.  [Versiones en idioma local en SQL Server](../../../2014/sql-server/install/local-language-versions-in-sql-server.md)  
  
 Otras referencias:  
  
1.  [Actualizaciones de ediciones y versiones admitidas](../../database-engine/install-windows/supported-version-and-edition-upgrades.md)  
  
2.  [Antes de instalar los clústeres de conmutación por error](../failover-clusters/install/before-installing-failover-clustering.md)  
  
## <a name="see-also"></a>Vea también  
 [Reglas de instalación](../../../2014/sql-server/install/install-rules.md)  
  
  
