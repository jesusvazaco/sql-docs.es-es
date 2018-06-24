---
title: Seguridad del Agente de distribución (replicación punto a punto) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- replication
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- sql12.rep.p2pwizard.DA.f1
ms.assetid: def6bf26-c640-4caf-ad30-05d1e649541d
caps.latest.revision: 13
author: craigg-msft
ms.author: craigg
manager: jhubbard
ms.openlocfilehash: 9a1f52e7fba90bcc03da9ca2f135be41013a29fb
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2018
ms.locfileid: "36199322"
---
# <a name="distribution-agent-security-peer-to-peer-replication"></a>Seguridad del Agente de distribución (replicación punto a punto)
  La página **Seguridad del Agente de distribución** permite especificar las cuentas con las que el Agente de distribución se ejecuta y realiza conexiones con los equipos de una topología punto a punto. Para obtener información sobre los permisos requeridos por los agentes y las prácticas recomendadas que se aplican a la seguridad de replicación, vea [Replication Agent Security Model](security/replication-agent-security-model.md) (Modelo de seguridad del Agente de replicación) y [Replication Security Best Practices](security/replication-security-best-practices.md) (Procedimientos recomendados de seguridad en la replicación).  
  
> [!NOTE]  
>  Si el Agente de distribución de una suscripción ya se ha configurado en una ejecución anterior de este asistente, no se pueden cambiar las credenciales que utiliza en este asistente. Si especifica credenciales nuevas, se omitirán. Para cambiar las credenciales, utilice el cuadro de diálogo **Propiedades de suscripción** . Para más información, consulte [View and Modify Replication Security Settings](security/view-and-modify-replication-security-settings.md).  
  
## <a name="options"></a>Opciones  
 Haga clic en el botón de propiedades (**...**) de la fila de cada suscriptor para tener acceso al cuadro de diálogo **Seguridad del Agente de distribución** . Haga clic en **Ayuda** en el cuadro de diálogo **Seguridad del Agente de distribución** que se muestra para obtener más información sobre los permisos requeridos para las cuentas utilizadas por los agentes.  
  
 Una vez especificadas las opciones en uno de los cuadros de diálogo, la información de conexión del suscriptor aparece en la cuadrícula.  
  
 **Agente para el suscriptor**  
 El nombre de cada elemento del mismo nivel.  
  
 **Base de datos del mismo nivel**  
 La base de datos del mismo nivel que servirá tanto de base de datos de publicaciones como de base de datos de suscripciones.  
  
 **Conexión al distribuidor**  
 Contexto en el que se realiza la conexión al distribuidor. Las conexiones locales se realizan siempre utilizando el contexto de la cuenta de Windows con la que se ejecuta el agente. Este asistente crea suscripciones de inserción (la conexión local es la conexión al distribuidor), por lo que este campo muestra siempre: **Suplantar '\<Dominio>\\<inicioDeSesión>\>'** o **Suplantar '\<Equipo>\\<inicioDeSesión>\>'**.  
  
 **Conexión al suscriptor**  
 Contexto en el que se realiza la conexión al suscriptor. La conexión se puede realizar utilizando el contexto de una cuenta de Windows con la que se ejecute el agente o en el contexto de un inicio de sesión de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] . En el campo se muestra una de las siguientes opciones: **Usar inicio de sesión '\<inicioDeSesión>'**, **Suplantar '\<Dominio>\\<inicioDeSesión\>'** o **Suplantar '\<equipo>\\<inicioDeSesión>\>'**. [!INCLUDE[msCoName](../../includes/msconame-md.md)] recomienda que todas las conexiones se realicen utilizando el contexto de la cuenta de Windows.  
  
## <a name="see-also"></a>Vea también  
 [Administrar una topología punto a punto &#40;programación de la replicación con Transact-SQL&#41;](administration/administer-a-peer-to-peer-topology-replication-transact-sql-programming.md)   
 [Peer-to-Peer Transactional Replication](transactional/peer-to-peer-transactional-replication.md)  
  
  