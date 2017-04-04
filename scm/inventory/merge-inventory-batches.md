---
title: Combinar lotes de inventario
description: "Este artículo proporciona información sobre la consolidación de dos o más lotes de inventario en un lote combinado."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: InventBatchJournalListPage, InventBatchJournalMerge
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 39782
ms.assetid: 07c5e98b-10fd-4f5c-b471-41d2150f47b0
ms.search.region: Global
ms.author: pjacobse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: f77012e7b64b7f153103e9bbe91e8ded202b509a
ms.openlocfilehash: 5abf8cf272924669cec6987a96f6565fffa54642
ms.lasthandoff: 03/31/2017


---

# <a name="merge-inventory-batches"></a>Combinar lotes de inventario

Este artículo proporciona información sobre la consolidación de dos o más lotes de inventario en un lote combinado. 

Cuando se combinan los lotes, los cálculos pueden ayudar a optimizar las características y los atributos de lote del lote combinado. Después de seleccionar los lotes de origen, puede revisar y cambiar el lote combinado antes de registrarlo. También puede transferir la combinación de lotes a un diario de inventario para su aprobación. El inventario luego se puede reservar o registrar directamente desde ese diario de inventario. Cuando se registra un lote combinado, el inventario se ajusta para los lotes de origen y el lote combinado.

## <a name="are-there-any-prerequisites"></a>¿Hay algún requisito previo?
Sí, existen algunas cosas que debe configurar antes de que pueda usar las herramientas de combinación de lotes. La siguiente tabla describe los requisitos previos.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Página</th>
<th>Descripción</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Nombres de diario, Inventario</td>
<td>Debe crear el nombre de diario que se usa de forma predeterminada al registrar combinaciones de lotes en diarios de inventario. Opcional pero muy recomendable: puede especificar que las reservas se deben realizar automáticamente cuando la combinación de lotes se transfiera al diario de inventario. De lo contrario, existe el riesgo de que se pueda cambiar un inventario disponible después de que se configuren los detalles de la combinación de lotes y se registre el diario. Para habilitar las reservas automáticas para el nombre de diario, seleccione <strong>Automático</strong> en <strong><strong>Reserva</strong></strong> el campo.</td>
</tr>
<tr class="even">
<td>Parámetros de gestión de inventario y almacenes</td>
<td>Debe especificar el nombre del diario predeterminado para el diario de inventario.</td>
</tr>
<tr class="odd">
<td>Productos emitidos</td>
<td>Estos son los valores recomendados para el artículo:
<ul>
<li>Para generar automáticamente números de lote para los lotes combinados, debe asignar el producto liberado a un grupo de números de lote. También puede especificar un número de lote manualmente cuando cree un lote combinado o seleccione un número de lote existente. Si selecciona un número de lote existente, asegúrese de que el lote seleccionado no se haya incluido en ninguna transacción de inventario.</li>
<li>Si utiliza valores de vida útil o fechas de consumo preferente para el producto liberado, las fechas de un lote combinado se calculan en función de la selección en el campo <strong>Cálculo de fecha de combinación de lotes</strong>. Están disponibles las siguientes opciones:
<ul>
<li><strong>Más temprana</strong>: el cálculo se basa en la fecha más temprana que se especifica para un lote de origen que se selecciona para la combinación de lotes.</li>
<li><strong>Más tardía</strong>: el cálculo se basa en la fecha más tardía que se especifica para un lote de origen que se selecciona para la combinación de lotes.</li>
<li><strong>Manual</strong>: no se realiza ningún cálculo. Si una fecha es la misma en todos los lotes de origen, se sugiere una fecha. Puede cambiar esa fecha. Si una fecha no es la misma en los lotes de origen, puede especificar la fecha manualmente.</li>
</ul></li>
</ul></td>
</tr>
<tr class="even">
<td>Grupo de números de lote</td>
<td>Opcional: para generar un número de lote al crear un lote combinado, debe asignar un grupo de número de lote al producto liberado. De lo contrario, puede especificar un número de lote manualmente.</td>
</tr>
</tbody>
</table>

