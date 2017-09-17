---
title: Colecciones (ASSL) | Documentos de Microsoft
ms.custom: 
ms.date: 03/17/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- analysis-services
- docset-sql-devref
ms.tgt_pltfrm: 
ms.topic: reference
applies_to:
- SQL Server 2016 Preview
helpviewer_keywords:
- collections [Analysis Services Scripting Language]
- Analysis Services Scripting Language, collections
- ASSL, collections
ms.assetid: 072b8c6b-1550-4cab-ae64-ba0e3e60b059
caps.latest.revision: 19
author: Minewiskan
ms.author: owend
manager: erikre
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: f9751d6b4052575c85abf41f745817def8f7ae75
ms.contentlocale: es-es
ms.lasthandoff: 09/01/2017

---
# <a name="collections-assl"></a>Colecciones (ASSL)
  Esta sección de referencia contiene información sobre sintaxis y uso de cada uno de los elementos que actúan como una colección en el esquema del Lenguaje de scripting de Analysis Services (ASSL).  
  
 Aunque el esquema ASSL solamente contiene elementos XML, desde el punto de vista de un programador, los elementos descritos en esta sección se corresponden con colecciones de objetos, como por ejemplo la **dimensiones** y **cubos** colecciones.  
  
 Las colecciones son principalmente colecciones de elementos de objeto, en el que un nombre plural designa la colección (para obtener ejemplos, **cubos**), y la colección contiene elementos designados por el mismo nombre en singular (por ejemplo,  **Cubo**).  
  
 En algunos casos, el esquema no se adhiere a esta regla general. Por ejemplo, el **ClassifiedColumns** colección contiene **ClassifiedColumnID** elementos.  
  
 En otros casos, una colección contiene elementos que se corresponden con propiedades de objetos, no a los objetos. Por ejemplo, el **alias** colección contiene **Alias** propiedades, cada uno de los cuales es un valor de cadena simple.  
  
