---
title: ALTER EVENT SESSION (Transact-SQL) | Documentos de Microsoft
ms.custom: 
ms.date: 08/07/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- ALTER EVENT SESSION
- ALTER_EVENT_SESSION_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- event sessions [SQL Server]
- extended events [SQL Server], Transact-SQL
- ALTER EVENT SESSION statement
ms.assetid: da006ac9-f914-4995-a2fb-25b5d971cd90
caps.latest.revision: 46
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: b6fd062bf55bb2630c436d452d2bab05a2f2d53d
ms.contentlocale: es-es
ms.lasthandoff: 09/01/2017

---
# <a name="alter-event-session-transact-sql"></a>ALTER EVENT SESSION (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx_md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Inicia o detiene una sesión de eventos, o cambia la configuración de una sesión de eventos.  
  
 ![Icono de vínculo de tema](../../database-engine/configure-windows/media/topic-link.gif "Icono de vínculo de tema") [Convenciones de sintaxis de Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Sintaxis  
  
```  
  
ALTER EVENT SESSION event_session_name  
ON SERVER  
{  
    [ [ {  <add_drop_event> [ ,...n] }     
       | { <add_drop_event_target> [ ,...n ] } ]   
    [ WITH ( <event_session_options> [ ,...n ] ) ]  
    ]  
    | [ STATE = { START | STOP } ]  
}  
  
<add_drop_event>::=  
{  
    [ ADD EVENT <event_specifier>   
         [ ( {   
                 [ SET { event_customizable_attribute = <value> [ ,...n ] } ]  
                 [ ACTION ( { [event_module_guid].event_package_name.action_name [ ,...n ] } ) ]  
                 [ WHERE <predicate_expression> ]  
        } ) ]  
   ]   
   | DROP EVENT <event_specifier> }  
  
<event_specifier> ::=  
{  
[event_module_guid].event_package_name.event_name  
}  
  
<predicate_expression> ::=   
{  
    [ NOT ] <predicate_factor> | {( <predicate_expression> ) }   
    [ { AND | OR } [ NOT ] { <predicate_factor> | ( <predicate_expression> ) } ]   
    [ ,...n ]  
}  
  
<predicate_factor>::=   
{  
    <predicate_leaf> | ( <predicate_expression> )  
}  
  
<predicate_leaf>::=  
{  
      <predicate_source_declaration> { = | < > | ! = | > | > = | < | < = } <value>   
    | [event_module_guid].event_package_name.predicate_compare_name ( <predicate_source_declaration>, <value> )   
}  
  
<predicate_source_declaration>::=   
{  
    event_field_name | ( [event_module_guid].event_package_name.predicate_source_name )  
}  
  
<value>::=   
{  
    number | 'string'  
}  
  
<add_drop_event_target>::=  
{  
    ADD TARGET <event_target_specifier>  
        [ ( SET { target_parameter_name = <value> [ ,...n] } ) ]  
    | DROP TARGET <event_target_specifier>  
}  
  
<event_target_specifier>::=  
{  
    [event_module_guid].event_package_name.target_name  
}  
  
<event_session_options>::=  
{  
    [    MAX_MEMORY = size [ KB | MB] ]  
    [ [,] EVENT_RETENTION_MODE = { ALLOW_SINGLE_EVENT_LOSS | ALLOW_MULTIPLE_EVENT_LOSS | NO_EVENT_LOSS } ]  
    [ [,] MAX_DISPATCH_LATENCY = { seconds SECONDS | INFINITE } ]  
    [ [,] MAX_EVENT_SIZE = size [ KB | MB ] ]  
    [ [,] MEMORY_PARTITION_MODE = { NONE | PER_NODE | PER_CPU } ]  
    [ [,] TRACK_CAUSALITY = { ON | OFF } ]  
    [ [,] STARTUP_STATE = { ON | OFF } ]  
}  
```  
  
## <a name="arguments"></a>Argumentos  
  
|||  
|-|-|  
|Término|Definición|  
|*event_session_name*|El nombre de una sesión de eventos existente.|  
|ESTADO = INICIO &#124; DETENER|Inicia o detiene la sesión de eventos. Este argumento solo es válido cuando ALTER EVENT SESSION se aplica a un objeto de sesión de eventos.|  
|Agregar evento \<event_specifier >|Asocia el evento identificado por \<event_specifier > con la sesión de eventos.|
|[*event_module_guid*]*. event_package_name.event_name*|El nombre de un evento en un paquete de eventos, donde.<br /><br /> -   *event_module_guid* es el GUID para el módulo que contiene el evento.<br />-   *event_package_name* es el paquete que contiene el objeto de acción.<br />-   *event_name* es el objeto de evento.<br /><br /> Los eventos aparecen en la vista sys.dm_xe_objects como object_type "event".|  
|Establezca { *event_customizable_attribute*= \<valor > [,...*n*] }|Especifica atributos personalizables del evento. Atributos personalizables aparecen en la vista sys.dm_xe_object_columns como column_type 'customizable' y object_name = *event_name*.|  
|ACCIÓN ({[*event_module_guid*]*. event_package_name.action_name* [ **,**... *n*] } )|Es la acción que se va a asociar a la sesión de eventos, donde:<br /><br /> -   *event_module_guid* es el GUID para el módulo que contiene el evento.<br />-   *event_package_name* es el paquete que contiene el objeto de acción.<br />-   *NombreDeAcción* es el objeto de acción.<br /><br /> Las acciones aparecen en la vista sys.dm_xe_objects como object_type 'action'.|  
|DONDE \<predicate_expression >|Especifica la expresión de predicado usada para determinar si debe procesarse un evento. Si \<predicate_expression > es true, se procesa el evento más acciones y los destinos de la sesión. Si \<predicate_expression > es false, el evento se quita la sesión antes de ser procesados por las acciones y los destinos de la sesión. Las expresiones de predicado se limitan a 3.000 caracteres, lo que limita los argumentos de cadena.|
|*event_field_name*|Es el nombre del campo de evento que identifica el origen del predicado.|  
|[event_module_guid].event_package_name.predicate_source_name|Es el nombre del origen del predicado global, donde:<br /><br /> -   *event_module_guid* es el GUID para el módulo que contiene el evento.<br />-   *event_package_name* es el paquete que contiene el objeto de predicado.<br />-   *predicate_source_name* se define en la vista sys.dm_xe_objects como object_type "pred_source".|  
|[*event_module_guid*]. *event_package_name*. *predicate_compare_name*|Es el nombre del objeto de predicado que se va a asociar al evento, donde:<br /><br /> -   *event_module_guid* es el GUID para el módulo que contiene el evento.<br />-   *event_package_name* es el paquete que contiene el objeto de predicado.<br />-   *predicate_compare_name* es un origen global definido en la vista sys.dm_xe_objects como object_type 'pred_compare'.|  
|DROP EVENT \<event_specifier >|Quita el evento identificado por  *\<event_specifier >*. \<event_specifier > debe ser válido en la sesión de eventos.|  
|Agregar destino \<event_target_specifier >|Asocia el destino identificado por \<event_target_specifier > con la sesión de eventos.|
|[*event_module_guid*]. *event_package_name*. *target_name*|El nombre de un destino en la sesión de eventos, donde:<br /><br /> -   *event_module_guid* es el GUID para el módulo que contiene el evento.<br />-   *event_package_name* es el paquete que contiene el objeto de acción.<br />-   *target_name* es la acción. Las acciones aparecen en la vista sys.dm_xe_objects como object_type 'target'.|  
|Establezca { *target_parameter_name*= \<valor > [,...*n*] }|Establece un parámetro de destino. Parámetros de destino aparecen en la vista sys.dm_xe_object_columns como column_type 'customizable' y object_name = *target_name*.<br /><br /> **NOTA** Si usa el destino de búfer en anillo, le recomendamos que establezca el parámetro de destino max_memory en 2048 kilobytes (KB) para intentar evitar el truncamiento de los datos en la salida XML. Para obtener más información sobre cuándo utilizar los diferentes tipos de destino, vea [SQL Server Extended Events Targets](http://msdn.microsoft.com/library/e281684c-40d1-4cf9-a0d4-7ea1ecffa384).|  
|El destino de eliminación \<event_target_specifier >|Quita el destino identificado por \<event_target_specifier >. \<event_target_specifier > debe ser válido en la sesión de eventos.|  
|EVENT_RETENTION_MODE = { **ALLOW_SINGLE_EVENT_LOSS** &#124; ALLOW_MULTIPLE_EVENT_LOSS &#124; NO_EVENT_LOSS}|Especifica el modo de retención de eventos usado para controlar las pérdidas de eventos.<br /><br /> **ALLOW_SINGLE_EVENT_LOSS**<br /> Puede perderse un evento de la sesión. Se elimina un único evento solo cuando todos los búferes de eventos están llenos. La pérdida de un único evento cuando los búferes de eventos están llenos permite un rendimiento de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] aceptable, al mismo tiempo que minimiza las pérdidas de datos en el flujo de eventos procesado.<br /><br /> ALLOW_MULTIPLE_EVENT_LOSS<br /> En la sesión pueden perderse búferes completos de eventos que contienen varios eventos. El número de eventos perdidos depende del tamaño de memoria asignada a la sesión, el particionamiento de la memoria y el tamaño de los eventos en el búfer. Esta opción minimiza el impacto en el rendimiento del servidor si los búferes de eventos se llenan rápidamente, pero se puede perder un gran número de eventos de la sesión.<br /><br /> NO_EVENT_LOSS<br /> No se permite ninguna pérdida de eventos. Esta opción asegura que se van a retener todos los eventos que aparezcan. Al utilizar esta opción, se obliga a todas las tareas que activan eventos a esperar hasta que haya espacio disponible en un búfer de eventos. Esto puede producir problemas detectables de rendimiento mientras la sesión de eventos está activa. Las conexiones de usuario pueden detenerse a la espera de que se quiten eventos del búfer.|  
|MAX_DISPATCH_LATENCY = { *segundos* segundos &#124; **Infinito** }|Especifica el tiempo que los eventos se almacenan en memoria antes de enviarse a los destinos de la sesión de eventos. El valor de latencia mínimo es de 1 segundo. Sin embargo, puede usarse el valor 0 para especificar la latencia INFINITE. De forma predeterminada, este valor está establecido en 30 segundos.<br /><br /> *segundos* segundos<br /> Tiempo, en segundos, que hay que esperar antes de que empiecen a vaciarse los búferes en los destinos. *segundos* es un número entero.<br /><br /> **INFINITO**<br /> Los búferes se vacían en los destinos solo si están llenos o cuando se cierra la sesión de eventos.<br /><br /> **NOTA** MAX_DISPATCH_LATENCY = 0 SECONDS es equivalente a MAX_DISPATCH_LATENCY = INFINITE.|  
|MAX_EVENT_SIZE =*tamaño* [KB &#124; **MB** ]|Especifica el tamaño máximo permitido para los eventos. MAX_EVENT_SIZE solo se debe establecer para permitir los eventos únicos mayores que MAX_MEMORY; al establecerlo en un valor menor que MAX_MEMORY, se producirá un error. *tamaño* es un número entero y puede tener un valor de megabytes (MB) o kilobytes (KB). Si *tamaño* se especifica en kilobytes, el tamaño mínimo permitido es 64 KB. Cuando se establece MAX_EVENT_SIZE, dos búferes de *tamaño* se crean además de MAX_MEMORY. Esto significa que la memoria total utilizada en búferes de eventos es MAX_MEMORY + 2 * MAX_EVENT_SIZE.|  
|MEMORY_PARTITION_MODE = { **NONE** &#124; PER_NODE &#124; PER_CPU}|Especifica la ubicación en la que se van a crear los búferes de eventos.<br /><br /> **NONE**<br /> Se crea un conjunto único de búferes dentro de la [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instancia.<br /><br /> Por cada nodo: se crea un conjunto de búferes para cada nodo NUMA.<br /><br /> POR CPU: se crea un conjunto de búferes para cada CPU.|  
|TRACK_CAUSALITY = {ON &#124; **OFF** }|Especifica si se va a realizar el seguimiento de la causalidad. Si está habilitado, la causalidad permite correlacionar eventos relacionados en las diferentes conexiones con el servidor.|  
|STARTUP_STATE = {ON &#124; **OFF** }|Especifica si esta sesión de eventos se inicia automáticamente cuando se inicie [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].<br /><br /> Si STARTUP_STATE = ON solo se iniciará la sesión de eventos si [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] se detiene y, a continuación, se reinicia.<br /><br /> EN = se inicia sesión en el inicio del evento.<br /><br /> **DESACTIVAR** = no se inicia sesión en el inicio del evento.|  
  
## <a name="remarks"></a>Comentarios  
 Los argumentos ADD y DROP no se pueden usar en la misma instrucción.  
  
## <a name="permissions"></a>Permissions  
 Necesita el permiso ALTER ANY EVENT SESSION.  
  
## <a name="examples"></a>Ejemplos  
 En el ejemplo siguiente se inicia una sesión de eventos, se obtienen algunas estadísticas de la sesión activa y, a continuación, se agregan dos eventos a la sesión existente.  
  
```  
-- Start the event session  
ALTER EVENT SESSION test_session  
ON SERVER  
STATE = start;  
GO  
-- Obtain live session statistics   
SELECT * FROM sys.dm_xe_sessions;  
SELECT * FROM sys.dm_xe_session_events;  
GO  
  
-- Add new events to the session  
ALTER EVENT SESSION test_session ON SERVER  
ADD EVENT sqlserver.database_transaction_begin,  
ADD EVENT sqlserver.database_transaction_end;  
GO  
```  
  
## <a name="see-also"></a>Vea también  
 [CREATE EVENT SESSION &#40;Transact-SQL&#41;](../../t-sql/statements/create-event-session-transact-sql.md)   
 [DROP EVENT SESSION &#40;Transact-SQL&#41;](../../t-sql/statements/drop-event-session-transact-sql.md)   
 [Destinos de SQL Server Extended Events](http://msdn.microsoft.com/library/e281684c-40d1-4cf9-a0d4-7ea1ecffa384)   
 [Sys.server_event_sessions &#40; Transact-SQL &#41;](../../relational-databases/system-catalog-views/sys-server-event-sessions-transact-sql.md)   
 [Sys.dm_xe_objects &#40; Transact-SQL &#41;](../../relational-databases/system-dynamic-management-views/sys-dm-xe-objects-transact-sql.md)   
 [sys.dm_xe_object_columns &#40;Transact-SQL&#41;](../../relational-databases/system-dynamic-management-views/sys-dm-xe-object-columns-transact-sql.md)  
  
  
