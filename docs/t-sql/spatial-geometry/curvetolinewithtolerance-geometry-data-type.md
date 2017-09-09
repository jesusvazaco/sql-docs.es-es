---
title: CurveToLineWithTolerance (tipo de datos geometry) | Documentos de Microsoft
ms.custom: 
ms.date: 08/03/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- TSQL
helpviewer_keywords:
- CurveToLineWithTolerance method (geometry)
ms.assetid: 96871075-1998-4cd9-86b1-3fc55577aee4
caps.latest.revision: 16
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: 5120f9c27e6157fd2f19c598ad984e1a3543db94
ms.contentlocale: es-es
ms.lasthandoff: 09/01/2017

---
# <a name="curvetolinewithtolerance-geometry-data-type"></a>CurveToLineWithTolerance (tipo de datos Geometry)
[!INCLUDE[tsql-appliesto-ss2012-asdb-xxxx-xxx_md](../../includes/tsql-appliesto-ss2012-asdb-xxxx-xxx-md.md)]

Devuelve una aproximación poligonal de un **geometry** instancia que contiene los segmentos de arco circular.
  
## <a name="syntax"></a>Sintaxis  
  
```  
  
.CurveToLineWithTolerance ( tolerance, relative )  
```  
  
## <a name="arguments"></a>Argumentos  
 *tolerancia*  
 Es un **doble** expresión que define el error máximo entre el segmento de arco circular original y su aproximación lineal.  
  
 *relativa*  
 Es un **bool** expresión que indica si se usa un máximo relativo para la desviación. Cuando relative está establecido en falso (0), se establece un máximo absoluto para la desviación que puede tener una aproximación lineal. Cuando relative está establecido en true (1), la tolerancia se calcula como un producto del parámetro de tolerancia y el diámetro del cuadro de límite para el objeto espacial.  
  
## <a name="return-types"></a>Tipos devueltos  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]tipo de valor devuelto: **geometry**  
  
 Tipo de valor devuelto de CLR: **SqlGeometry**  
  
## <a name="exceptions"></a>Excepciones  
 Al establecer la tolerancia <= 0 se produce una excepción `ArgumentOutOfRange`.  
  
## <a name="remarks"></a>Comentarios  
 Este método puede especificar una cantidad de tolerancia a errores para los resultantes **LineString**.  
  
 En la siguiente tabla se muestra el tipo de instancia que `CurveToLineWithTolerance()` devuelve para varios tipos.  
  
|Tipo de la instancia que hace la llamada|Tipo espacial devuelto|  
|----------------------------|---------------------------|  
|Instancia de geometría vacía|Vacía **GeometryCollection** instancia|  
|**Punto de** y **MultiPoint**|**Punto** instancia|  
|**MultiPoint**|**Punto de** o **MultiPoint** instancia|  
|**CircularString**, **CompoundCurve**, o **LineString**|**LineString** instancia|  
|**MultiLineString**|**LineString** o **MultiLineString** instancia|  
|**CurvePolygon** y **polígono**|**Polígono** instancia|  
|**MultiPolígono**|**Polígono** o **MultiPolygon** instancia|  
|**GeometryCollection** con una única instancia que no contiene un segmento de arco circular|La instancia que se encuentra en la **GeometryCollection** determina el tipo de la instancia devuelta.|  
|**GeometryCollection** con una instancia del segmento de arco circular unidimensional en el único (**CircularString**, **CompoundCurve**)|**LineString** instancia|  
|**GeometryCollection** con una instancia del segmento de arco circular bidimensional único (**CurvePolygon**)|**Polígono** instancia|  
|**GeometryCollection** con varias instancias unidimensionales|**MultiLineString** instancia|  
|**GeometryCollection** con varias instancias bidimensionales|**MultiPolygon** instancia|  
|**GeometryCollection** con varias instancias de distintas dimensiones|**GeometryCollection** instancia|  
  
## <a name="examples"></a>Ejemplos  
  
