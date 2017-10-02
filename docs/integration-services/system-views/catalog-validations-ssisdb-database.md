---
title: Catalog.validations (base de datos SSISDB) | Documentos de Microsoft
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- integration-services
ms.tgt_pltfrm: 
ms.topic: language-reference
ms.assetid: dbafe110-b480-48f3-b45f-31d71ca68f62
caps.latest.revision: 18
author: douglaslMS
ms.author: douglasl
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 2edcce51c6822a89151c3c3c76fbaacb5edd54f4
ms.openlocfilehash: 2d799fd23c2adef75e3dcf4543e9e0ee6271c9b5
ms.contentlocale: es-es
ms.lasthandoff: 09/26/2017

---
# <a name="catalogvalidations-ssisdb-database"></a>catalog.validations (base de datos de SSISDB)
[!INCLUDE[tsql-appliesto-ss2012-xxxx-xxxx-xxx_md](../../includes/tsql-appliesto-ss2012-xxxx-xxxx-xxx-md.md)]

  Muestra los detalles de todas las validaciones de paquete y proyecto en el catálogo de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].  
  
|Nombre de columna|Tipo de datos|Description|  
|-----------------|---------------|-----------------|  
|validation_id|**bigint**|Identificador (id.) único de la validación.|  
|environment_scope|**Char (1)**|Indica las referencias de entorno que la validación tiene en cuenta. Cuando el valor es `A`, todas las referencias de entorno asociadas con el proyecto se incluyen en la validación. Cuando el valor es `S`, solo se incluye una sola referencia de entorno. Cuando el valor es `D`, no se incluyen referencias de entorno y todos los parámetros deben tener un valor literal predeterminado para pasar la validación.|  
|validate_type|**Char (1)**|Tipo de validación que se llevará a cabo. Los tipos de validación posibles son validación de la dependencia (`D`) o validación completa (`F`). La validación del paquete siempre es la validación completa.|  
|nombreDeCarpeta|**nvarchar (128)**|El nombre de la carpeta que contiene el proyecto correspondiente.|  
|Nombre_proyecto|**nvarchar (128)**|Nombre del proyecto.|  
|project_lsn|**bigint**|Versión del proyecto respecto al que se valida.|  
|use32bitruntime|**bit**|Indica si el motor en tiempo de ejecución de 32 bits se usa para ejecutar el paquete en un sistema operativo de 64 bits. Cuando el valor es `1`, la ejecución se realiza con el tiempo de ejecución de 32 bits. Si el valor es `0`, se realiza la ejecución con el motor en tiempo de ejecución de 64 bits.|  
|reference_id|**bigint**|Identificador único de la referencia del entorno del proyecto que el proyecto usa para hacer referencia a un entorno.|  
|operation_type|**smallint**|El tipo de operación. Las operaciones mostradas en esta vista incluyen la validación del proyecto (`300`) y la validación del paquete (`301`).|  
|object_name|**nvarhcar(260)**|Nombre del objeto.|  
|object_type|**smallint**|Tipo de objeto. El objeto puede ser un proyecto (`20`) o un paquete (`30`).|  
|object_id|**bigint**|Identificador del objeto afectado por la operación.|  
|start_time|**DateTimeOffset(7)**|Hora a la que se inició la operación.|  
|end_time|**datetimeoffsset(7)**|Hora a la que finalizó la operación.|  
|status|**int**|Estado de la operación. Los valores posibles son creado (`1`), en ejecución (`2`), cancelado (`3`), con errores (`4`), pendiente (`5`), finalizado inesperadamente (`6`), correcto (`7`), deteniendo (`8`) y completado (`9`).|  
|caller_sid|**varbinary (85)**|Identificador de seguridad (SID) del usuario si se utilizó Autenticación de Windows para iniciar sesión.|  
|caller_name|**nvarchar (128)**|Nombre de la cuenta que realizó la operación.|  
|process_id|**int**|Identificador de proceso del proceso externo, si es aplicable.|  
|stopped_by_sid|**varbinary (85)**|Identificador de seguridad (SID) del usuario que detuvo la operación.|  
|stopped_by_name|**nvarchar (128)**|Nombre del usuario que detuvo la operación.|  
|server_name|**nvarchar (128)**|Información del servidor Windows y de la instancia asociada a una instancia especificada de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].|  
|machine_name|**nvarchar (128)**|Nombre del equipo en el que se está ejecutando la instancia del servidor.|  
|dump_id|**uniqueidentifier**|Identificador del volcado de ejecución.|  
  
## <a name="remarks"></a>Comentarios  
 Esta vista muestra una fila por cada validación del catálogo de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].  
  
## <a name="permissions"></a>Permissions  
 Esta vista exige uno de los siguientes permisos:  
  
-   Permiso READ en la operación correspondiente  
  
-   La pertenencia a la **ssis_admin** rol de base de datos  
  
-   La pertenencia a la **sysadmin** rol de servidor  
  
> [!NOTE]  
>  Cuando se dispone de permiso para realizar una operación en el servidor, también se dispone de permiso para ver información sobre la operación. Se aplica la seguridad en el nivel de fila; solo se muestran las filas para las que disponga de permiso para ver.  
  
  