## <a name="when-might-i-want-to-merge-batches-of-inventory"></a>¿Cuándo podría desear combinar los lotes de inventario?
Estos son algunos ejemplos de situaciones en las que podría ser útil combinar lotes:

-   Conforme Sammy camina por su almacén, observa que hay varios lotes del mismo artículo de los que hay cantidades bajas. Está esperando recibir varios envíos nuevos y se da cuenta de que puede liberar espacio combinando las cantidades incompletas en un nuevo lote.
-   Sammy recibe el inventario y desea combinar el nuevo lote con uno que ya ha recibido, para mejorar el valor de atributo de lote del lote existente.

## <a name="can-i-merge-batches-across-sites-and-legal-entities"></a>¿Se pueden combinar los lotes a través de sitios y entidades jurídicas?
No, solo puede combinar lotes que tengan las mismas dimensiones de almacenamiento del almacén y el sitio en una entidad jurídica. Sin embargo, puede especificar otra ubicación e identificación del pallet para el lote combinado.

## <a name="can-i-merge-partial-quantities"></a>¿Se puedo combinar cantidades parciales?
No, solo puede combinar la cantidad completa de lotes. La funcionalidad de combinación de lotes está pensada como característica de inventario, no como característica de producción.

## <a name="what-if-the-batches-have-different-batch-attribute-values"></a>¿Qué ocurre si los lotes tienen valores de atributo diferentes?
Cuando seleccione los lotes de origen para combinar en el lote combinado, Microsoft Dynamics 365 for Operations comprueba si todos los lotes tienen las características o los valores de atributos. Cuando un valor de atributo es el mismo, se sugerirá un valor para el lote combinado. Ese valor se puede modificar. Los valores de atributo que no son iguales se dejan en blanco para el lote combinado y se pueden especificar esos valores manualmente. Si el tipo de atributo de lote del valor de atributo es un número entero o una fracción, y los valores no son iguales para todos los lotes de origen, el valor se calculará mediante un cálculo de media ponderada. El valor calculado se redondea hacia arriba o hacia abajo al incremento más cercano. Si el valor está en blanco para un lote de origen, el lote y la cantidad no se incluyen en el cálculo. **Ejemplo** En el ejemplo siguiente se muestra un cálculo de promedio ponderado para un lote combinado. Dos de los lotes de origen tienen un valor en blanco para un tipo de atributo de lote que es un número entero. El atributo siguiente se asigna a los lotes de origen.

| Atributo | Mínimo | Incremento | Máximo |
|-----------|---------|-----------|---------|
| Categoría     | 3       | 3         | 30      |

Los lotes de origen tienen los valores de atributo siguientes para el atributo de **Lote de categoría**.

| Lote | Cantidad | Atributo | Valor de atributo |
|-------|----------|-----------|-----------------|
| B1    | 10       | Categoría     | En blanco           |
| B2    | 15       | Categoría     | 15              |
| B3    | 20       | Categoría     | 20              |
| B4    | 25       | Categoría     | En blanco           |
| B5    | 30       | Categoría     | 25              |

Al agregar estos lotes como lotes de origen, se asignan los siguientes valores al lote combinado.

| Lote | Cantidad | Atributo | Valor de atributo |
|-------|----------|-----------|-----------------|
| B6    | 100      | Categoría     | 21              |

Los valores y las cantidades de los lotes B1 y B4 no se incluyen en el cálculo de la media ponderada. Por lo tanto, así es cómo se calcula el valor del lote combinado.

| Valor | Cantidad (peso)                              | Peso relativo | Peso relativo × Valor                                               |
|-------|------------------------------------------------|-----------------|-----------------------------------------------------------------------|
| 15    | 15                                             | 0.230769231     | 3.461538462                                                           |
| 20    | 20                                             | 0.307692308     | 6.153846154                                                           |
| 25    | 30                                             | 0.461538462     | 11.53846154                                                           |
|       | **Total:** 65, que es la suma de los pesos |                 | **Total:** 21,5384615, que se redondea a 21 (el incremento más cercano). |

