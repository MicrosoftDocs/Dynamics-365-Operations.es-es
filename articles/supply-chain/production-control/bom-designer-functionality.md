---
title: Funcionalidad del diseñador de lista de materiales
description: Este tema describe cómo puede usar la página del diseñador de L. MAT para diseñar y trabajar con estructuras de árbol para las listas de materiales (L. MAT).
author: cvocph
manager: tfehr
ms.date: 11/03/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BOMDesigner, BOMDesignerSetup, BOMDesignerFilterDialog, BOMDesignerBOMVersion, BOMChangeLine
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 20981
ms.assetid: 2b92eec1-d28c-4965-9086-939c77b3c62b
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2e845b05d77701191a267de45354c3da25bd7699
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4436899"
---
# <a name="bom-designer-functionality"></a>Funcionalidad del diseñador de lista de materiales

[!include [banner](../includes/banner.md)]

Este tema describe cómo puede usar la página del diseñador de L. MAT para diseñar y trabajar con estructuras de árbol para las listas de materiales (L. MAT). Puede hacer clic Configurar para seleccionar distintas configuraciones y especificar qué información aparece en las líneas del árbol.

Cuando abre la página **Diseñador de L. MAT.** desde la página **Productos emitidos**, se muestra la jerarquía de las listas de materiales activas y aprobadas para el artículo seleccionado, el sitio de pedido predeterminado del artículo y la fecha real.  

Haga clic en **Filtro** para cambiar la selección inicial en la vista. Al establecer la visualización en **Seleccionado/Activo o Seleccionado**, puede seleccionar listas de materiales o versiones de rutas que usar en la vista. Puede seleccionar versiones de listas de materiales no aprobadas e inactivas que mostrar o mantener en el diseñador de lista de materiales.  

**Nota:** si abre el diseñador de lista de materiales desde la página **Listas de materiales**, no se mostrará la información de ruta. Actualmente, la selección de una lista de materiales o la versión de ruta es una propiedad de la lista de materiales y la versión de la ruta, y se aplica a todas las instancias del diseñador de lista de materiales.  

Las siguientes secciones describen la funcionalidad disponible en las diferentes fichas del diseñador de lista de materiales.

## <a name="analyzing-a-bom-structure-by-using-the-bom-designer"></a>Análisis de estructuras de lista de materiales con el diseñador de lista de materiales
El diseñador de lista de materiales tiene dos secciones:

-   La vista de árbol de la estructura de la lista de materiales.
-   La sección de detalles, que muestra los detalles de los datos seleccionados. Cuando selecciona un nodo en la vista de árbol, las fichas desplegables de la sección de detalles se actualiza en función del nodo:
    -   **Detalles de línea de L. MAT**: muestra los detalles de la línea de la lista de materiales seleccionada en la vista de árbol.
    -   **Datos de artículo**: muestra los detalles del artículo principal o del artículo utilizado en el nodo seleccionado. Puede hacer en **Editar el producto emitido** para mantener el artículo seleccionado.
    -   **L. MAT.**: muestra el encabezado de la lista de materiales relacionada con el nodo seleccionado.
    -   **Ruta**: muestra el encabezado de la ruta relacionada con el nodo seleccionado.
    -   **Operaciones de ruta**: muestra una vista preliminar de las operaciones de ruta. Cuando se selecciona una línea de lista de materiales asignada a una operación específica, se marca la operación como **Componente necesario en las operaciones**.

## <a name="selecting-a-bom-and-route"></a>Selección de una lista de materiales y una ruta
El filtro que se aplica para la lista de materiales y la ruta se muestra en el encabezado del diseñador de lista de materiales. Puede cambiar el filtro mediante el cuadro de diálogo **Filtro**. En la tabla siguiente se describen los campos de este cuadro de diálogo.

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
<td>Si el producto terminado seleccionado es un producto maestro, puede definir las dimensiones de producto activas para la selección principal. <strong>Nota:</strong> Si abre el diseñador de L. MAT para un artículo que no sea un producto maestro, no se pueden seleccionar dimensiones de producto en el cuadro de diálogo <strong>Filtro</strong>.</td>
</tr>
<tr class="even">
<td>Sitio</td>
<td>Cambie el sitio para el cual se muestra el árbol de lista de materiales. El sitio predeterminado es el sitio de inventario predeterminado del artículo terminado.</td>
</tr>
<tr class="odd">
<td>Principio de presentación</td>
<td>Seleccione el principio de visualización de versiones que se aplica a la estructura de lista de materiales actual y la ruta actual:
<ul>
<li>Si el principio está definido como <strong>Activo o Seleccionado/Activo</strong>, se busca la lista de materiales o la versión de ruta válida para esta fecha.</li>
<li>Si el principio se establece en <strong>Seleccionado/Activo o Seleccionado</strong>, puede seleccionar una versión de lista de materiales o una versión de ruta haciendo clic en <strong>L. MAT.</strong> &gt; <strong>Versiones de L. MAT.</strong> o <strong>Ruta</strong> &gt; <strong>Versiones de ruta</strong>.</li>
</ul></td>
</tr>
<tr class="even">
<td>Fecha de la versión</td>
<td>Escriba la fecha de la versión de la L. MAT y la ruta. La versión identifica qué versión de la lista de materiales se va a usar en una fecha concreta, según determinan las fechas de versión de la configuración de versión de la lista de materiales.</td>
</tr>
<tr class="odd">
<td>Cantidad inicial</td>
<td>Filtre las versiones seleccionando una determinada de cantidad de origen. Si establece un valor, se podrán seleccionar listas de materiales y versiones de ruta diferentes.</td>
</tr>
<tr class="even">
<td>Mostrar sólo válidas</td>
<td>Si se selecciona la casilla, la estructura de árbol únicamente muestra las líneas de la lista de materiales con fechas válidas. Haga clic con el botón secundario en una línea de lista de materiales para abrir la página <strong>Editar línea de L. MAT.</strong> y ver las fechas de validez para la línea de la lista de materiales.</td>
</tr>
</tbody>
</table>

