---
title: "Diseñador de fórmula"
description: "Este tema explica cómo utilizar el diseñador de fórmulas para analizar y mantener fórmulas en una vista de árbol."
author: cvocph
manager: AnnBe
ms.date: 06/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: PlanActivity, ReqSupplyDemandSchedule
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.search.industry: 
ms.author: cvocph
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 159aa0fd5d057ed4105a79f11b3658133f417319
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---

# <a name="formula-designer"></a>Diseñador de fórmula

[!include[banner](../includes/banner.md)]

Este tema explica cómo utilizar el diseñador de fórmulas para analizar y mantener fórmulas en una vista de árbol.

Al abrir la página **Diseñador de fórmulas** en la página **Productos emitidos**, el árbol en el panel izquierdo muestra la lista de los coproductos y la jerarquía de los ingredientes para el producto liberado. La estructura deriva de la jerarquía de las fórmulas que están activas y aprobadas para el artículo seleccionado y sus ingredientes, el sitio del pedido predeterminad del artículo y la fecha real.

Haga clic en **Configurar** para seleccionar distintas configuraciones y especificar qué información aparece en las líneas del árbol.

Haga clic en **Filtro** para cambiar la selección inicial en la vista. Si establece el principio de presentación en **Seleccionado/Activo** o **Seleccionado**, puede seleccionar fórmulas individuales o versiones de rutas para usar en la vista. Puede seleccionar versiones de fórmulas no aprobadas e inactivas que mostrar o mantener en el diseñador de fórmulas.  

> [!NOTE]
> Si abre el **Diseñador de fórmulas** en la página de la **Lista de materiales**, no se mostrará la información de ruta. Actualmente, la selección de una fórmula o una versión de ruta se aplica a todas las instancias del diseñador de fórmula.  

Las siguientes secciones describen la funcionalidad disponible en el diseñador de lista de materiales.

## <a name="analyze-a-formula-structure-by-using-the-formula-designer"></a>Analizar una estructura de fórmulas mediante el diseñador de fórmulas
El diseñador de fórmulas tiene dos secciones:

-   La vista de árbol de la estructura de fórmulas.
-   La sección de detalles, que muestra los detalles de los datos seleccionados. Cuando selecciona un nodo en la vista de árbol, las fichas desplegables de la sección de detalles se actualiza en función del nodo:
    -   **Detalles de línea de fórmula**: muestra los detalles de fórmula seleccionada en la vista de árbol.
    -   **Datos de artículo**: muestra los detalles del artículo principal o del artículo utilizado en el nodo seleccionado. Puede hacer en **Editar el producto emitido** para mantener el artículo seleccionado.
    -   **Fórmula**: muestra el encabezado de la fórmula relacionada con el nodo seleccionado.
    -   **Ruta**: muestra el encabezado de la ruta relacionada con el nodo seleccionado.
    -   **Operaciones de ruta**: muestra una vista preliminar de las operaciones de ruta. Cuando se selecciona una línea de lista de materiales asignada a una operación específica, se marca la operación como **Componente necesario en las operaciones**.

## <a name="select-a-formula-and-route"></a>Seleccionar una fórmula y una ruta
El filtro que se aplica para la fórmula y la ruta se muestra en el encabezado del diseñador de fórmulas. Puede cambiar el filtro mediante el cuadro de diálogo **Filtro**. En la tabla siguiente se describen los campos de este cuadro de diálogo.

<table>
<thead>
<tr class="header">
<th>Campo</th>
<th>Descripción</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Dimensiones de producto</td>
<td>Si el producto terminado seleccionado es un producto maestro, puede definir las dimensiones de producto activas para la selección principal. Tenga en cuenta que si abre el diseñador de fórmulas de un artículo que no sea un producto maestro, no se pueden seleccionar dimensiones de producto en el cuadro de diálogo <strong>Filtro</strong>.</p></td>
</tr>
<tr class="even">
<td>Sitio</td>
<td>Cambie el sitio para el cual se muestra el árbol de componentes. El sitio predeterminado es el sitio de inventario predeterminado del artículo terminado.</td>
</tr>
<tr class="odd">
<td>Principio de presentación</td>
<td><p>Seleccione el principio de visualización de versiones que se aplica a la estructura de fórmula actual y la ruta actual:</p>
<ul>
<li>Si el principio está definido como <strong>Activo</strong> o <strong>Seleccionado/Activo</strong>, se buscará la fórmula válida o la versión de ruta de esta fecha.</li>
<li>Si el principio se establece en <strong>Seleccionado/Activo</strong> o <strong>Seleccionado</strong>, puede seleccionar una versión de la fórmula o la versión de la ruta haciendo clic <strong>Fórmula</strong> &gt; <strong>Versiones de la fórmula</strong> o <strong>Ruta</strong> &gt; <strong>Versiones de la ruta</strong>.</li>
</ul></td>
</tr>
<tr class="even">
<td>Fecha de la versión</td>
<td>Especifique la fecha de la versión de la fórmula y la ruta. La versión identifica qué versión de la fórmula se usa en una fecha concreta, según determinan las fechas de la versión en la configuración de versión de la fórmula.</td>
</tr>
<tr class="odd">
<td>Cantidad inicial</td>
<td>Filtre las versiones seleccionando una determinada de cantidad de origen. Si establece un valor, se podrán seleccionar fórmulas y versiones de ruta diferentes.</td>
</tr>
<tr class="even">
<td>Mostrar sólo válidas</td>
<td>Si se selecciona la casilla, la estructura de árbol únicamente muestra las líneas de fórmula con fechas válidas. Haga clic con el botón secundario en una fórmula para abrir la página <strong>Editar línea de fórmula</strong> y ver las fechas de validez para la línea de la fórmula.</td>
</tr>
</tbody>
</table>

