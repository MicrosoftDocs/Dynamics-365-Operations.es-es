---
title: Inspeccionar el componente ER configurado para evitar problemas de runtime
description: Este tema explica cómo inspeccionar los componentes de informes electrónicos (ER) configurados para evitar problemas de runtime que puedan ocurrir.
author: NickSelin
ms.date: 08/26/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, ERDataModelDesigner, ERModelMappingTable, ERModelMappingDesigner, EROperationDesigner
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a855619ebd1c41dc3ca583912f758ed8a8f9ceef
ms.sourcegitcommit: 7a2001e4d01b252f5231d94b50945fd31562b2bc
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2021
ms.locfileid: "7488123"
---
# <a name="inspect-the-configured-er-component-to-prevent-runtime-issues"></a>Inspeccionar el componente ER configurado para evitar problemas de runtime

[!include[banner](../includes/banner.md)]

Cada componente de [Informe electrónico (ER)](general-electronic-reporting.md) con [formato](general-electronic-reporting.md#FormatComponentOutbound) configurado y [asignación de modelos](general-electronic-reporting.md#data-model-and-model-mapping-components) puede ser [validado](er-fillable-excel.md#validate-an-er-format) en tiempo de diseño. Durante esta validación, se ejecuta una verificación de coherencia para ayudar a prevenir problemas de runtime que puedan ocurrir, como errores de ejecución y degradación del rendimiento. Para cada problema que se encuentra, la comprobación proporciona la ruta de un elemento problemático. Para algunos problemas, hay una solución automática disponible.

De forma predeterminada, la validación se aplica automáticamente en los siguientes casos para una configuración de ER que contiene los componentes de ER mencionados anteriormente:

- Usted [importa](general-electronic-reporting.md#importing-an-er-component-from-lcs-to-use-it-internally) una [versión](general-electronic-reporting.md#component-versioning) nueva de una configuración de ER en su instancia de Microsoft Dynamics 365 Finance.
- Cambia el [estado](general-electronic-reporting.md#component-versioning) de la configuración de ER configurable de **Borrador** a **Completado**.
- Usted [rebasa](general-electronic-reporting.md#upgrading-a-format-selecting-a-new-version-of-base-format-rebase) una configuración de ER editable aplicando una nueva versión base.

Puede ejecutar explícitamente esta validación. Seleccione una de las siguientes tres opciones y siga los pasos que se proporcionan:

- Opción 1:

    1. Vaya a **Administración de la organización \> Informes electrónicos \> Configuraciones**.
    2. En el árbol de configuraciones del panel izquierdo, seleccione la configuración de ER deseada que contiene el formato ER o el componente de asignación del modelo ER.
    3. En la ficha desplegable **Versiones**, seleccione la versión deseada de la configuración de ER seleccionada.
    4. En el panel de acciones, seleccione **Validar**.

- Opción 2, para un formato ER:

    1. Vaya a **Administración de la organización \> Informes electrónicos \> Configuraciones**.
    2. En el árbol de configuraciones del panel izquierdo, seleccione la configuración de ER deseada que contiene el componente de formato ER.
    3. En la ficha desplegable **Versiones**, seleccione la versión deseada de la configuración de ER seleccionada.
    4. En el panel de acciones, haga clic en **Diseñador**.
    5. En la página **Diseñador de formato**, en el panel de acciones seleccione **Validar**.

- Opción 3, para una asignación de modelo ER:

    1. Vaya a **Administración de la organización \> Informes electrónicos \> Configuraciones**.
    2. En el árbol de configuraciones del panel izquierdo, seleccione la configuración de ER deseada que contiene el componente de asignación del modelo ER.
    3. En la ficha desplegable **Versiones**, seleccione la versión deseada de la configuración de ER seleccionada.
    4. En el panel de acciones, haga clic en **Diseñador**.
    5. En la página **Asignación de modelo a origen de datos** en el Panel acciones, seleccione **Diseñador**.
    6. En la página **Diseñador de asignación de modelo** en el Panel acciones, seleccione **Validar**.

Para omitir la validación cuando se importa la configuración, siga estos pasos.

1. Vaya a **Administración de la organización \> Informes electrónicos \> Configuraciones**.
2. En la página **Configuraciones**, en el panel de acciones, en la pestaña **Configuraciones**, en el grupo **Configuración avanzada**, seleccione **Parámetros de usuario**.
3. Establezca la opción **Validar la configuración después de importar** a **No**.

Para omitir la validación cuando cambia o resuelve el estado de la versión, siga estos pasos.

1. Vaya a **Administración de la organización \> Informes electrónicos \> Configuraciones**.
2. En la página **Configuraciones**, en el panel de acciones, en la pestaña **Configuraciones**, en el grupo **Configuración avanzada**, seleccione **Parámetros de usuario**.
3. Establezca la opción **Omitir la validación en el cambio de estado de la configuración y el cambio de base** a **Sí**.

ER utiliza las siguientes categorías para agrupar las inspecciones de verificación de coherencia:

- **Ejecutabilidad**: inspecciones que detectan problemas críticos que pueden ocurrir en runtime. Estos problemas se encuentran principalmente en un nivel **Error**. 
- **Rendimiento**: inspecciones que detectan problemas que pueden causar una ejecución ineficaz de los componentes ER configurados. Estos problemas se encuentran principalmente en un nivel **Advertencia**.
- **Integridad de los datos**: inspecciones que detectan problemas que pueden causar pérdida de datos o problemas de runtime. Estos problemas se encuentran principalmente en un nivel **Advertencia**.

## <a name="list-of-inspections"></a>Lista de inspecciones

La tabla siguiente proporciona información general de las inspecciones que proporciona ER. Para obtener más información sobre estas inspecciones, utilice los enlaces de la primera columna para ir a las secciones relevantes de este tema. Esas secciones explican los tipos de componentes para los que ER proporciona inspecciones y cómo puede reconfigurar los componentes de ER para ayudar a prevenir problemas.

<table>
<thead>
<tr>
<th>Nombre</th>
<th>Categoría</th>
<th>Nivel</th>
<th>Mensaje</th>
</tr>
</thead>
<tbody>
<tr>
<td><a href='#i1'>Conversión de tipos</a></td>
<td>Ejecutabilidad</td>
<td>Error</td>
<td>
<p>No se puede convertir la expresión de tipo &lt;tipo&gt; al campo de tipo &lt;tipo&gt;.</p>
<p><b>Error de runtime:</b> Excepción para tipo</p>
</td>
</tr>
<tr>
<td><a href='#i2'>Compatibilidad de tipo</a></td>
<td>Ejecutabilidad</td>
<td>Error</td>
<td>
<p>La expresión configurada no se puede utilizar como enlace del elemento de formato actual a una fuente de datos, ya que esta expresión devuelve el valor del tipo de datos &lt;tipo&gt; que está más allá del alcance de los tipos de datos que son compatibles con el elemento de formato actual de tipo &lt;tipo&gt;.</p>
<p><b>Error de runtime:</b> Excepción de tipo</p>
</td>
</tr>
<tr>
<td><a href='#i3'>Falta un elemento de configuración</a></td>
<td>Ejecutabilidad</td>
<td>Error</td>
<td>
<p>Ruta de acceso no encontraa &lt;ruta de acceso&gt;.</p>
<p><b>Error de runtime:</b> Elemento de la configuración &lt;ruta de acceso&gt; no encontrado</p>
</td>
</tr>
<tr>
<td><a href='#i4'>Ejecutabilidad de una expresión con función FILTRO</a></td>
<td>Ejecutabilidad</td>
<td>Error</td>
<td>
<p>La expresión de lista de la función FILTER no es consultable.</p>
<p><b>Error de runtime:</b> No se admite el filtrado. Valide la configuración para obtener más detalles sobre esto.</p>
</td>
</tr>
<tr>
<td rowspan='2'><a href='#i5'>Ejecutabilidad de una fuente de datos GROUPBY</a></td>
<td>Ejecutabilidad</td>
<td>Error</td>
<td>Ruta de acceso &lt;ruta de acceso&gt; no admite consultas.</td>
</tr>
<tr>
<td>Ejecutabilidad</td>
<td>Error</td>
<td>
<p>El grupo por función no se puede ejecutar con la consulta.</p>
<p><b>Error de runtime:</b> El grupo por función no se puede ejecutar con la consulta.</p>
</td>
</tr>
<tr>
<td><a href='#i6'>Ejecutabilidad de una fuente de datos JOIN</a></td>
<td>Ejecutabilidad</td>
<td>Error</td>
<td>
<p>No puede unirse a una lista &lt;ruta de acceso&gt; eso no es un filtro en la consulta.</p>
<p><b>Error de runtime:</b> La función unida a la fuente de datos debe ser una expresión de filtro. El campo calculado se ha llamado incorrectamente.</p>
</td>
</tr>
<tr>
<td><a href='#i7'>Preferibilidad de la función FILTER frente a WHERE</a></td>
<td>Rendimiento</td>
<td>Advertencia</td>
<td>Es preferible usar la función FILTER para la expresión que WHERE desde la perspectiva del desempeño. Seleccione Reparar para reemplazarlo automáticamente.</td>
</tr>
<tr>
<td><a href='#i8'>Preferibilidad de la función ALLITEMSQUERY vs ALLITEMS</a></td>
<td>Rendimiento</td>
<td>Advertencia</td>
<td>Es preferible usar la función ALLITEMSQUERY para la expresión que ALLITEMS desde la perspectiva del desempeño. Seleccione Reparar para reemplazarlo automáticamente.</td>
</tr>
<tr>
<td><a href='#i9'>Consideración de casos de lista vacía</a></td>
<td>Ejecutabilidad</td>
<td>Advertencia</td>
<td>
<p>Lista &lt;ruta de acceso&gt; no tiene ninguna verificación de caso de lista vacía, puede resultar en un error en runtime. Agregue una comprobación para caso de lista vacía.</p>
<p><b>Error de runtime:</b> La lista está vacía en &lt;ruta de acceso&gt;</p>
<p><b><a href='#i9a'>Posible problema</a>:</b> la línea se rellena una vez mientras que un origen de datos desde la que se rellena contiene varios registros</p>
</td>
</tr>
<tr>
<td><a href='#i10'>Ejecutabilidad de una expresión con función FILTRO (caché)</a></td>
<td>Ejecutabilidad</td>
<td>Error</td>
<td>
<p>La función FILTER no se puede aplicar al tipo de origen de datos seleccionado. Un origen de datos del tipo Registros de tabla es aplicable solo cuando no está almacenado en caché y no tiene fuentes de datos anidadas agregadas manualmente.</p>
<p><b>Error de runtime:</b> No se admite el filtrado. Valide la configuración para obtener más detalles sobre esto.</p>
</td>
</tr>
<tr>
<td><a href='#i11'>Falta enlace</a></td>
<td>Ejecutabilidad</td>
<td>Advertencia</td>
<td>
<p>Ruta de acceso &lt;ruta de acceso&gt; no tiene ningún vínculo con ninguna fuente de datos al usar la asignación del modelo.</p>
<p><b>Error de runtime:</b> Ruta de acceso &lt;ruta de acceso&gt; no está vinculada</p>
</td>
</tr>
<tr>
<td><a href='#i12'>Plantilla no vinculada</a></td>
<td>Integridad de los datos</td>
<td>Advertencia</td>
<td>Archivo &lt;nombre&gt; no está vinculado a ningún componente de archivo y se eliminará después de cambiar el estado de la versión de configuración.</td>
</tr>
<tr>
<td><a href='#i13'>Formato no sincronizado</a></td>
<td>Integridad de los datos</td>
<td>Advertencia</td>
<td>Nombre definido &lt;nombre del componente&gt; no existe en la hoja de Excel &lt;nombre de la hoja&gt;</td>
</tr>
<tr>
<td><a href='#i14'>Formato no sincronizado</a></td>
<td>Integridad de datos</td>
<td>Advertencia</td>
<td>
<p>La etiqueta &lt;Control de contenido de Word etiquetado&gt; no existe en el archivo de plantilla de Word</p>
<p><b>Error de runtime:</b> la etiqueta &lt;Control de contenido de Word etiquetado&gt; no existe en el archivo de plantilla de Word.</p>
</td>
</tr>
<tr>
<td><a href='#i15'>Sin asignación predeterminada</a></td>
<td>Integridad de datos</td>
<td>Error</td>
<td>
<p>Existe más de una asignación de modelo para el modelo de datos &lt;nombre del modelo (descriptor raíz)&gt; en las configuraciones &lt;nombres de configuración separados por comas&gt;. Establezca una de las configuraciones como predeterminada</p>
<p><b>Error de runtime:</b> existe más de una asignación de modelo para el &lt;modelo de datos de nombre del modelo (descriptor raíz)&gt; en las configuraciones &lt;nombres de configuración separados por comas&gt;. Establezca una de las configuraciones como predeterminada.</p>
</td>
</tr>
<tr>
<td><a href='#i16'>Configuración incoherente de los componentes de encabezado o pie de página</a></td>
<td>Integridad de datos</td>
<td>Error</td>
<td>
<p>Encabezados/pies de página (&lt;tipo de componente: encabezado o pie de página&gt;) incoherentes</p>
<p><b>Runtime:</b> el último componente configurado se utiliza en tiempo de ejecución si se ejecuta la versión de borrador del formato ER configurado.</p>
</td>
</tr>
<tr>
<td><a href='#i17'>Configuración incoherente del componente de página</a></td>
<td>Integridad de datos</td>
<td>Error</td>
<td>Hay más de dos componentes de rango sin replicación. Elimine los componentes innecesarios.</td>
</tr>
</tbody>
</table>

## <a name="type-conversion"></a><a id="i1"></a>Conversión de tipos

ER comprueba si el tipo de datos de un campo de modelo de datos es compatible con el tipo de datos de una expresión que está configurada como el enlace de ese campo. Si los tipos de datos son incompatibles, se produce un error de validación en el diseñador de asignación del modelo ER. El mensaje que recibe indica que ER no puede convertir una expresión de tipo A en un campo de tipo B.

Los siguientes pasos muestran cómo puede ocurrir este problema.

1. Comience a configurar el modelo de datos ER y los componentes de asignación del modelo ER simultáneamente.
2. En el árbol del modelo de datos, agregue un campo con el nombre **X** y seleccione **Entero** como tipo de datos.

    ![El campo X y el tipo de datos Entero se agregaron al árbol del modo de datos en la página Modelo de datos.](./media/er-components-inspections-01.png)

3. En el diseñador de asignación de datos, en el panel **Orígenes de datos**, agregue un origen de datos del tipo **Campo calculado**.
4. Nombre la nueva fuente de datos **Y** y configúrela para que contenga la expresión `INTVALUE(100)`.
5. Enlazar **X** a **Y**.
6. En el diseñador de modelos de datos, cambie el tipo de datos del campo **X** de **Entero** a **Int64**.
7. Seleccione **Validar** para inspeccionar el componente de asignación del modelo editable en la página **Diseñador de asignación de modelos**.

    ![Validar el componente de asignación del modelo editable en la página Diseñador de asignación de modelos.](./media/er-components-inspections-01.gif)

8. Seleccione **Validar** para inspeccionar el componente de asignación del modelo de la configuración de ER seleccionada en la página **Configuraciones**.

    ![Inspeccionar la asignación del modelo en la página Configuraciones.](./media/er-components-inspections-01a.png)

9. Observe que se produce un error de validación. El mensaje indica que el valor del tipo **Entero** que la expresión `INTVALUE(100)` del origen de datos **Y** devuelve no se puede almacenar en el campo del modelo de datos **X** del tipo **Int64**.

La siguiente ilustración muestra el error de runtime que se produce si ignora la advertencia y selecciona **Ejecutar** para ejecutar un formato que esté configurado para usar la asignación del modelo.

![Errores de runtime en la página del Diseñador de formato.](./media/er-components-inspections-01b.png)

### <a name="automatic-resolution"></a>Resolución automática

No hay ninguna opción disponible para solucionar este problema automáticamente.

### <a name="manual-resolution"></a>Resolución manual

#### <a name="option-1"></a>Opción 1

Actualice la estructura del modelo de datos cambiando el tipo de datos del campo del modelo de datos para que coincida con el tipo de datos de la expresión configurada para el enlace de ese campo. Para el ejemplo anterior, el tipo de datos del campo **X** debe cambiarse de nuevo a **Entero**.

#### <a name="option-2"></a>Opción 2

Actualice la asignación del modelo cambiando la expresión de la fuente de datos que está vinculada con el campo del modelo de datos. Para el ejemplo anterior, la expresión del origen de datos **Y** debe cambiarse a `INT64VALUE(100)`.

## <a name="type-compatibility"></a><a id="i2"></a>Compatibilidad de tipo

ER comprueba si el tipo de datos de un elemento de formato es compatible con el tipo de datos de una expresión que está configurada como el enlace de ese elemento de formato. Si los tipos de datos son incompatibles, se produce un error de validación en el diseñador de Operaciones ER. El mensaje que ha recibido afirma que la expresión configurada no se puede utilizar como enlace del elemento de formato actual a una fuente de datos, ya que esta expresión devuelve un valor del tipo de datos A que está más allá del alcance de los tipos de datos que son compatibles con el elemento de formato actual de tipo B.

Los siguientes pasos muestran cómo puede ocurrir este problema.

1. Comience a configurar el modelo de datos ER y los componentes de formato ER simultáneamente.
2. En el árbol del modelo de datos, agregue un campo con el nombre **X** y seleccione **Entero** como tipo de datos.
3. En el árbol de estructura de formato, agregue un elemento de formato del tipo **Numérico**.
4. Nombre el nuevo elemento de formato **Y**. En el campo **Tipo numérico**, seleccione **Entero** como tipo de datos.
5. Enlazar **X** a **Y**.
6. En el árbol de estructura de formato, cambie el tipo de datos del elemento **Y** de formato de **Entero** a **Int64**.
7. Seleccione **Validar** para inspeccionar el componente de formato editable en la página **Diseñador de formato**.

    ![Validación de la compatibilidad de tipos en la página Diseñador de formatos.](./media/er-components-inspections-02.gif)

8. Observe que se produce un error de validación. El mensaje indica que la expresión configurada solo puede aceptar valores **Int64**. Por tanto, el valor de del campo **X** del modelo de datos del tipo **Entero** no se puede introducir en el elemento de formato **Y**.

### <a name="automatic-resolution"></a>Resolución automática

No hay ninguna opción disponible para solucionar este problema automáticamente.

### <a name="manual-resolution"></a>Resolución manual

#### <a name="option-1"></a>Opción 1

Actualice la estructura del formato cambiando el tipo de datos del elemento de formato **Numérico** para que coincida con el tipo de datos de la expresión que configura para el enlace de ese elemento. En el ejemplo anterior, el valor del **Tipo numérico** del elemento de formato **X** debe cambiarse de nuevo a **Entero**.

#### <a name="option-2"></a>Opción 2

Actualice la asignación de formato del elemento de formato **X** cambiando la expresión de `model.X` a `INT64VALUE(model.X)`.

## <a name="missing-configuration-element"></a><a id="i3"></a>Falta un elemento de configuración

ER comprueba si las expresiones vinculantes contienen solo orígenes de datos que están configurados en el componente ER editable. Por cada enlace que contiene un origen de datos que falta en el componente ER editable, se produce un error de validación en el diseñador de operaciones ER o en el diseñador de mapeo del modelo ER.

Los siguientes pasos muestran cómo puede ocurrir este problema.

1. Comience a configurar el modelo de datos ER y los componentes de asignación del modelo ER simultáneamente.
2. En el árbol del modelo de datos, agregue un campo con el nombre **X** y seleccione **Entero** como tipo de datos.

    ![El árbol de modelo de datos con el campo X y el tipo de datos Entero en la página Modelo de datos.](./media/er-components-inspections-01.png)

3. En el diseñador de asignación de datos, en el panel **Orígenes de datos**, agregue un origen de datos del tipo **Campo calculado**.
4. Nombre la nueva fuente de datos **Y** y configúrela para que contenga la expresión `INTVALUE(100)`.
5. Enlazar **X** a **Y**.
6. En el diseñador de asignación de modelos, en el panel **Orígenes de datos**, elimine el origen de datos **Y**.
7. Seleccione **Validar** para inspeccionar el componente de asignación del modelo editable en la página **Diseñador de asignación de modelos**.

    ![Inspeccione el componente de asignación del modelo ER editable en la página Diseñador de asignación de modelos.](./media/er-components-inspections-03.gif)

8. Observe que se produce un error de validación. El mensaje afirma que la vinculación del campo del modelo de datos **X** contiene la ruta que se refiere al origen de datos **Y**, pero esta fuente de datos no se encuentra.

### <a name="automatic-resolution"></a>Resolución automática

Seleccione **Desenlazar** para solucionar automáticamente este problema eliminando el enlace de origen de datos que falta.

### <a name="manual-resolution"></a>Resolución manual

#### <a name="option-1"></a>Opción 1

Desenlaza el campo **X** del modelo de datos para dejar de referirse al origen de datos **Y** inexistente.

#### <a name="option-2"></a>Opción 2

En el panel **Orígenes de datos** del diseñador de asignación de modelos, agregue de nuevo el origen de datos **Y**.

## <a name="executability-of-an-expression-with-filter-function"></a><a id="i4"></a>Ejecutabilidad de una expresión con función FILTER

La función ER incorporada [FILTRAR](er-functions-list-filter.md) se utiliza para acceder a tablas de aplicaciones, vistas o entidades de datos al realizar una sola llamada SQL para obtener los datos requeridos como una lista de registros. Un origen de datos del tipo **Lista de registros** se utiliza como argumento de esta función y especifica el origen de la aplicación para la llamada. ER comprueba si se puede establecer una consulta SQL directa a una fuente de datos a la que se hace referencia en la función `FILTER`. Si no se puede establecer una consulta directa, se produce un error de validación en el diseñador de mapas del modelo ER. El mensaje que recibe indica que la expresión ER que incluye la función `FILTER` no se puede ejecutar en runtime.

Los siguientes pasos muestran cómo puede ocurrir este problema.

1. Comience a configurar el componente de asignación del modelo ER.
2. Agregue un origen de datos del tipo **Dynamics 365 for Operations \\ Registros de tabla**.
3. Asigne un origen de datos nuevo **Proveedor**. En el campo **Tabla**, seleccione **VendTable** para especificar que este origen de datos solicitará la tabla VendTable.
4. Agregue un origen de datos del tipo **Campo calculado**.
5. Nombre el nuevo origen de datos **FilteredVendor** y configúrelo para que contenga la expresión `FILTER(Vendor, Vendor.AccountNum="US-101")`.
6. Seleccione **Validar** para inspeccionar el componente de asignación del modelo editable en la página **Diseñador de asignación de modelos** y verifique que la expresión `FILTER(Vendor, Vendor.AccountNum="US-101")` en el origen de datos **Proveedor** pueda consultarse en el origen de datos.
7. Modifique el origen de datos **Proveedor** agregando un campo anidado del tipo **Campo calculado** para obtener el número de cuenta de proveedor recortado.
8. Nombre el nuevo campo anidado **$AccNumber** y configúrelo para que contenga la expresión `TRIM(Vendor.AccountNum)`.
9. Seleccione **Validar** para inspeccionar el componente de asignación del modelo editable en la página **Diseñador de asignación de modelos** y verifique que la expresión `FILTER(Vendor, Vendor.AccountNum="US-101")` en el origen de datos **Proveedor** pueda consultarse en el origen de datos.

    ![Verificar que la expresión se puede consultar en la página Diseñador de asignación de modelos.](./media/er-components-inspections-04.gif)

10. Observe que se produce un error de validación, porque el origen de datos **Proveedor** contiene un campo anidado del tipo **Campo calculado** que no permite la expresión del origen de datos **FilteredVendor** se traduzca a la instrucción SQL directa.

La siguiente ilustración muestra el error de runtime que se produce si ignora la advertencia y selecciona **Ejecutar** para ejecutar un formato que esté configurado para usar la asignación del modelo.

![Errores de runtime que ocurren cuando ejecuta el formato editable en la página del diseñador de formato.](./media/er-components-inspections-04a.png)

### <a name="automatic-resolution"></a>Resolución automática

No hay ninguna opción disponible para solucionar este problema automáticamente.

### <a name="manual-resolution"></a>Resolución manual

#### <a name="option-1"></a>Opción 1

En lugar de agregar un campo anidado del tipo **Campo calculado** al origen de datos **Proveedor** datos, agregue el campo anidado **$AccNumber** al origen de datos **FilteredVendor** y configúrelo para que contenga la expresión `TRIM(FilteredVendor.AccountNum)`. De esta manera, la expresión `FILTER(Vendor, Vendor.AccountNum="US-101")` se puede ejecutar en el nivel SQL y calcular el campo anidado **$AccNumber** después.

#### <a name="option-2"></a>Opción 2

Cambiar la expresión del origen de datos **FilteredVendor** de `FILTER(Vendor, Vendor.AccountNum="US-101")` a `WHERE(Vendor, Vendor.AccountNum="US-101")`. No recomendamos que cambie la expresión para una tabla que tiene un gran volumen de datos (tabla transaccional), porque todos los registros se recuperarán y la selección de los registros necesarios se realizará en la memoria. Por lo tanto, este enfoque puede provocar un rendimiento deficiente. Para más información, ver [función WHERE ER](er-functions-list-where.md).

## <a name="executability-of-a-groupby-data-source"></a><a id="i5"></a>Ejecutabilidad de una fuente de datos GROUPBY

El origen de datos **GROUPBY** divide el resultado de la consulta en grupos de registros, generalmente con el propósito de realizar una o más agregaciones en cada grupo. Cada origen de datos **GROUPBY** se puede configurar para que se ejecute en el nivel de la base de datos o en la memoria. Cuando un origen de datos **GROUPBY** está configurado para que se ejecute en el nivel de la base de datos, ER comprueba si se puede establecer una consulta SQL directa a un origen de datos a la que se hace referencia en ese origen de datos. Si no se puede establecer una consulta directa, se produce un error de validación en el diseñador de mapas del modelo ER. El mensaje que recibe indica que el origen de datos configurado **GROUPBY** no se puede ejecutar en runtime.

Los siguientes pasos muestran cómo puede ocurrir este problema.

1. Comience a configurar el componente de asignación del modelo ER.
2. Agregue un origen de datos del tipo **Dynamics 365 for Operations \\ Registros de tabla**.
3. Nombre el nuevo origen de datos **Trans**. En el campo **Tabla**, seleccione **VendTrans** para especificar que este origen de datos solicitará la tabla VendTrans.
4. Agregue un origen de datos del tipo **Agrupado por**.
5. Nombre el nuevo origen de datos **GroupedTrans** y configúrelo de la siguiente manera:

    - Seleccione el origen de datos **Trans** como la fuente de registros que deben agruparse.
    - En el campo **Ubicación de ejecución**, seleccione **Consulta** para especificar que desea ejecutar este origen de datos en el nivel de la base de datos.

    ![Configuración del origen de datos en la página Editar parámetros 'Agrupar por'.](./media/er-components-inspections-05a.gif)

6. Seleccione **Validar** para inspeccionar el componente de asignación del modelo editable en la página **Diseñador de asignación de modelos** y verifique que la expresión configurada **GroupedTrans** pueda consultarse.
7. Modifique el origen de datos **Trans** agregando un campo anidado del tipo **Campo calculado** para obtener el número de cuenta de proveedor recortado.
8. Nombre el nuevo origen de datos **$AccNumber** y configúrelo para que contenga la expresión `TRIM(Trans.AccountNum)`.

    ![Configurar el origen de datos en la página del diseñador de asignación de modelo.](./media/er-components-inspections-05a.png)

9. Seleccione **Validar** para inspeccionar el componente de asignación del modelo editable en la página **Diseñador de asignación de modelos** y verifique que la expresión configurada **GroupedTrans** pueda consultarse.

    ![Validar el componente de asignación del modelos ER y verificar que el origen de datos GroupedTrans pueda consultarse en la página Diseñador de asignación de modelos.](./media/er-components-inspections-05b.png)

10. Observe que se produce un error de validación, porque el origen de datos **Trans** contiene un campo anidado del tipo **Campo calculado** que no permite que la llamada del origen de datos **GroupedTrans** se traduzca a la instrucción SQL directa.

La siguiente ilustración muestra el error de runtime que se produce si ignora la advertencia y selecciona **Ejecutar** para ejecutar un formato que esté configurado para usar la asignación del modelo.

![Errores de runtime que ocurren cuando la advertencia se ignora en la página del diseñador de formato.](./media/er-components-inspections-05c.png)

### <a name="automatic-resolution"></a>Resolución automática

No hay ninguna opción disponible para solucionar este problema automáticamente.

### <a name="manual-resolution"></a>Resolución manual

#### <a name="option-1"></a>Opción 1

En lugar de agregar un campo anidado del tipo **Campo calculado** al origen de datos **Trans**, agregue el campo anidado **$AccNumber** para el elemento **GroupedTrans.lines** del origen de datos **GroupedTrans** y configúrelo para que contenga la expresión `TRIM(GroupedTrans.lines.AccountNum)`. De esta manera, el origen de datos **GroupedTrans** se puede ejecutar en el nivel SQL y calcular el campo anidado **$AccNumber** después.

#### <a name="option-2"></a>Opción 2

Cambie el valor del campo **Ubicación de ejecución** para el origen de datos **GroupedTrans** de **Consulta** a **En memoria**. No recomendamos que cambie el valor para una tabla que tiene un gran volumen de datos (tabla transaccional), porque todos los registros se recuperarán y la agrupación y agregación se realizará en la memoria. Por lo tanto, este enfoque puede provocar un rendimiento deficiente.

## <a name="executability-of-a-join-data-source"></a><a id="i6"></a>Ejecutabilidad de una fuente de datos JOIN

El origen de datos [JOIN](er-join-data-sources.md) combina registros de dos o más tablas de base de datos, según los campos relacionados. Cada origen de datos **JOIN** se puede configurar para que se ejecute en el nivel de la base de datos o en la memoria. Cuando un origen de datos **JOIN** está configurado para que se ejecute en el nivel de la base de datos, ER comprueba si se puede establecer una consulta SQL directa a orígenes de datos a la que se hace referencia en ese origen de datos. Si no se puede establecer una consulta directa SQL con al menos un origen de datos referenciado, se produce un error de validación en el diseñador de mapas del modelo ER. El mensaje que recibe indica que el origen de datos configurado **JOIN** no se puede ejecutar en runtime.

Los siguientes pasos muestran cómo puede ocurrir este problema.

1. Comience a configurar el componente de asignación del modelo ER.
2. Agregue un origen de datos del tipo **Dynamics 365 for Operations \\ Registros de tabla**.
3. Asigne un origen de datos nuevo **Proveedor**. En el campo **Tabla**, seleccione **VendTable** para especificar que este origen de datos solicitará la tabla VendTable.
4. Agregue un origen de datos del tipo **Dynamics 365 for Operations \\ Registros de tabla**.
5. Nombre el nuevo origen de datos **Trans**. En el campo **Tabla**, seleccione **VendTrans** para especificar que este origen de datos solicitará la tabla VendTrans.
6. Agregue una fuente de datos del tipo **Campo calculado** como el campo anidado del origen de datos **Proveedor**.
7. Nombre el nuevo origen de datos **FilteredTrans** y configúrelo para que contenga la expresión `FILTER(Trans, Trans.AccountNum=Vendor.AccountNum)`.
8. Agregue un origen de datos del tipo **Join**.
9. Nombre el nuevo origen de datos **JoinedList** y configúrelo de la siguiente manera:

    1. Añada el origen de datos **Proveedor** como el primer conjunto de registros para unirse.
    2. Agregue el origen de datos **Vendor.FilteredTrans** como el segundo conjunto de registros para unirse. Seleccione **INNER** como el tipo.
    3. En el campo **Ejecutar**, seleccione **Consulta** para especificar que desea ejecutar este origen de datos en el nivel de la base de datos.

    ![Configurar el origen de datos en la página del diseñador de Unir.](./media/er-components-inspections-06a.gif)

10. Seleccione **Validar** para inspeccionar el componente de asignación del modelo editable en la página **Diseñador de asignación de modelos** y verifique que la expresión configurada **JoinedList** pueda consultarse.
11. Cambiar la expresión del origen de datos **Vendor.FilteredTrans** de `FILTER(Trans, Trans.AccountNum=Vendor.AccountNum)` a `WHERE(Trans, Trans.AccountNum=Vendor.AccountNum)`.
12. Seleccione **Validar** para inspeccionar el componente de asignación del modelo editable en la página **Diseñador de asignación de modelos** y verifique que la expresión configurada **JoinedList** pueda consultarse.

    ![Validar el componente de asignación de modelos editable y verificar que el origen de datos JoinedList pueda consultarse en la pagina del diseñador de asignación de modelos.](./media/er-components-inspections-06b.png)

13. Observe que se produce un error de validación, porque la expresión del origen de datos **Vendor.FilteredTrans** no se puede traducir a la llamada SQL directa. Además, la llamada SQL directa no permite la llamada al origen de datos **JoinedList** que se traducirá a la sentencia SQL directa.

    ![Errores de runtime de la validación fallida del origen de datos JoinedList en la página Diseñador de asignación de modelos.](./media/er-components-inspections-06c.png)

La siguiente ilustración muestra el error de runtime que se produce si ignora la advertencia y selecciona **Ejecutar** para ejecutar un formato que esté configurado para usar la asignación del modelo.

![Ejecutar el formato editable en la página Diseñador de formatos.](./media/er-components-inspections-06e.png)

### <a name="automatic-resolution"></a>Resolución automática

No hay ninguna opción disponible para solucionar este problema automáticamente.

### <a name="manual-resolution"></a>Resolución manual

#### <a name="option-1"></a>Opción 1

Cambie la expresión del origen de datos **Vendor.FilteredTrans** de `WHERE(Trans, Trans.AccountNum=Vendor.AccountNum)` de vuelta a `FILTER(Trans, Trans.AccountNum=Vendor.AccountNum)`, como aconsejaba la advertencia.

![Expresión actualizada del origen de datos en la página del diseñador de asignación de modelo.](./media/er-components-inspections-06d.png)

#### <a name="option-2"></a>Opción 2

Cambie el valor del campo **Ejecutar** para el origen de datos **JoinedList** de **Consulta** a **En memoria**. No recomendamos que cambie el valor para una tabla que tiene un gran volumen de datos (tabla transaccional), porque todos los registros se recuperarán y la unión ocurrirá en la memoria. Por lo tanto, este enfoque puede provocar un rendimiento deficiente. Se muestra una advertencia de validación para informarle sobre este riesgo.

## <a name="preferability-of-filter-vs-where-function"></a><a id="i7"></a>Preferibilidad de la función FILTER frente a WHERE

La función ER incorporada [FILTRAR](er-functions-list-filter.md) se utiliza para acceder a tablas de aplicaciones, vistas o entidades de datos al realizar una sola llamada SQL para obtener los datos requeridos como una lista de registros. La función [WHERE](er-functions-list-where.md) recupera todos los registros de la fuente dada y registra la selección en la memoria. Un origen de datos del tipo **Lista de registros** se utiliza como argumento de ambas funciones y especifica un origen para obtener registros. ER comprueba si se puede establecer una llamada SQL directa a una fuente de datos a la que se hace referencia en la función **WHERE**. Si no se puede establecer una llamada directa, se produce una advertencia de validación en el diseñador de mapas del modelo ER. El mensaje que recibe recomienda que utilice la función **FILTER** en lugar de la función **WHERE** para ayudar a mejorar la eficiencia.

Los siguientes pasos muestran cómo puede ocurrir este problema.

1. Comience a configurar el componente de asignación del modelo ER.
2. Agregue un origen de datos del tipo **Dynamics 365 for Operations \\ Registros de tabla**.
3. Nombre el nuevo origen de datos **Trans**. En el campo **Tabla**, seleccione **VendTrans** para especificar que este origen de datos solicitará la tabla VendTrans.
4. Agregue una fuente de datos del tipo **Campo calculado** como el campo anidado del origen de datos **Proveedor**.
5. Nombre el nuevo origen de datos **FilteredTrans** y configúrelo para que contenga la expresión `WHERE(Trans, Trans.AccountNum="US-101")`.
6. Agregue un origen de datos del tipo **Dynamics 365 for Operations \\ Registros de tabla**.
7. Asigne un origen de datos nuevo **Proveedor**. En el campo **Tabla**, seleccione **VendTable** para especificar que este origen de datos solicitará la tabla VendTable.
8. Agregue un origen de datos del tipo **Campo calculado**.
9. Nombre el nuevo origen de datos **FilteredVendor** y configúrelo para que contenga la expresión `WHERE(Vendor, Vendor.AccountNum="US-101")`.
10. Seleccione **Validar** para inspeccionar el componente de asignación del modelo editable en la página **Diseñador de asignación de modelos**.

    ![Inspeccione el componente de asignación del modelo editable en la página Diseñador de asignación de modelos.](./media/er-components-inspections-07a.png)

11. Tenga en cuenta que las advertencias de validación recomiendan que utilice la función **FILTER** en lugar de la función **WHERE** para los orígenes de datos **FilteredVendor** y **FilteredTrans** fuentes de datos.

    ![Recomendación de usar la función FILTRO en lugar de la función DONDE en la página Diseñador de asignación de modelos.](./media/er-components-inspections-07b.png)

### <a name="automatic-resolution"></a>Resolución automática

Seleccione **Reparar** para reemplazar automáticamente la función **WHERE** con la función **FILTER** en la expresión de todos los orígenes de datos que aparecen en la cuadrícula en la pestaña **Advertencias** para este tipo de inspección.

Alternativamente, puede seleccionar la fila para una sola advertencia en la cuadrícula y luego seleccionar **Reparar seleccionado**. En este caso, la expresión se cambia automáticamente solo en el origen de datos que se menciona en la advertencia seleccionada.

![Seleccione Reparar para reemplazar automáticamente la función DONDE con la función FILTROr en la página Diseñador de asignación de modelos.](./media/er-components-inspections-07c.png)

### <a name="manual-resolution"></a>Resolución manual

Puede ajustar manualmente las expresiones de todos los orígenes de datos en la cuadrícula de validación reemplazando la función **WHERE** con la función **FILTER**.

## <a name="preferability-of-allitemsquery-vs-allitems-function"></a><a id="i8"></a>Preferibilidad de la función ALLITEMSQUERY vs ALLITEMS

Las funciones integradas [ALLITEMS](er-functions-list-allitems.md) y [ALLITEMSQUERY](er-functions-list-allitemsquery.md) de ER recuperan un valor aplanado de **Lista de registros** que consta de una lista de registros que representan todos los elementos que coinciden con la ruta especificada. ER comprueba si se puede establecer una llamada SQL directa a una fuente de datos a la que se hace referencia en la función **ALLITEMS**. Si no se puede establecer una llamada directa, se produce una advertencia de validación en el diseñador de mapas del modelo ER. El mensaje que recibe recomienda que utilice la función **ALLITEMSQUERY** en lugar de la función **ALLITEMS** para ayudar a mejorar la eficiencia.

Los siguientes pasos muestran cómo puede ocurrir este problema.

1. Comience a configurar el componente de asignación del modelo ER.
2. Agregue un origen de datos del tipo **Dynamics 365 for Operations \\ Registros de tabla**.
3. Asigne un origen de datos nuevo **Proveedor**. En el campo **Tabla**, seleccione **VendTable** para especificar que este origen de datos solicitará la tabla VendTable.
4. Agregue un origen de datos del tipo **Campo calculado** para obtener registros de varios proveedores.
5. Nombre el nuevo origen de datos **FilteredVendor** y configúrelo para que contenga la expresión `FILTER(Vendor, OR(Vendor.AccountNum="US-101",Vendor.AccountNum="US-102"))`.
6. Agregue un origen de datos del tipo **Campo calculado** para obtener las transacciones de todos los proveedores filtrados.
7. Nombre el nuevo origen de datos **FilteredVendorTrans** y configúrelo para que contenga la expresión `ALLITEMS(FilteredVendor.'<Relations'.'VendTrans.VendTable_AccountNum')`.
8. Seleccione **Validar** para inspeccionar el componente de asignación del modelo editable en la página **Diseñador de asignación de modelos**.

    ![Inspeccione el componente de asignación del modelo editable en la página Diseñador de asignación de modelos.](./media/er-components-inspections-08a.png)

9. Observe que se produce una advertencia de validación. El mensaje recomienda que utilice la función **ALLITEMSQUERY** en lugar de la función **ALLITEMS** función para el origen de datos **FilteredVendorTrans**.

    ![Recomendación de usar la función ALLITEMSQUERY en lugar de la función ALLITEMS en la página Diseñador de asignación de modelos.](./media/er-components-inspections-08b.png)

### <a name="automatic-resolution"></a>Resolución automática

Seleccione **Reparar** para reemplazar automáticamente la función **ALLITEMS** con la función **ALLITEMSQUERY** en la expresión de todos los orígenes de datos que aparecen en la cuadrícula en la pestaña **Advertencias** para este tipo de inspección.

Alternativamente, puede seleccionar la fila para una sola advertencia en la cuadrícula y luego seleccionar **Reparar seleccionado**. En este caso, la expresión se cambia automáticamente solo en el origen de datos que se menciona en la advertencia seleccionada.

![Página del diseñador de asignación de modelos, con Selección de corrección seleccionado.](./media/er-components-inspections-08c.png)

### <a name="manual-resolution"></a>Resolución manual

Puede ajustar manualmente las expresiones de todos los orígenes de datos que se mencionan en la cuadrícula de validación reemplazando la función **ALLITEMS** con la función **ALLITEMSQUERY**.

## <a name="consideration-of-empty-list-cases"></a><a id="i9"></a>Consideración de casos de lista vacía

Puede configurar su componente de asignación de modelo o formato ER para obtener el valor de campo de una fuente de datos del tipo **Lista de registros**. ER verifica si su diseño considera el caso en el que una fuente de datos que se llama no contiene registros (es decir, está vacía), para evitar errores de tiempo de ejecución cuando se obtiene un valor de un campo de un registro inexistente.

Los siguientes pasos muestran cómo puede ocurrir este problema.

1. Comience a configurar los componentes del modelo de datos ER, de asignación del modelo ER y el formato ER simultáneamente.
2. En el árbol del modelo de datos, agregue un elemento raíz que se llame **Root3**.
3. Modifique el elemento **Root3** agregando un elemento anidado del tipo **Lista de registros**.
4. Nombre el nuevo elemento anidado **Proveedor**.
5. Modifique el elemento **Proveedor** de la siguiente manera:

    - Agregue un campo anidado del tipo **Cadena** y nómbrelo **Nombre**.
    - Agregue un campo anidado del tipo **Cadena** y nómbrelo **AccountNumber**.

    ![Agregar campos anidados en la página del modelo de datos.](./media/er-components-inspections-09a.png)

6. En el diseñador de asignación de modelos, en el panel **Orígenes de datos**, agregue un origen de datos al tipo **Dynamics 365 for Operations \\ Registros de tabla**.
7. Asigne un origen de datos nuevo **Proveedor**. En el campo **Tabla**, seleccione **VendTable** para especificar que este origen de datos solicitará la tabla VendTable.
8. Agregue un origen de datos del tipo **General \\ Parámetro de entrada de usuario** para buscar una cuenta de proveedor en el cuadro de diálogo de runtime.
9. Asigne un origen de datos nuevo **RequestedAccountNum**. En el campo **Etiqueta**, introduzca el **Número de cuenta del proveedor**. En el campo **Nombre del tipo de datos de operaciones**, deje el valor predeterminado, **Descripción**.
10. Agregue un origen de datos del tipo **Campo calculado** para filtrar un proveedor al que se consulte.
11. Nombre el nuevo origen de datos **FilteredVendor** y configúrelo para que contenga la expresión `FILTER(Vendor, Vendor.AccountNum=RequestedAccountNum)`.
12. Vincule los elementos del modelo de datos a los orígenes de datos configurados de la siguiente manera:

    - Enlazar **FilteredVendor** a **Proveedor**.
    - Enlazar **FilteredVendor.AccountNum** a **Vendor.AccountNumber**.
    - Enlazar **FilteredVendor.'name()'** a **Vendor.Name**.

    ![Enlazar elementos del modelo de datos en la página del diseñador de asignación de modelo.](./media/er-components-inspections-09b.png)

13. En el árbol de estructura de formato, agregue los siguientes elementos para generar un documento saliente en formato XML que contenga los detalles del proveedor:

    1. Agregue el elemento XML raíz **Instrucción**.
    2. Para el elemento XML **Instrucción**, agregue el elemento XML anidado **Entidad**.
    3. Para el elemento XML **Entidad**, agregue los siguientes atributos XML anidados:

        - Nombre
        - AccountNum

14. Vincule elementos de formato a los orígenes de datos proporcionados de la siguiente manera:

    - Vincule el elemento de formato **Instrucción\\Entidad\\Nombre** al campo de origen de datos **model.Vendor.Name**.
    - Vincule el elemento de formato **Instrucción\\Entidad\\AccountNum** al campo de origen de datos **model.Vendor.AccountNumber**.

15. Seleccione **Validar** para inspeccionar el componente de formato editable en la página **Diseñador de formato**.

    ![Validar los elementos de formato que vinculó a los orígenes de datos en la página Diseñador de formatos.](./media/er-components-inspections-09c.png)

16. Observe que se produce un error de validación. El mensaje indica que se puede generar un error para el formato configurado de los componentes **Instrucción\\Entidad\\Nombre** e **Instrucción\\Entidad\\AccountNum** en runtime si la lista `model.Vendor` esta vacía.

    ![Error de validación sobre un posible error para los componentes de formato configurados.](./media/er-components-inspections-09d.png)

La siguiente ilustración muestra el error de runtime que se produce si ignora la advertencia, selecciona **Ejecutar** para ejecutar el formato y seleccione el número de cuenta de un proveedor inexistente. Como el proveedor solicitado no existe, la lista `model.Vendor` estará vacía (es decir, no contendrá registros).

![Errores de runtime que se producen durante la ejecución de asignación de formato.](./media/er-components-inspections-09e.png)

### <a name="automatic-resolution"></a>Resolución automática

Para la fila seleccionada en la cuadrícula en la pestaña **Advertencias**, puede seleccionar **Desvincular**. El enlace que se señala en la columna **Ruta** se elimina automáticamente de los elementos de formato.

### <a name="manual-resolution"></a>Resolución manual

#### <a name="option-1"></a>Opción 1

Puede vincular el elemento de formato **Instrucción\\Entidad\\Nombre** al elemento de origen de datos `model.Vendor`. En runtime, este enlace llama primero al origen de datos `model.Vendor`. Cuando `model.Vendor` devuelve una lista de registros vacía, los elementos de formato anidados no se ejecutan. Por lo tanto, no se producen advertencias de validación para esta configuración de formato.

![Vincule el elemento de formato al elemento del origen de datos en la página Diseñador de formatos.](./media/er-components-inspections-09e.gif)

#### <a name="option-2"></a>Opción 2

Cambiar el enlace del elemento de formato **Instrucción\\Entidad\\Nombre** de `model.Vendor.Name` a `FIRSTORNULL(model.Vendor).Name`. El enlace actualizado convierte condicionalmente el primer registro del origen de datos `model.Vendor` del tipo **Lista de registros** a un nuevo origen de datos del tipo **Registro**. Este origen de datos nuevo contiene el mismo conjunto de campos.

- Si al menos un registro está disponible en el origen de datos `model.Vendor`, los campos de ese registro se llenan con los valores de los campos del primer registro del origen de datos `model.Vendor`. En este caso, el enlace actualizado devuelve el nombre del proveedor.
- De lo contrario, cada campo del registro que se crea se completa con el valor predeterminado para el tipo de datos de ese campo. En este caso, la cadena en blanco se devuelve como el valor predeterminado del tipo de datos **Cadena**.

Por lo tanto, no se producen advertencias de validación para el elemento de formato **Instrucción\\Entidad\\Nombre** cuando está vinculado a la expresión `FIRSTORNULL(model.Vendor).Name`.

![El enlace modificado resuelve las advertencias de validación en la página Diseñador de formatos.](./media/er-components-inspections-09f.gif)

#### <a name="option-3"></a>Opción 3

Si desea especificar explícitamente los datos que se introducen en un documento generado cuando el origen de datos `model.Vendor` del tipo **Lista de registros** no devuelve registros (el texto **No disponible** en este ejemplo), cambie el enlace del elemento de formato **Instrucción\\Entidad\\Nombre** de `model.Vendor.Name` a `IF(NOT(ISEMPTY(model.Vendor)), model.Vendor.Name, "Not available")`. También puedes usar la expresión `IF(COUNT(model.Vendor)=0, model.Vendor.Name, "Not available")`.

### <a name="additional-consideration"></a><a id="i9a"></a>Consideración adicional

La inspección también le advierte sobre otro problema potencial. De forma predeterminada, al vincular los elementos de formato **Instrucción\\Entidad\\Nombre** e **Instrucción\\Entidad\\AccountNum** a los campos apropiados del origen de datos `model.Vendor` del tipo **Lista de registros**, esos enlaces se ejecutarán y tomarán los valores de los campos apropiados del primer registro del origen de datos `model.Vendor`, si esa lista no está vacía.

Como no ha vinculado el elemento de formato **Instrucción\\Entidad** con el origen de datos `model.Vendor`, el elemento **Instrucción\\Entidad** no se iterará para cada registro del origen de datos `model.Vendor` durante la ejecución del formato. En cambio, un documento generado se llenará con información solo del primer registro de la lista de registros, si esa lista contiene varios registros. Por lo tanto, puede haber un problema si el formato está destinado a llenar un documento generado con información sobre todos los proveedores del origen de datos `model.Vendor`. Para solucionar este problema, vincule el elemento **Instrucción\\Entidad** con el origen de datos `model.Vendor`.

## <a name="executability-of-an-expression-with-filter-function-caching"></a><a id="i10"></a>Ejecutabilidad de una expresión con función FILTER (caché)

Varias funciones ER integradas, incluyendo [FILTER](er-functions-list-filter.md) y [ALLITEMSQUERY](er-functions-list-allitemsquery.md) se utilizan para acceder a tablas de aplicaciones, vistas o entidades de datos al realizar una sola llamada SQL para obtener los datos requeridos como una lista de registros. Un origen de datos del tipo **Lista de registros** se utiliza como argumento de cada una de estas funciones y especifica el origen de una aplicación para la llamada. ER comprueba si se puede establecer una llamada SQL directa a una fuente de datos a la que se hace referencia en una de estas funciones. Si no se puede establecer una llamada directa porque el origen de datos estaba marcado como [caché](trace-execution-er-troubleshoot-perf.md#improve-the-model-mapping-based-on-information-from-the-execution-trace), se produce un error de validación en el asignador de modelo ER. El mensaje que recibe indica que la expresión ER que contiene una de estas funciones no se puede ejecutar en runtime.

Los siguientes pasos muestran cómo puede ocurrir este problema.

1. Comience a configurar el componente de asignación del modelo ER.
2. Agregue un origen de datos del tipo **Dynamics 365 for Operations \\ Registros de tabla**.
3. Asigne un origen de datos nuevo **Proveedor**. En el campo **Tabla**, seleccione **VendTable** para especificar que este origen de datos solicitará la tabla VendTable.
4. Agregue un origen de datos del tipo **General \\ Parámetro de entrada de usuario** para buscar una cuenta de proveedor en el cuadro de diálogo de runtime.
5. Asigne un origen de datos nuevo **RequestedAccountNum**. En el campo **Etiqueta**, introduzca el **Número de cuenta del proveedor**. En el campo **Nombre del tipo de datos de operaciones**, deje el valor predeterminado, **Descripción**.
6. Agregue un origen de datos del tipo **Campo calculado** para filtrar un proveedor al que se consulte.
7. Nombre el nuevo origen de datos **FilteredVendor** y configúrelo para que contenga la expresión `FILTER(Vendor, Vendor.AccountNum=RequestedAccountNum)`.
8. Marca el origen de datos configurado **Proveedor** como en caché.

    ![Configurar el componente de asignación de modelos en la página Diseñador de asignación de modelos.](./media/er-components-inspections-10a.gif)

9. Seleccione **Validar** para inspeccionar el componente de asignación del modelo editable en la página **Diseñador de asignación de modelos**.

    ![Validar la función FILTRO aplicada al origen de datos de datos del proveedor de caché en la página Diseñador de mapas de asignación de modelos.](./media/er-components-inspections-10a.png)

10. Observe que se produce un error de validación. El mensaje dice que la función **FILTER** no se puede aplicar al origen de datos **Proveedor** en caché.

La siguiente ilustración muestra el error de runtime que se produce si ignora la advertencia y selecciona **Ejecutar** para ejecutar el formato.

![Error de runtime que ocurre durante la ejecución de asignación de formato en la página Diseñador de formato.](./media/er-components-inspections-10b.png)

### <a name="automatic-resolution&quot;></a>Resolución automática

No hay ninguna opción disponible para solucionar este problema automáticamente.

### <a name=&quot;manual-resolution&quot;></a>Resolución manual

#### <a name=&quot;option-1&quot;></a>Opción 1

Eliminar la etiqueta **Caché** del origen de datos **Proveedor**. El origen de datos **FilteredVendor** se volverá ejecutable, pero el origen de datos **Proveedor** al que se hace referencia en la tabla VendTable se accederá cada vez que se llame al origen de datos **FilteredVendor**.

#### <a name=&quot;option-2&quot;></a>Opción 2

Cambiar la expresión del origen de datos **FilteredVendor** de `FILTER(Vendor, Vendor.AccountNum=&quot;US-101")` a `WHERE(Vendor, Vendor.AccountNum="US-101")`. En este caso, el origen de datos **Proveedor** al que se referencia en la tabla VendTable se accederá solo durante la primera llamada al origen de datos **Proveedor**. Sin embargo, la selección de registros se hará en memoria. Por lo tanto, este enfoque puede provocar un rendimiento deficiente.

## <a name="missing-binding"></a><a id="i11"></a>Falta enlace

Cuando configura un componente de formato ER, el modelo de datos ER base se ofrece como origen de datos predeterminado para el formato ER. Cuando se ejecuta el formato ER configurado, la [asignación de modelo predeterminado](er-country-dependent-model-mapping.md) para el modelo base se utiliza para llenar el modelo de datos con datos de aplicación. El diseñador de formato de ER muestra una advertencia si vincula un elemento de formato a un elemento de modelo de datos que no está vinculado a ningún origen de datos en la asignación de modelo que está seleccionada actualmente como asignación de modelo predeterminado para el formato editable. Este tipo de enlace no se puede ejecutar en runtime, porque el formato que se ejecuta no puede llenar un elemento enlazado con datos de la aplicación. Por lo tanto, se produce un error en runtime.

Los siguientes pasos muestran cómo puede ocurrir este problema.

1. Comience a configurar los componentes del modelo de datos ER, de asignación del modelo ER y el formato ER simultáneamente.
2. En el árbol del modelo de datos, agregue un elemento raíz que se llame **Root3**.
3. Modifique el elemento **Root3** agregando un nuevo elemento anidado del tipo **Lista de registros**.
4. Nombre el nuevo elemento anidado **Proveedor**.
5. Modifique el elemento **Proveedor** de la siguiente manera:

    - Agregue un campo anidado del tipo **Cadena** y nómbrelo **Nombre**.
    - Agregue un campo anidado del tipo **Cadena** y nómbrelo **AccountNumber**.

    ![Agregar campos anidados al artículo del proveedor en la página Modelo de datos.](./media/er-components-inspections-11a.png)

6. En el diseñador de asignación de modelos, en el panel **Orígenes de datos**, agregue un origen de datos al tipo **Dynamics 365 for Operations \\ Registros de tabla**.
7. Asigne un origen de datos nuevo **Proveedor**. En el campo **Tabla**, seleccione **VendTable** para especificar que este origen de datos solicitará la tabla VendTable.
8. Agregue un origen de datos del tipo **General \\ Parámetro de entrada de usuario** para buscar una cuenta de proveedor en el cuadro de diálogo de runtime.
9. Asigne un origen de datos nuevo **RequestedAccountNum**. En el campo **Etiqueta**, introduzca el **Número de cuenta del proveedor**. En el campo **Nombre del tipo de datos de operaciones**, deje el valor predeterminado, **Descripción**.
10. Agregue un origen de datos del tipo **Campo calculado** para filtrar un proveedor al que se consulte.
11. Nombre el nuevo origen de datos **FilteredVendor** y configúrelo para que contenga la expresión `FILTER(Vendor, Vendor.AccountNum=RequestedAccountNum)`.
12. Vincule los elementos del modelo de datos a los orígenes de datos configurados de la siguiente manera:

    - Enlazar **FilteredVendor** a **Proveedor**.
    - Enlazar **FilteredVendor.AccountNum** a **Vendor.AccountNumber**.

    > [!NOTE]
    > El campo **Vendor.Name** del modelo de datos permanece sin consolidar.

    ![Elementos del modelo de datos vinculados a orígenes de datos configurados y un elemento de modo de datos que se encuentra desenlazado en la página Diseñador de asignación de modelos.](./media/er-components-inspections-11b.png)

13. En el árbol de estructura de formato, agregue los siguientes elementos para generar un documento saliente en formato XML que contenga los detalles de los proveedores consultados:

    1. Agregue el elemento XML raíz **Instrucción**.
    2. Para el elemento XML **Instrucción**, agregue el elemento XML anidado **Entidad**.
    3. Para el elemento XML **Entidad**, agregue los siguientes atributos XML anidados:

        - Nombre
        - AccountNum

14. Vincule los elementos de formato a los orígenes de datos proporcionados de la siguiente manera:

    - Vincule el elemento de formato **Instrucción\\Entidad** al elemento de origen de datos `model.Vendor`.
    - Vincule el elemento de formato **Instrucción\\Entidad\\Nombre** al campo de origen de datos **model.Vendor.Name**.
    - Vincule el elemento de formato **Instrucción\\Entidad\\AccountNum** al campo de origen de datos **model.Vendor.AccountNumber**.

15. Seleccione **Validar** para inspeccionar el componente de formato editable en la página **Diseñador de formato**.

    ![Validar el componente de formato ER en la página Diseñador de formato.](./media/er-components-inspections-11c.png)

16. Observe que se produce una advertencia de validación. El mensaje dice que el campo del origen de datos **model.Vendor.Name** no está vinculado a ningún origen de datos en la asignación del modelo que está configurado para ser utilizado por el formato. Por lo tanto, el elemento de formato **Instrucción\\Entidad\\Nombre** es posible que el elemento de formato no se complete en runtime y que se produzca una excepción en runtime.

    ![Validar el componente de formato ER en la página de diseñador de formato.](./media/er-components-inspections-11d.png)

La siguiente ilustración muestra el error de runtime que se produce si ignora la advertencia y selecciona **Ejecutar** para ejecutar el formato.

![Ejecutar el formato editable en la página Diseñador de formatos.](./media/er-components-inspections-11e.png)

### <a name="automatic-resolution"></a>Resolución automática

No hay ninguna opción disponible para solucionar este problema automáticamente.

### <a name="manual-resolution"></a>Resolución manual

#### <a name="option-1"></a>Opción 1

Modifique la asignación del modelo configurado agregando un enlace para el campo **model.Vendor.Name** del origen de datos.

#### <a name="option-2"></a>Opción 2

Modifique el formato configurado eliminando el enlace para el elemento de formato **Instrucción\\Entidad\\Nombre**.

## <a name="not-linked-template"></a><a id="i12"></a>Plantilla no vinculada

Cuando usted configura [manualmente](er-fillable-excel.md#manual-entry) un componente de formato ER para usar una plantilla para generar un documento saliente, debe agregar manualmente el elemento **Excel\\Archivo**, agregue la plantilla requerida como un adjunto del componente editable y seleccione ese adjunto en el elemento **Excel\\Archivo** agregado. De esta manera, indicas que el elemento agregado llenará la plantilla seleccionada en runtime. Cuando configura una versión de componente de formato en [estado](general-electronic-reporting.md#component-versioning), **Borrador** puede agregar varias plantillas al componente editable y luego seleccionar cada plantilla en el elemento **Excel\\Archivo** para ejecutar el formato ER. De esta manera, puede ver cómo se llenan las diferentes plantillas en runtime. Si tiene plantillas que no están seleccionadas en ningún elemento **Excel\\Archivo**, el diseñador de formato ER le advierte que esas plantillas se eliminarán de la versión editable del componente de formato ER cuando su estado cambie de **Borrador** a **Terminado**.

Los siguientes pasos muestran cómo puede ocurrir este problema.

1. Comience a configurar el componente de formato ER.
2. En el árbol de estructura de formato, agregue el elemento **Excel\\Archivo**.
3. Para el elemento **Excel\\Archivo** que acaba de agregar, agregue un archivo de libro de Excel, **A.xlsx**, como archivo adjunto. Utilice el tipo de documento que está configurado en los [Parámetros de ER](electronic-reporting-er-configure-parameters.md#parameters-to-manage-documents) para especificar el almacenamiento de plantillas de formato ER.
4. Para el elemento **Excel\\Archivo** agregue otro archivo de libro de Excel, **B.xlsx**, como archivo adjunto. Utilice el mismo tipo de documento que se utiliza para el archivo de libro A.
5. En el elemento **Excel\\Archivo**, seleccione el archivo de libro A.
6. Seleccione **Validar** para inspeccionar el componente de formato editable en la página **Diseñador de formato**.

    ![Validación del componente de formato editable del archivo del libro de trabajo en la página del diseñador de formato.](./media/er-components-inspections-12a.gif)

7. Observe que se produce una advertencia de validación. El mensaje indica que el archivo del libro B.xlsx no está vinculado a ningún componente y que se eliminará después de que se cambie el estado de la versión de configuración.

### <a name="automatic-resolution"></a>Resolución automática

No hay ninguna opción disponible para solucionar este problema automáticamente.

### <a name="manual-resolution"></a>Resolución manual

Modifique el formato configurado eliminando todas las plantillas que no están vinculadas a ningún elemento **Excel\\Archivo**.

## <a name="not-synced-format"></a><a id="i13"></a>Formato no sincronizado

Cuando usted [configura](er-fillable-excel.md) un componente de formato ER para usar una plantilla Excel para generar un documento saliente, puede agregar manualmente el elemento **Excel\\Archivo**, agregue la plantilla requerida como un adjunto del componente editable y seleccione ese adjunto en el elemento **Excel\\Archivo** agregado. De esta manera, indicas que el elemento agregado llenará la plantilla seleccionada en runtime. Debido a que la plantilla de Excel agregada se ha diseñado externamente, el formato ER editable puede contener nombres de Excel que faltan en la plantilla agregada. El diseñador de formato ER le advierte sobre cualquier inconsistencia entre las propiedades de los elementos del formato ER que se refieren a nombres que no están incluidos en la plantilla de Excel agregada.

Los siguientes pasos muestran cómo puede ocurrir este problema.

1. Comience a configurar el componente de formato ER.
2. En el árbol de estructura de formato, agregue el elemento de **Excel\\Archivo** **Informe**.
3. Para el elemento **Excel\\Archivo** que acaba de agregar, agregue un archivo de libro de Excel, **A.xlsx**, como archivo adjunto. Utilice el tipo de documento que está configurado en los [Parámetros de ER](electronic-reporting-er-configure-parameters.md#parameters-to-manage-documents) para especificar el almacenamiento de plantillas de formato ER.

    > [!IMPORTANT]
    > Asegúrese de que el libro de Excel agregado no contenga el nombre **ReportTitle**.

4. Agregue el siguiente **Título** de elemento **Excel\\Celda** como elemento anidado del elemento **Informe**. En el campo **Intervalo de Excel**, introduzca **ReportTitle**.
5. Seleccione **Validar** para inspeccionar el componente de formato editable en la página **Diseñador de formato**.

    ![Validar los elementos y campos anidados en la página Diseñador de formato.](./media/er-components-inspections-13a.png)

6. Observe que se produce una advertencia de validación. El mensaje dice que el nombre **ReportTitle** no existe en la hoja **Hoja1** de la plantilla de Excel que está utilizando.

    ![Advertencia de validación de que el nombre ReportTitle no existe en Sheet1 de la plantilla de Excel.](./media/er-components-inspections-13b.png)

### <a name="automatic-resolution"></a>Resolución automática

No hay ninguna opción disponible para solucionar este problema automáticamente.

### <a name="manual-resolution"></a>Resolución manual

#### <a name="option-1"></a>Opción 1

Modifique el formato configurado eliminando todos los elementos que hacen referencia a los nombres de Excel que faltan en la plantilla.

#### <a name="option-2"></a>Opción 2

[Actualizar](er-fillable-excel.md#template-import) el formato ER editable mediante la importación de una plantilla de Excel. La estructura del formato ER editable se [sincronizará](modify-electronic-reporting-format-reapply-excel-template.md) con la estructura de la plantilla de Excel importada.

### <a name="additional-consideration"></a>Consideración adicional

Para saber cómo se puede sincronizar la estructura del formato con una plantilla de ER en el editor de plantillas de [Gestión de documentos empresariales](er-business-document-management.md), ver [Actualizar la estructura de una plantilla de documento empresarial](er-bdm-update-structure.md).

## <a name="not-synced-with-a-word-template-format"></a><a id="i14"></a>No sincronizado con un formato de plantilla de Word

Cuando usted [configura](er-fillable-excel.md) un componente de formato ER para usar una plantilla de Word para generar un documento saliente, puede agregar manualmente el elemento **Excel\\Archivo**, agregar la plantilla de Word requerida como un adjunto del componente editable y seleccionar ese adjunto en el elemento **Excel\\Archivo** agregado.

> [!NOTE]
> Cuando se adjunta el documento de Word, el diseñador de formato ER presenta el elemento editable como **Palabra\\Archivo**.

De esta manera, indicas que el elemento agregado llenará la plantilla seleccionada en runtime. Debido a que la plantilla de Word se ha diseñado externamente, el formato ER editable puede contener referencias a controles de contenido de Word que faltan en la plantilla agregada. El diseñador de formato ER le advierte sobre cualquier incoherencia entre las propiedades de los elementos del formato ER que se refieren a controles de contenido que no están incluidos en la plantilla de Word agregada.

Para ver un ejemplo que muestra cómo puede ocurrir este problema, consulte [Configurar el formato editable para suprimir la sección de resumen](er-design-configuration-word-suppress-controls.md#configure-to-suppress-control).

### <a name="automatic-resolution"></a>Resolución automática

No hay ninguna opción disponible para solucionar este problema automáticamente.

### <a name="manual-resolution"></a>Resolución manual

#### <a name="option-1"></a>Opción 1

Modifique el formato configurado eliminando la fórmula **Eliminado** del elemento de formato que se menciona en la advertencia de validación.

#### <a name="option-2"></a>Opción 2

Modifique la plantilla de Word [agregando](er-design-configuration-word-suppress-controls.md#tag-control) la etiqueta requerida para el control de contenido de Word relevante.

## <a name="no-default-mapping"></a><a id="i15"></a>Sin asignación predeterminada

Cuando se realiza la inspección [Enlace que falta](#i11), los enlaces de formato inspeccionados se evalúan frente a los enlaces del componente de asignación de modelo relevante. Como puede importar [diversas](./tasks/er-manage-model-mapping-configurations-july-2017.md) configuraciones de asignación de modelos de ER a su instancia de Finance, y cada configuración puede contener el componente de asignación de modelos aplicable, se debe seleccionar una configuración como la configuración predeterminada. De lo contrario, cuando intente ejecutar, editar o validar el formato de ER inspeccionado, se producirá una excepción y recibirá el siguiente mensaje: "Existe más de una asignación de modelo para el \<model name (root descriptor)\> modelo de datos en las configuraciones \<configuration names separated by comma\>. Establezca una de las configuraciones como predeterminada".

Para ver un ejemplo que muestra cómo puede ocurrir este problema y cómo se puede solucionar, consulte [Gestionar varias asignaciones derivadas para una única raíz de modelo](er-multiple-model-mappings.md).

## <a name="inconsistent-setting-of-header-or-footer-components"></a><a id="i16"></a>Configuración incoherente de los componentes de encabezado o pie de página

Cuando usted [configura](er-fillable-excel.md) un componente de formato ER para usar una plantilla de Excel para generar un documento saliente, puede agregar el componente **Excel\\Encabezamiento** para completar los encabezados en la parte superior de una hoja de cálculo en un libro de Excel. También puede agregar el componente **Excel\\Pie de página** para rellenar pies de página en la parte inferior de una hoja de cálculo. Para cada componente **Excel\\Encabezamiento** o **Excel\\Pie de página** componente que agregue, debe establecer la propiedad **Apariencia del encabezado/pie de página** para especificar las páginas para las que se ejecuta el componente. Porque puede configurar varios componentes **Excel\\Encabezamiento** o **Excel\\Pie de página** para un solo componente **Hoja**, y puede generar diferentes encabezados o pies de página para diferentes tipos de páginas en una hoja de cálculo de Excel, debe configurar un único componente **Excel\\Encabezamiento** o **Excel\\Pie de página** para un valor específico de la propiedaad **Apariencia del encabezado/pie de página**. Si se configura más de un componente **Excel\\Encabezamiento** o **Excel\\Pie de página** para un valor específico de la propiedad **Apariencia del encabezado/pie de página**, se produce un error de validación y recibe el siguiente mensaje de error: "Encabezados/pies de página (&lt;tipo de componente: encabezado o pie de página&gt;) incoherentes".

### <a name="automatic-resolution"></a>Resolución automática

No hay ninguna opción disponible para solucionar este problema automáticamente.

### <a name="manual-resolution"></a>Resolución manual

#### <a name="option-1"></a>Opción 1

Modifique el formato configurado eliminando uno de los componentes incoherentes **Excel\\Encabezamiento** o **Excel\\Pie de página**.

#### <a name="option-2"></a>Opción 2

Modifique el valor de la propiedad **Apariencia del encabezado/pie de página** para uno de los componentes incoherentes **Excel\\Encabezamiento** o **Excel\\Pie de página**.

## <a name="inconsistent-setting-of-page-component"></a><a id="i17"></a>Configuración incoherente del componente Página

Al [configurar](er-fillable-excel.md) un componente de formato ER para usar una plantilla de Excel para generar un documento saliente, puede agregar el componente **Excel\\Página** para paginar un documento generado mediante el uso de fórmulas de ER. Para cada componente **Excel\\Página** que agregue, puede agregar muchos componentes [Rango](er-fillable-excel.md#range-component) y seguirá la compatibilidad con la siguiente [estructura](er-fillable-excel.md#page-component-structure):

- El primer componente **Rango** anidado se puede configurar para que la propiedad **Dirección de replicación** esté establecida en **Sin replicación**. Este rango se utiliza para crear encabezados de página en documentos generados.
- Puede agregar muchos otros componentes **Rango** en los que la propiedad **Dirección de replicación** está establecida en **Vertical**. Estos rangos se utilizan para rellenar los documentos generados.
- El último componente **Rango** anidado se puede configurar para que la propiedad **Dirección de replicación** esté establecida en **Sin replicación**. Este rango se utiliza para crear pies de página en documentos generados y para agregar los saltos de página necesarios.

Si no sigue esta estructura para un formato ER en el diseñador de formato ER en tiempo de diseño, se produce un error de validación y se recibe el siguiente mensaje de error: "Hay más de dos componentes de rango sin replicación. Elimine los componentes innecesarios".

### <a name="automatic-resolution"></a>Resolución automática

No hay ninguna opción disponible para solucionar este problema automáticamente.

### <a name="manual-resolution"></a>Resolución manual

#### <a name="option-1"></a>Opción 1

Modifique el formato configurado cambiando la propiedad **Dirección de replicación** para todos los componentes **Excel\\Rango** incoherentes.

## <a name="additional-resources"></a>Recursos adicionales

[Función ALLITEMS ER](er-functions-list-allitems.md)

[Función ALLITEMSQUERY ER](er-functions-list-allitemsquery.md)

[Función INT64VALUE de ER](er-functions-conversion-int64value.md)

[Función INTVALUE ER](er-functions-conversion-intvalue.md)

[Función FILTER de ER](er-functions-list-filter.md)

[Función WHERE de ER](er-functions-list-where.md)

[Usar los orígenes de datos de JOIN para obtener datos de varias tablas de aplicación en las asignaciones de modelo ER](er-join-data-sources.md)

[Realizar un seguimiento de la ejecución de los formatos de ER para solucionar problemas de rendimiento](trace-execution-er-troubleshoot-perf.md)

[Visión general de la gestión de documentos empresariales](er-business-document-management.md)

[Suprimir los controles de contenido de Word en los informes generados](er-design-configuration-word-suppress-controls.md)

[Gestionar varias asignaciones derivadas para una única raíz del modelo](er-multiple-model-mappings.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