Al usar el diseñador de lista de materiales para revisar o editar las listas de materiales que constan de uno o varios niveles de fantasmas, la ruta asociada con el elemento superior normalmente abarca la jerarquía completa de la lista de materiales. Para simplificar la descripción, puede bloquear la ruta de nivel superior en la visualización haciendo clic en **Ver** &gt; **Bloquear ruta**. Para desbloquear la ruta, haga clic en **Ver** &gt; **Desbloquear ruta**.

## <a name="adding-and-editing-boms-and-bom-lines"></a>Adición y edición de listas de materiales y líneas de listas de materiales
Use las funciones **Líneas de L. MAT.** o **L. MAT.** para modificar las líneas de la lista de materiales o la lista de materiales. Cuando selecciona un nodo del árbol, el tipo de nodo determina las funciones disponibles.

| Función                            | Descripción                                                                                               | Tipo de nodo y condiciones                                                                                                                                                                                                                                                                       |
|-------------------------------------|-----------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Líneas de L. MAT. &gt; Editar                 | Abra un cuadro de diálogo donde pueda editar los atributos de línea de la lista de materiales.                                             | Esta función solo está disponible cuando se ha seleccionado un nodo de línea de lista de materiales.                                                                                                                                                                                                                                   |
| Líneas de L. MAT. &gt; Eliminar               | Elimine una línea de la lista de materiales seleccionada.                                                                  | Esta función solo está disponible cuando se ha seleccionado un nodo de línea de lista de materiales y la lista de materiales no está bloqueada frente a ediciones.                                                                                                                                                                                             |
| Líneas de L. MAT. &gt; Agregar antes de la línea      | Abra un cuadro de diálogo donde pueda seleccionar una variante de producto que incluir antes de la línea de lista de materiales seleccionada.         | Esta función solo está disponible cuando se ha seleccionado un nodo de línea de lista de materiales.                                                                                                                                                                                                                                   |
| Líneas de L. MAT. &gt; Agregar a L. MAT. de componentes | Abra un cuadro de diálogo donde pueda seleccionar una variante de producto que incluir al final de la lista de materiales seleccionada.       | Esta función solo está disponible cuando se ha seleccionado un nodo con una lista de materiales seleccionada. Si esta función no está disponible, es posible que falte una versión de lista de materiales de la variante del artículo seleccionada. En este caso, puede hacer clic en **L. MAT.** &gt; **Crear versión** para crear la versión que falta del nodo seleccionado. |
| Líneas de L. MAT. &gt; Agregar después de la línea       | Abra un cuadro de diálogo donde pueda seleccionar una variante de producto que incluir después de la línea de lista de materiales seleccionada.          | Esta función solo está disponible cuando se ha seleccionado un nodo de línea de lista de materiales.                                                                                                                                                                                                                                   |
| L. MAT. &gt; Crear versión             | Cree una nueva versión de lista de materiales o una lista de materiales para la variante del producto del nodo seleccionado.                             | Esta función solo está disponible cuando el nodo de línea de lista de materiales seleccionado está vinculado a un artículo con tipo de producción **L. MAT.** o **Fórmula**.                                                                                                                                                  |
| L. MAT. &gt; Cálculo                | Abra un cuadro de diálogo donde pueda ejecutar el cálculo de coste o del precio de ventas para la variante del producto seleccionada. | Esta función solo está disponible cuando se ha seleccionado un nodo relacionado con una versión de lista de materiales.                                                                                                                                                                                                         |
| L. MAT. &gt; Comprobar                      | Valide y compruebe la lista de materiales seleccionada.                                                                      | Esta función solo está disponible cuando se ha seleccionado un nodo relacionado con una versión de lista de materiales.                                                                                                                                                                                                         |

## <a name="configuring-the-tree-view"></a>Configuración de la vista de árbol
Haga clic en **Configurar** para personalizar la información que se muestra en el diseñador de lista de materiales.

| Grupo de campos | Descripción                                                                                                                                                  |
|-------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------|
| L. MAT         | Sírvase de las casillas de verificación para seleccionar los criterios que se ven en la estructura de árbol. El diseñador de lista de materiales mostrará los criterios seleccionados en la parte inferior de ambas fichas. |
| Ruta       | Sírvase de las casillas de verificación para seleccionar los criterios que se ven para las rutas.                                                                                    |







[!INCLUDE[footer-include](../../includes/footer-banner.md)]