## <a name="what-if-the-batches-have-different-batch-dates"></a>¿Qué ocurre si los lotes tienen diferentes fechas de lote?
Si los lotes tienen diferentes fechas de lote, algunas de las fechas se calculan en función de los valores del grupo **Fechas de lote** de la ficha desplegable **Lote combinado** de la página **Combinación de lotes**. El sistema calcula los valores de los campos en el grupo **Fechas de lote**. Estos valores incluyen la fecha de fabricación, la fecha de vencimiento, la fecha de comprobación de vida útil y la fecha de consumo preferente. Las fechas se calculan en función de la configuración del artículo en el grupo de campos **Datos del artículo** de la página **Detalles de producto emitido**. Puede cambiar los valores o introducirlos manualmente. Para el resto de fechas, no se realiza ningún cálculo. El mismo principio se usa para los valores de atributo de lote. Si una fecha es la misma para todos los lotes de origen, esa fecha se sugiere para el lote combinado. Si la fecha no es la misma para todos los lotes de origen, la fecha aparece en blanco en el lote combinado y se puede introducir manualmente.

## <a name="what-if-the-dimensions-are-different-on-the-batches-that-i-want-to-merge"></a>¿Qué ocurre si las dimensiones son diferentes en los lotes que quiero combinar?
Así es como se administran las dimensiones del producto, las dimensiones del seguimiento y las dimensiones del almacenamiento:

-   **Dimensiones de producto**: todas las dimensiones de producto para el artículo seleccionado deben ser iguales. No es posible combinar los lotes entre dimensiones de producto.
-   **Dimensiones de seguimiento**: se genera automáticamente un nuevo número de lote si se especifica un grupo de número de lote para el artículo. Si no se asigna un grupo de número de lote a un artículo, puede seleccionar un lote existente o especificar el número manualmente. Los números de serie se transfieren del lote de origen a las líneas de diario del inventario del lote combinado.
-   **Dimensiones de almacenamiento**: las dimensiones de almacenamiento del sitio y del almacén deben ser iguales para todos los lotes de origen y para el lote combinado. Sin embargo, puede especificar una ubicación nueva e identificación del pallet para el lote combinado.

## <a name="how-does-posting-work"></a>¿Cómo funciona el registro?
El registro funciona de dos maneras, en función de si usa un proceso de aprobación para los diarios. Puede usar las acciones **Transferir al diario** y **Registrar la combinación de lotes** para transferir la combinación de lotes a un diario donde se pueda verificar y registrar, o puede registrar la combinación de lotes directamente. La diferencia principal entre las dos acciones es que una transferencia a un diario no registra la combinación de lotes. Ambas acciones crean un nuevo lote si no se selecciona un lote existente, actualizarán todos los detalles de lotes y valores de atributo, y crearán un diario de inventario.

-   **Transferir al diario**: transfiere los detalles de la combinación de lotes a un nuevo diario de inventario. Si ha configurado reservas automáticas, se reservan las cantidades de los lotes de origen. Los detalles de la combinación de lotes no se pueden cambiar. Para modificar la combinación de lotes, debe eliminar el diario. El diario se puede usar como tarea que otro empleado debe realizar más adelante. Se garantiza la reserva de la cantidad del lote a la línea de diario. Esta asignación permite a un planificador de calidad o a un responsable de almacén crear tareas para sus empleados.
-   **Registrar la combinación de lotes**: registra la combinación de lotes directamente. Esta acción puede llevarse a cabo una vez que se ha producido la combinación física.

Puede aprobar el diario de inventario para la combinación de lotes de la página de lista **Todas las combinaciones de lotes**. Haga clic en ** Journal ** &gt; ** Registrar **. Después de registrar un diario, no es posible modificar los detalles del lote combinado. Una vez transferida una combinación de lotes a un diario de inventario, puede cambiar los detalles si se elimina el diario.

## <a name="after-i-merged-a-catchweight-item-why-cant-i-see-the-catchweight-information-in-the-inventory-journal"></a>¿Una vez que combinara un artículo de catchweight, por qué no puedo ver la información de catchweight en el diario de inventario?
Puede combinar lotes de artículos con peso capturado de la misma forma que con el resto de artículos. Sin embargo, la información de peso capturado no aparece en el diario de inventario. Se recomienda comprobar la información de peso capturado antes de transferir la combinación de lotes al diario de inventario.