### <a name="a-using-different-tolerance-values-on-a-circularstring-instance"></a>A. Utilizar valores de tolerancia diferentes en una instancia de CircularString  
 En el ejemplo siguiente se muestra cómo establecer la tolerancia afecta a la `LineString`instancia devuelta desde un `CircularString` instancia:  
  
 `DECLARE @g geometry;`  
  
 `SET @g = geometry::Parse('CIRCULARSTRING(0 0, 1 2.1082, 3 6.3246, 0 7, -3 6.3246, -1 2.1082, 0 0)');`  
  
 `SELECT @g.CurveToLineWithTolerance(0.1,0).STNumPoints(), @g.CurveToLineWithTolerance(0.01, 0).STNumPoints();`  
  
### <a name="b-using-the-method-on-a-multilinestring-instance-containing-one-linestring"></a>B. Utilizar el método en una instancia de MultiLineString que contiene un LineString  
 En el siguiente ejemplo se muestra lo que se devuelve de una instancia de `MultiLineString` que solo contiene una instancia de `LineString`:  
  
 `DECLARE @g geometry;`  
  
 `SET @g = geometry::Parse('MULTILINESTRING((1 3, 4 8, 6 9))');`  
  
 `SELECT @g.CurveToLineWithTolerance(0.1,0).ToString();`  
  
### <a name="c-using-the-method-on-a-multilinestring-instance-containing-multiple-linestrings"></a>C. Utilizar el método en una instancia de MultiLineString que contiene varios LineString  
 En el siguiente ejemplo se muestra lo que se devuelve de una instancia de `MultiLineString` que contiene más de una instancia de `LineString`:  
  
 `DECLARE @g geometry;`  
  
 `SET @g = geometry::Parse('MULTILINESTRING((1 3, 4 8, 6 9),(4 4, 9 18))');`  
  
 `SELECT @g.CurveToLineWithTolerance(0.1,0).ToString();`  
  
### <a name="d-setting-relative-to-true-for-an-invoking-curvepolygon-instance"></a>D. Establecer relative en true para invocar una instancia de CurvePolygon  
 En el ejemplo siguiente se usa un `CurvePolygon` instancia para llamar a `CurveToLineWithTolerance()` con *relativa* establecido en true:  
  
 `DECLARE @g geometry = 'CURVEPOLYGON(COMPOUNDCURVE(CIRCULARSTRING(0 4, 4 0, 8 4), (8 4, 0 4)))';`  
  
 `SELECT @g.CurveToLineWithTolerance(.5,1).ToString();`  
  
### <a name="e-using-the-method-on-a-geometrycollection-instance"></a>E. Usar el método en una instancia de GeometryCollection  
 En el ejemplo siguiente se llama a `CurveToLineWithTolerance()` en un elemento `GeometryCollection` que contiene una instancia de `CurvePolygon` bidimensional y una instancia de `CircularString` unidimensional. `CurveToLineWithTolerance()` convierte los dos tipos de segmento de arco circular en tipos de segmento de línea y los devuelve en un tipo `GeometryCollection`.  
  
 `DECLARE @g geometry;`  
  
 `SET @g = geometry::Parse('GEOMETRYCOLLECTION(CURVEPOLYGON( COMPOUNDCURVE(CIRCULARSTRING(0 2, 2 0, 4 2), (4 2, 0 2))), CIRCULARSTRING(4 4, 8 6, 9 5))');`  
  
 `SELECT @g.CurveToLineWithTolerance(0.1,0).STNumPoints(), @g.CurveToLineWithTolerance(0.1, 0).ToString();`  
  
## <a name="see-also"></a>Vea también  
 [CurveToLineWithTolerance &#40; tipo de datos geography &#41;](../../t-sql/spatial-geography/curvetolinewithtolerance-geography-data-type.md)   
 [STCurveToLine &#40; tipo de datos geometry &#41;](../../t-sql/spatial-geometry/stcurvetoline-geometry-data-type.md)  
  
  