|Elemento|Description|  
|-------------|-----------------|  
|[Accounts, elemento &#40; ASSL &#41;](../../../analysis-services/scripting/collections/accounts-element-assl.md)|Contiene la colección de tipos de cuenta que se definen en un [base de datos](../../../analysis-services/scripting/objects/database-element-assl.md) elemento.|  
|[Actions, elemento &#40; ASSL &#41;](../../../analysis-services/scripting/collections/actions-element-assl.md)|Contiene la colección de acciones para un [cubo](../../../analysis-services/scripting/objects/cube-element-assl.md) o [perspectiva](../../../analysis-services/scripting/objects/perspective-element-assl.md) elemento.|  
|[Aggregationdesigns, elemento &#40; ASSL &#41;](../../../analysis-services/scripting/collections/aggregationdesigns-element-assl.md)|Contiene la colección de diseños de agregaciones que se pueden compartir en varias particiones de una base de datos.|  
|[Aggregationinstances, elemento &#40; ASSL &#41;](../../../analysis-services/scripting/collections/aggregationinstances-element-assl.md)|Contiene la colección de instancias de agregación que se definen en un [partición](../../../analysis-services/scripting/objects/partition-element-assl.md) elemento.|  
|[Aggregations, elemento &#40; ASSL &#41;](../../../analysis-services/scripting/collections/aggregations-element-assl.md)|Contiene la colección de agregaciones definida para un [AggregationDesign](../../../analysis-services/scripting/objects/aggregationdesign-element-assl.md) elemento.|  
|[AlgorithmParameters, elemento &#40; ASSL &#41;](../../../analysis-services/scripting/collections/algorithmparameters-element-assl.md)|Contiene la colección de parámetros para el algoritmo usado por un [MiningModel](../../../analysis-services/scripting/objects/miningmodel-element-assl.md) elemento.|  
|[Aliases, elemento &#40; ASSL &#41;](../../../analysis-services/scripting/collections/aliases-element-assl.md)|Contiene la colección de [Alias](../../../analysis-services/scripting/properties/alias-element-assl.md) elementos asociados a un [cuenta](../../../analysis-services/scripting/objects/account-element-assl.md) elemento|  
|[Allmembertranslations, elemento &#40; ASSL &#41;](../../../analysis-services/scripting/collections/allmembertranslations-element-assl.md)|Contiene la colección de [traducción](../../../analysis-services/scripting/objects/translation-element-assl.md) elementos para el título del miembro All de un [jerarquía](../../../analysis-services/scripting/objects/hierarchy-element-assl.md) elemento.|  
|[Annotations, elemento &#40; ASSL &#41;](../../../analysis-services/scripting/collections/annotations-element-assl.md)|Contiene la colección de [anotación](../../../analysis-services/scripting/objects/annotation-element-assl.md) elementos asociados con el elemento primario.|  
|[Assemblies, elemento &#40; ASSL &#41;](../../../analysis-services/scripting/collections/assemblies-element-assl.md)|Contiene la colección de [ensamblado](../../../analysis-services/scripting/objects/assembly-element-assl.md) elementos asociados a un [Server](../../../analysis-services/scripting/objects/server-element-assl.md) elemento o un [base de datos](../../../analysis-services/scripting/objects/database-element-assl.md) elemento.|  
|[Attributeallmembertranslations, elemento &#40; ASSL &#41;](../../../analysis-services/scripting/collections/attributeallmembertranslations-element-assl.md)|Contiene la colección de traducciones para el título del miembro All de la dimensión.|  
|[Attributepermissions, elemento &#40; ASSL &#41;](../../../analysis-services/scripting/collections/attributepermissions-element-assl.md)|Contiene la colección de permisos de atributo para las personas [rol](../../../analysis-services/scripting/objects/role-element-assl.md) elemento en una dimensión concreta de un [cubo](../../../analysis-services/scripting/objects/cube-element-assl.md) elemento.|  
|[AttributeRelationships, elemento &#40; ASSL &#41;](../../../analysis-services/scripting/collections/attributerelationships-element-assl.md)|Contiene la colección de [AttributeRelationship](../../../analysis-services/scripting/objects/attributerelationship-element-assl.md) elementos para el atributo.|  
|[Elemento Attributes &#40; ASSL &#41;](../../../analysis-services/scripting/collections/attributes-element-assl.md)|Contiene la colección de atributos de la dimensión asociada.|  
|[Elemento Blocks &#40; ASSL &#41;](../../../analysis-services/scripting/collections/blocks-element-assl.md)|Contiene la colección de bloques de datos binarios que representan el contenido binario de un [ClrAssemblyFile](../../../analysis-services/scripting/data-type/clrassemblyfile-data-type-assl.md) elemento.|  
|[Calculationproperties, elemento &#40; ASSL &#41;](../../../analysis-services/scripting/collections/calculationproperties-element-assl.md)|Contiene la colección de [CalculationProperty](../../../analysis-services/scripting/objects/calculationproperty-element-assl.md) elementos asociados a un [MdxScript](../../../analysis-services/scripting/objects/mdxscript-element-assl.md) elemento.|  
|[Elemento calculations &#40; ASSL &#41;](../../../analysis-services/scripting/collections/calculations-element-assl.md)|Contiene la colección de [PerspectiveCalculation](../../../analysis-services/scripting/data-type/perspectivecalculation-data-type-assl.md) elementos asociados a un [perspectiva](../../../analysis-services/scripting/objects/perspective-element-assl.md) elemento.|  
|[Cellpermissions, elemento &#40; ASSL &#41;](../../../analysis-services/scripting/collections/cellpermissions-element-assl.md)|Contiene la colección de permisos para las celdas en el asociado [cubo](../../../analysis-services/scripting/objects/cube-element-assl.md) elemento.|  
|[Elemento ClassifiedColumns &#40; ASSL &#41;](../../../analysis-services/scripting/collections/classifiedcolumns-element-assl.md)|Contiene la colección de columnas relacionadas clasificadas por el [ScalarMiningStructureColumn](../../../analysis-services/scripting/data-type/scalarminingstructurecolumn-data-type-assl.md) elemento.|  
|[Columns, elemento &#40; ASSL &#41;](../../../analysis-services/scripting/collections/columns-element-assl.md)|Contiene la colección de columnas asociada al elemento primario.|  
|[Commands, elemento &#40; ASSL &#41;](../../../analysis-services/scripting/collections/commands-element-assl.md)|Contiene la colección de elementos [Command](../../../analysis-services/scripting/objects/command-element-assl.md) asociada a un elemento [MdxScript](../../../analysis-services/scripting/objects/mdxscript-element-assl.md) .|  
|[Cubepermissions, elemento &#40; ASSL &#41;](../../../analysis-services/scripting/collections/cubepermissions-element-assl.md)|Contiene la colección de permisos aplicable a una [cubo](../../../analysis-services/scripting/objects/cube-element-assl.md) elemento.|  
|[Cubes, elemento &#40; ASSL &#41;](../../../analysis-services/scripting/collections/cubes-element-assl.md)|Contiene la colección de [cubo](../../../analysis-services/scripting/objects/cube-element-assl.md) elementos asociados a un [base de datos](../../../analysis-services/scripting/objects/database-element-assl.md) elemento.|  
|[Databasepermissions, elemento &#40; ASSL &#41;](../../../analysis-services/scripting/collections/databasepermissions-element-assl.md)|Contiene la colección de [DatabasePermission](../../../analysis-services/scripting/objects/databasepermission-element-assl.md) elementos asociados a un [base de datos](../../../analysis-services/scripting/objects/database-element-assl.md) elemento.|  
|[Elemento de las bases de datos &#40; ASSL &#41;](../../../analysis-services/scripting/collections/databases-element-assl.md)|Contiene la colección de [base de datos](../../../analysis-services/scripting/objects/database-element-assl.md) elementos asociados a un [Server](../../../analysis-services/scripting/objects/server-element-assl.md) elemento.|  
|[Elemento de orígenes de datos &#40; ASSL &#41;](../../../analysis-services/scripting/collections/datasources-element-assl.md)|Contiene la colección de [DataSourcePermission](../../../analysis-services/scripting/objects/datasourcepermission-element-assl.md) elementos asociados a un [DataSource](../../../analysis-services/scripting/data-type/datasource-data-type-assl.md) tipo de datos.|  
|[Datasourcepermissions, elemento &#40; ASSL &#41;](../../../analysis-services/scripting/collections/datasourcepermissions-element-assl.md)|Contiene la colección de [DataSource](../../../analysis-services/scripting/objects/datasource-element-assl.md) elementos asociados a un [base de datos](../../../analysis-services/scripting/objects/database-element-assl.md) elemento.|  
|[Datasourceviews, elemento &#40; ASSL &#41;](../../../analysis-services/scripting/collections/datasourceviews-element-assl.md)|Contiene la colección de [DataSourceView](../../../analysis-services/scripting/objects/datasourceview-element-assl.md) elementos asociados a un [base de datos](../../../analysis-services/scripting/objects/database-element-assl.md) elemento.|  
|[Dimensionpermissions, elemento &#40; ASSL &#41;](../../../analysis-services/scripting/collections/dimensionpermissions-element-assl.md)|Contiene la colección de permisos aplicable a una [dimensión](../../../analysis-services/scripting/objects/dimension-element-assl.md) elemento o un [CubePermission](../../../analysis-services/scripting/objects/cubepermission-element-assl.md) elemento.|  
|[Dimensions, elemento &#40; ASSL &#41;](../../../analysis-services/scripting/collections/dimensions-element-assl.md)|Contiene la colección de dimensiones asociada al elemento primario.|  
|[Events, elemento &#40; ASSL &#41;](../../../analysis-services/scripting/collections/events-element-assl.md)|Define la colección de elementos de evento que va a capturar un [seguimiento](../../../analysis-services/scripting/objects/trace-element-assl.md).|  
|[Elemento de archivos &#40; ASSL &#41;](../../../analysis-services/scripting/collections/files-element-assl.md)|Contiene la colección de [archivo](../../../analysis-services/scripting/objects/file-element-assl.md) elementos que componen un [ClrAssembly](../../../analysis-services/scripting/data-type/clrassembly-data-type-assl.md) elemento.|  
|[ForeignKeyColumns, elemento &#40; ASSL &#41;](../../../analysis-services/scripting/collections/foreignkeycolumns-element-assl.md)|Contiene la colección de columnas que identifican la unión a la tabla primaria para un origen de datos relacional.|  
|[Elemento Groups &#40; ASSL &#41;](../../../analysis-services/scripting/collections/groups-element-assl.md)|Contiene la colección de grupos de miembros enlazados a un atributo.|  
|[Hierarchies, elemento &#40; ASSL &#41;](../../../analysis-services/scripting/collections/hierarchies-element-assl.md)|Contiene la colección de [jerarquía](../../../analysis-services/scripting/objects/hierarchy-element-assl.md) elementos asociados con el elemento primario.|  
|[Elemento IncrementalProcessingNotifications &#40; ASSL &#41;](../../../analysis-services/scripting/collections/incrementalprocessingnotifications-element-assl.md)|Contiene la colección de [IncrementalProcessingNotification](../../../analysis-services/scripting/objects/incrementalprocessingnotification-element-assl.md) elementos que proporcionan información para la [ProactiveCaching](../../../analysis-services/scripting/objects/proactivecaching-element-assl.md) elemento acerca de las consultas que se ejecutan para determinar el progreso del procesamiento incremental.|  
|[Elemento KeyColumns &#40; ASSL &#41;](../../../analysis-services/scripting/collections/keycolumns-element-assl.md)|Contiene la colección de [KeyColumn](../../../analysis-services/scripting/objects/keycolumn-element-assl.md) definiciones de elementos para un objeto primario.|  
|[KPIs, elemento &#40; ASSL &#41;](../../../analysis-services/scripting/collections/kpis-element-assl.md)|Contiene la colección de [Kpi](../../../analysis-services/scripting/objects/kpi-element-assl.md) elementos asociados con el elemento primario.|  
|[Levels, elemento &#40; ASSL &#41;](../../../analysis-services/scripting/collections/levels-element-assl.md)|Contiene la colección de [nivel](../../../analysis-services/scripting/objects/level-element-assl.md) elementos en una [jerarquía](../../../analysis-services/scripting/objects/hierarchy-element-assl.md) elemento.|  
|[MdxScripts, elemento &#40; ASSL &#41;](../../../analysis-services/scripting/collections/mdxscripts-element-assl.md)|Contiene la colección de [MdxScript](../../../analysis-services/scripting/objects/mdxscript-element-assl.md) elementos asociados a un [cubo](../../../analysis-services/scripting/objects/cube-element-assl.md) elemento.|  
|[Measuregroups, elemento &#40; ASSL &#41;](../../../analysis-services/scripting/collections/measuregroups-element-assl.md)|Contiene la colección de [MeasureGroup](../../../analysis-services/scripting/objects/measuregroup-element-assl.md) elementos asociados con el elemento primario.|  
|[Measures, elemento &#40; ASSL &#41;](../../../analysis-services/scripting/collections/measures-element-assl.md)|Contiene la colección de [medida](../../../analysis-services/scripting/objects/measure-element-assl.md) elementos asociados con el elemento primario.|  
|[Members, elemento &#40; ASSL &#41;](../../../analysis-services/scripting/collections/members-element-assl.md)|Contiene la colección de elementos [Member](../../../analysis-services/scripting/objects/member-element-assl.md) asociada al elemento primario.|  
|[Miningmodelpermissions, elemento &#40; ASSL &#41;](../../../analysis-services/scripting/collections/miningmodelpermissions-element-assl.md)|Contiene la colección de permisos para un [MiningModel](../../../analysis-services/scripting/objects/miningmodel-element-assl.md) elemento.|  
|[Miningmodels, elemento &#40; ASSL &#41;](../../../analysis-services/scripting/collections/miningmodels-element-assl.md)|Contiene la colección de [MiningModel](../../../analysis-services/scripting/objects/miningmodel-element-assl.md) elementos asociados a un [MiningStructure](../../../analysis-services/scripting/objects/miningstructure-element-assl.md).|  
|[Miningstructurepermissions, elemento &#40; ASSL &#41;](../../../analysis-services/scripting/collections/miningstructurepermissions-element-assl.md)|Contiene la colección de permisos en un [MiningStructure](../../../analysis-services/scripting/objects/miningstructure-element-assl.md) elemento.|  
|[Miningstructures, elemento &#40; ASSL &#41;](../../../analysis-services/scripting/collections/miningstructures-element-assl.md)|Contiene la colección de [MiningStructure](../../../analysis-services/scripting/objects/miningstructure-element-assl.md) elementos en una [base de datos](../../../analysis-services/scripting/objects/database-element-assl.md) elemento.|  
|[Modelingflags, elemento &#40; ASSL &#41;](../../../analysis-services/scripting/collections/modelingflags-element-assl.md)|Contiene la colección de [ModelingFlag](../../../analysis-services/scripting/objects/modelingflag-element-assl.md) elementos para una columna en una [MiningStructure](../../../analysis-services/scripting/objects/miningstructure-element-assl.md) o un [MiningModel](../../../analysis-services/scripting/objects/miningmodel-element-assl.md).|  
|[Namingtemplatetranslations, elemento &#40; ASSL &#41;](../../../analysis-services/scripting/collections/namingtemplatetranslations-element-assl.md)|Proporciona una colección de traducciones adaptadas para el [NamingTemplate](../../../analysis-services/scripting/properties/namingtemplate-element-assl.md) elemento del elemento primario [DimensionAttribute](../../../analysis-services/scripting/data-type/dimensionattribute-data-type-assl.md).|  
|[Partitions, elemento &#40; ASSL &#41;](../../../analysis-services/scripting/collections/partitions-element-assl.md)|Contiene la colección de [partición](../../../analysis-services/scripting/objects/partition-element-assl.md) elementos utilizados por un [MeasureGroup](../../../analysis-services/scripting/objects/measuregroup-element-assl.md) elemento o la colección de enlaces de partición que constituyen un fuera de línea [MeasureGroupBinding](../../../analysis-services/scripting/data-type/measuregroupbinding-data-type-out-of-line-assl.md)elemento.|  
|[Perspectives, elemento &#40; ASSL &#41;](../../../analysis-services/scripting/collections/perspectives-element-assl.md)|Contiene la colección de [perspectiva](../../../analysis-services/scripting/objects/perspective-element-assl.md) elementos asociados a un [cubo](../../../analysis-services/scripting/objects/cube-element-assl.md) elemento.|  
|[Elemento QueryNotifications &#40; ASSL &#41;](../../../analysis-services/scripting/collections/querynotifications-element-assl.md)|Contiene la colección de [QueryNotification](../../../analysis-services/scripting/objects/querynotification-element-assl.md) elementos que proporcionan información para la [ProactiveCaching](../../../analysis-services/scripting/objects/proactivecaching-element-assl.md) elemento acerca de las consultas que se ejecutan para determinar si se ha modificado un origen de datos.|  
|[Reportformatparameters, elemento &#40; ASSL &#41;](../../../analysis-services/scripting/collections/reportformatparameters-element-assl.md)|Contiene la colección de los elementos [ReportFormatParameter](../../../analysis-services/scripting/objects/reportformatparameter-element-asl.md) para un elemento [ReportAction](../../../analysis-services/scripting/data-type/reportaction-data-type-assl.md) .|  
|[Reportparameters, elemento &#40; ASSL &#41;](../../../analysis-services/scripting/collections/reportparameters-element-assl.md)|Contiene la colección de [ReportParameter](../../../analysis-services/scripting/objects/reportparameter-element-assl.md) elementos de un [ReportAction](../../../analysis-services/scripting/data-type/reportaction-data-type-assl.md) elemento.|  
|[Elemento roles &#40; ASSL &#41;](../../../analysis-services/scripting/collections/roles-element-assl.md)|Contiene la colección de elementos [Role](../../../analysis-services/scripting/objects/role-element-assl.md) definida bajo el elemento primario.|  
|[Serverproperties, elemento &#40; ASSL &#41;](../../../analysis-services/scripting/collections/serverproperties-element-assl.md)|Contiene la colección de [ServerProperty](../../../analysis-services/scripting/objects/serverproperty-element-assl.md) elementos asociados a un [Server](../../../analysis-services/scripting/objects/server-element-assl.md) elemento.|  
|[Tablenotifications, elemento &#40; ASSL &#41;](../../../analysis-services/scripting/collections/tablenotifications-element-assl.md)|Contiene la colección de [TableNotification](../../../analysis-services/scripting/objects/tablenotification-element-assl.md) elementos que proporcionan información para la [ProactiveCaching](../../../analysis-services/scripting/objects/proactivecaching-element-assl.md) elemento sobre las tablas o vistas en un origen de datos que se han modificado.|  
|[Traces, elemento &#40; ASSL &#41;](../../../analysis-services/scripting/collections/traces-element-assl.md)|Contiene la colección de elementos [Trace](../../../analysis-services/scripting/objects/trace-element-assl.md) asociados a un elemento [Server](../../../analysis-services/scripting/objects/server-element-assl.md) .|  
|[Translations, elemento &#40; ASSL &#41;](../../../analysis-services/scripting/collections/translations-element-assl.md)|Contiene la colección de [traducción](../../../analysis-services/scripting/objects/translation-element-assl.md) elementos asociados con el elemento primario.|  
|[Unknownmembertranslations, elemento &#40; ASSL &#41;](../../../analysis-services/scripting/collections/unknownmembertranslations-element-assl.md)|Contiene la colección de traducciones para el título de la [UnknownMember](../../../analysis-services/scripting/properties/unknownmember-element-assl.md) elemento de una dimensión.|  
  
## <a name="see-also"></a>Vea también  
 [Analysis Services Scripting Language jerarquía de elementos XML &#40; ASSL &#41;](../../../analysis-services/scripting/analysis-services-scripting-language-xml-element-hierarchy-assl.md)  
  
  