Al usar el diseñador de fórmulas para revisar o editar las fórmulas que constan de uno o varios niveles de fantasmas, la ruta asociada con el elemento superior normalmente abarca la jerarquía completa de fórmulas. Para simplificar la descripción, puede bloquear la ruta de nivel superior en la visualización haciendo clic en **Ver** &gt; **Bloquear ruta**. Para desbloquear la ruta, haga clic en **Ver** &gt; **Desbloquear ruta**.

## <a name="add-and-edit-formulas-and-formula-lines"></a>Agregar y editar fórmulas y líneas de fórmula
Use las funciones **Líneas de L. MAT.** o **Fórmula** para modificar las líneas de fórmula o la fórmula. Cuando selecciona un nodo del árbol, el tipo de nodo determina las funciones disponibles.

| Función                            | Descripción                                                                                               | Tipo de nodo y condiciones |
|-------------------------------------|-----------------------------------------------------------------------------------------------------------|--------------------------|
| Líneas de L. MAT. &gt; Editar                 | Abra un cuadro de diálogo donde pueda editar los atributos de línea de la fórmula.                                         | Esta función solo está disponible cuando se ha seleccionado un nodo de línea de fórmulas. |
| Líneas de L. MAT. &gt; Eliminar               | Elimine una línea fórmula para la fórmula seleccionada.                                                          | Esta función solo está disponible cuando se ha seleccionado una línea de fórmulas y la fórmula no está bloqueada frente a ediciones. |
| Líneas de L. MAT. &gt; Agregar antes de la línea      | Abra un cuadro de diálogo donde pueda seleccionar una variante de producto que incluir antes de la línea de fórmulas.     | Esta función solo está disponible cuando se ha seleccionado un nodo de línea de fórmulas. |
| Líneas de L. MAT. &gt; Agregar a L. MAT. de componentes | Abra un cuadro de diálogo donde pueda seleccionar una variante de producto que incluir al final de la fórmula seleccionada.   | Esta función solo está disponible cuando el nodo que se ha seleccionado tiene una fórmula seleccionada. Si esta función no está disponible, es posible que falte una versión de fórmula de la variante del artículo seleccionada. En este caso, puede hacer clic en **Fórmula** &gt; **Crear versión** para crear la versión que falta del nodo seleccionado. |
| Líneas de L. MAT. &gt; Agregar después de la línea       | Abra un cuadro de diálogo donde pueda seleccionar una variante de producto que incluir después de la línea de fórmulas.      | Esta función solo está disponible cuando se ha seleccionado un nodo de línea de fórmulas. |
| Fórmula &gt; Crear una versión         | Cree una nueva versión de fórmula o una fórmula para la variante del producto del nodo seleccionado.                     | Esta función solo está disponible cuando el nodo de línea de fórmulas seleccionado está vinculado a un artículo con tipo de producción **L. MAT.** o **Fórmula**. |
| Fórmula &gt; Cálculo            | Abra un cuadro de diálogo donde pueda ejecutar el cálculo de coste o del precio de ventas para la variante del producto seleccionada. | Esta función solo está disponible cuando se ha seleccionado un nodo relacionado con una versión de fórmulas. |
| Fórmula &gt; Comprobar                  | Valide y compruebe la fórmula seleccionada.                                                                  | Esta función solo está disponible cuando se ha seleccionado un nodo relacionado con una versión de fórmulas. |

## <a name="configuring-the-tree-view"></a>Configuración de la vista de árbol
Haga clic en **Configurar** para personalizar la información que se muestra en el diseñador de fórmula.

| Grupo de campos | Descripción |
|-------------|-------------|
| L. MAT         | Sírvase de las casillas de verificación para seleccionar los criterios que se ven en la estructura de árbol. El diseñador de fórmula muestra los criterios seleccionados en la parte inferior de ambas fichas. |
| Ruta       | Sírvase de las casillas de verificación para seleccionar los criterios que se ven para las rutas. |

