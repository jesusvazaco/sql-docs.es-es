---
title: sp_droppublication (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 03/17/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: replication
ms.topic: language-reference
f1_keywords:
- sp_droppublication_TSQL
- sp_droppublication
helpviewer_keywords:
- sp_droppublication
ms.assetid: b52b37e6-4fec-40cf-abba-7dce4ff395fd
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: a05845955116454ae23b2cd97e25250dbb1e6331
ms.sourcegitcommit: 7aa6beaaf64daf01b0e98e6c63cc22906a77ed04
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2019
ms.locfileid: "54124095"
---
# <a name="spdroppublication-transact-sql"></a>sp_droppublication (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Quita una publicación y su Agente de instantáneas asociado. Antes de quitar una publicación, es necesario quitar todas las suscripciones. Los artículos de la publicación se quitan automáticamente. Este procedimiento almacenado se ejecuta en el publicador de la base de datos de publicación.  
  
 ![Icono de vínculo de tema](../../database-engine/configure-windows/media/topic-link.gif "Icono de vínculo de tema") [Convenciones de sintaxis de Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Sintaxis  
  
```  
  
sp_droppublication [ @publication= ] 'publication'   
    [ , [ @ignore_distributor = ] ignore_distributor ]  
```  
  
## <a name="arguments"></a>Argumentos  
 [  **@publication=** ] **'**_publicación_**'**  
 Es el nombre de la publicación que se va a quitar. *publicación* es **sysname**, no tiene ningún valor predeterminado. Si **todas** se especifica, se quitan todas las publicaciones de la base de datos de publicación, excepto las que tienen suscripciones.  
  
 [  **@ignore_distributor =** ] *ignore_distributor*  
 [!INCLUDE[ssInternalOnly](../../includes/ssinternalonly-md.md)]  
  
## <a name="return-code-values"></a>Valores de código de retorno  
 **0** (correcto) o **1** (error)  
  
## <a name="remarks"></a>Comentarios  
 **sp_droppublication** se utiliza en la replicación de instantáneas y transaccional.  
  
 **sp_droppublication** quita recursivamente todos los artículos asociados con una publicación y, a continuación, quita la propia publicación. No se puede quitar una publicación si tiene una o más suscripciones. Para obtener información acerca de cómo quitar suscripciones, vea [Delete a Push Subscription](../../relational-databases/replication/delete-a-push-subscription.md) y [Delete a Pull Subscription](../../relational-databases/replication/delete-a-pull-subscription.md).  
  
 Ejecutar **sp_droppublication** quitar una publicación no quita los objetos publicados de la base de datos de publicación o los objetos correspondientes de la base de datos de suscripción. Utilice DROP \<objeto > para quitar estos objetos manualmente si es necesario.  
  
## <a name="permissions"></a>Permisos  
 Solo los miembros de la **sysadmin** rol fijo de servidor puede ejecutar **sp_droppublication**.  
  
## <a name="examples"></a>Ejemplos  
 [!code-sql[HowTo#sp_droppublication](../../relational-databases/replication/codesnippet/tsql/sp-droppublication-trans_1.sql)]  
  
## <a name="see-also"></a>Vea también  
 [Eliminar una publicación](../../relational-databases/replication/publish/delete-a-publication.md)   
 [sp_addpublication &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-addpublication-transact-sql.md)   
 [sp_changepublication &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-changepublication-transact-sql.md)   
 [sp_helppublication &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-helppublication-transact-sql.md)   
 [Procedimientos almacenados de replicación &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/replication-stored-procedures-transact-sql.md)  
  
  
