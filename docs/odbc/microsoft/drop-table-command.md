---
title: Comando DROP TABLE | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
helpviewer_keywords:
- drop table command [ODBC]
ms.assetid: bc50459b-8861-4889-84a9-129ae9065aa8
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 0865502928e98329764ae6085ab2b67aa26f0517
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2018
ms.locfileid: "47852303"
---
# <a name="drop-table-command"></a>Comando DROP TABLE
Quita una tabla de la base de datos especificado con el origen de datos y lo elimina del disco.  
  
 El controlador ODBC de Visual FoxPro admite la sintaxis del lenguaje Visual FoxPro nativa para este comando. Para obtener información específica del controlador, vea la sección Comentarios.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
  
DROP TABLE TableName | FileName | ?  
```  
  
## <a name="settings"></a>Configuración  
 *TableName*  
 Especifica la tabla para quitar de la base de datos especificado con el origen de datos y eliminar del disco.  
  
 *FileName*  
 Especifica una tabla para eliminar del disco libre.  
  
 ?  
 Muestra el cuadro de diálogo Quitar desde el que puede elegir una tabla para quitar de la base de datos especificado con el origen de datos y eliminar del disco.  
  
## <a name="remarks"></a>Comentarios  
 Cuando se emite DROP TABLE, también se quitan todos los índices principales, los valores predeterminados y reglas de validación asociadas a la tabla. DROP TABLE también afecta a otras tablas en la base de datos especificada con el origen de datos si las tablas tienen reglas o las relaciones asociadas con la tabla que se va a quitar. Las relaciones y reglas ya no son válidas cuando se quita la tabla de la base de datos.  
  
## <a name="driver-remarks"></a>Comentarios del controlador  
 Cuando la aplicación envía la instrucción DROP TABLE de SQL de ODBC para el origen de datos, el controlador ODBC de Visual FoxPro convierte el comando en el comando de la tabla de FoxProDROP Visual mediante la sintaxis mostrada en la tabla siguiente.  
  
|Sintaxis de ODBC|Origen de datos|Sintaxis de Visual FoxPro|  
|-----------------|-----------------|--------------------------|  
|DROP TABLE *nombre de la tabla de base*|Base de datos (archivo .dbc)|Quitar tabla *TableName* eliminar|  
||Directorio de tablas libres (archivos)|Borrar *dbfName*<br /><br /> Borrar *cdxName*<br /><br /> Borrar *fptName*|
