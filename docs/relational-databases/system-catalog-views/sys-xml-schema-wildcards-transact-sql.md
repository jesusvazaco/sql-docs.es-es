---
title: Sys.xml_schema_wildcards (Transact-SQL) | Documentos de Microsoft
ms.custom: 
ms.date: 06/10/2016
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: system-catalog-views
ms.reviewer: 
ms.suite: sql
ms.technology: database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- sys.xml_schema_wildcards
- sys.xml_schema_wildcards_TSQL
- xml_schema_wildcards
- xml_schema_wildcards_TSQL
dev_langs: TSQL
helpviewer_keywords: sys.xml_schema_wildcards catalog view
ms.assetid: 7cedfe9a-e99e-4777-8a28-98674b6e5cff
caps.latest.revision: "30"
author: douglaslMS
ms.author: douglasl
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: f4c30d9d2cf3c97994d37e831b708367556b6d48
ms.sourcegitcommit: 44cd5c651488b5296fb679f6d43f50d068339a27
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/17/2017
---
# <a name="sysxmlschemawildcards-transact-sql"></a>sys.xml_schema_wildcards (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Devuelve una fila por cada componente del esquema XML que es un comodín de atributo (**tipo** de **V**) o comodín de elementos (**tipo** de **W**), ambos con **symbol_space** de **N**.  
  
|Nombre de columna|Tipo de datos|Description|  
|-----------------|---------------|-----------------|  
|**\<hereda columnas >**||Hereda columnas de [sys.xml_schema_components](../../relational-databases/system-catalog-views/sys-xml-schema-components-transact-sql.md).|  
|**process_content**|**Char (1)**|Indica cómo se procesa el contenido.<br /><br /> S = Validación estricta (debe validarse)<br /><br /> L = Validación flexible (validar si es posible)<br /><br /> P = Omitir validación|  
|**process_content_desc**|**nvarchar (60)**|Descripción de cómo se procesa el contenido.<br /><br /> **STRICT_VALIDATION**<br /><br /> **LAX_VALIDATION**<br /><br /> **SKIP_VALIDATION**|  
|**disallow_namespaces**|**bit**|0 = los espacios de nombres enumerados en [sys.xml_schema_wildcard_namespaces](../../relational-databases/system-catalog-views/sys-xml-schema-wildcard-namespaces-transact-sql.md) son los únicos permitidos.<br /><br /> 1 = Los espacios de nombres son los únicos que no se permiten.|  
  
## <a name="permissions"></a>Permissions  
 [!INCLUDE[ssCatViewPerm](../../includes/sscatviewperm-md.md)] Para obtener más información, consulte [Metadata Visibility Configuration](../../relational-databases/security/metadata-visibility-configuration.md).  
  
## <a name="see-also"></a>Vea también  
 [Vistas de catálogo &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/catalog-views-transact-sql.md)   
 [Esquemas XML &#40; Sistema de tipo XML &#41; Vistas de catálogo &#40; Transact-SQL &#41;](../../relational-databases/system-catalog-views/xml-schemas-xml-type-system-catalog-views-transact-sql.md)  
  
  