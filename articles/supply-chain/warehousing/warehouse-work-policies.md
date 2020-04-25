---
title: Visión general de las directivas de trabajo de almacén
description: Control de las directivas de trabajo de almacén si el trabajo del almacén se crea mediante procesos de almacén en la fabricación, en función de tipo de pedido del trabajo, la ubicación de inventario y el producto.
author: johanhoffmann
manager: tfehr
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSWorkPolicy
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 196561
ms.assetid: cbf48ec6-1836-48d5-ad66-a9b534af1786
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: 3fe22a92b445abbf6d1dcc67ead878db3f80d532
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2020
ms.locfileid: "3204571"
---
# <a name="warehouse-work-policies-overview"></a>Visión general de las directivas de trabajo de almacén

[!include [banner](../includes/banner.md)]

Control de las directivas de trabajo de almacén si el trabajo del almacén se crea mediante procesos de almacén en la fabricación, en función de tipo de pedido del trabajo, la ubicación de inventario y el producto.

Esta directiva de trabajo controla si el trabajo del almacén se ha creado para los procesos de almacén en la fabricación. Puede configurar la directiva de trabajo mediante una combinación de **tipos de pedido de trabajo**, la **ubicación del inventario**, y un **producto**. Por ejemplo, se ha informado a la ubicación de salida 001 que el producto L0101 ha finalizado. El producto terminado se consume más adelante en otro pedido de producción en la ubicación de salida 001. En este caso, puede configurar una directiva de trabajo para evitar que el trabajo para productos terminados se deseche por haberse creado cuando se informa a la ubicación de salida 001 que el producto L0101 ha finalizado. La directiva de trabajo es una entidad individual que puede ser descrita mediante la siguiente información:

-   **Nombre de la directiva de trabajo**(el identificador único de la directiva de trabajo)
-   **Tipos de pedido de trabajo** y **Método de creación de trabajo**
-   **Ubicaciones del inventario**
-   **Productos**

## <a name="work-order-types"></a>Tipos de pedido de trabajo
Puede seleccionar los siguientes tipos de pedido de trabajo:

-   Ubicación de bienes terminados
-   Ubicación de coproducto y producto derivado
-   Picking de materia prima

El campo de **Método de creación de trabajo** tiene el valor **Nunca**. Este valor indica que la directiva de trabajo evitará que se genere el trabajo del almacén para el tipo de pedido de trabajo seleccionado.

## <a name="inventory-locations"></a>Ubicaciones del inventario
Puede seleccionar una ubicación para la que se aplique la directiva de trabajo. Si no se asocia ninguna ubicación a una directiva de trabajo, la directiva de trabajo no se aplica a ningún proceso. En la página **Ubicaciones**, puede activar o cancelar la selección de la directiva de trabajo para una ubicación concreta.

## <a name="products"></a>Productos
Puede seleccionar un producto para el que se aplique la directiva de trabajo. Puede aplicar la directiva de trabajo a todos los productos o productos seleccionados.

## <a name="example"></a>Ejemplo
En el siguiente ejemplo, hay dos pedidos de producción, PRD-001 y PRD-00*2*. El pedido de producción PRD-001 tiene una operación llamada **Montaje**, en la que el producto SC1 se notifica a la ubicación O1 como terminado. El pedido de producción PRD-002 tiene una operación llamada **Pintura** y consume el producto SC1 de la ubicación O1. El pedido de producción PRD-002 también consume la materia prima RM1 de la ubicación O1. RM1 se almacena en la ubicación del almacén BULK-001 y el trabajo del almacén lo escogerá como recogida de materia prima a la ubicación O1. El trabajo de recogida se genera cuando se lanza la producción PRD-002. 

[![Directivas de trabajo de almacén](./media/warehouse-work-policies.png)](./media/warehouse-work-policies.png) 

Cuando desee configurar una directiva de trabajo del almacén para este escenario, debe tener en cuenta la siguiente información:

-   El trabajo del almacén para el almacenaje del producto terminado no es necesario cuando informa de que el producto SC1 se ha completado del pedido de producción PRD-001 a la ubicación O1. Esto sucede porque la operación **Pintura** del pedido de producción PRD-002 consume el SC1 en la misma ubicación.
-   El trabajo de almacén para la recogida de la materia prima se requiere para mover la materia prima RM1 de la ubicación del almacén BULK-001 a la ubicación O1.

A continuación se muestra un ejemplo de una directiva de trabajo que puede configurar, en función de estas cuestiones.


|                                       |                                       |
|---------------------------------------|---------------------------------------|
| <strong>Nombre de directiva de trabajo</strong><br> | <strong>Tipos de pedido de trabajo</strong><br> |
|         Sin almacenaje 01     `          |     - Almacenaje de bienes terminados<br>      |
|                                       |    <strong>Ubicaciones</strong><br>     |
|                                       |                 - O1                  |
|                                       |    <strong>Productos</strong> <br>     |
|                                       |                 - SC1                 |

Los siguientes procedimientos proporcionan instrucciones detalladas sobre cómo configurar la directiva de trabajo del almacén para esta situación. También describe un ejemplo de la configuración que muestra cómo informar de un pedido de producción que se ha completado a una ubicación no controlada por matrícula.

## <a name="set-up-a-warehouse-work-policy"></a>Configurar una directiva de trabajo de almacén
Los procesos de almacén no siempre incluyen trabajo de almacén. Al definir una directiva de trabajo, puede evitar la creación de trabajo para picking de materia prima y ubicación de bienes terminados para un conjunto de productos en ubicaciones específicas. Para crear este procedimiento se utiliza la empresa de datos de prueba USMF. 

PASOS (21)

|     |                                                                            |
|-----|----------------------------------------------------------------------------|
| 1.  | Vaya a Gestión de almacenes &gt; Configurar &gt; Trabajo &gt; Directivas de trabajo.        |
| 2.  | Haga clic en Nuevo.                                                                 |
| 3.  | En el campo Nombre de directiva de trabajo, escriba "Ningún trabajo de ubicación".                    |
| 4.  | Haga clic en Guardar.                                                                |
| 5.  | Haga clic en Agregar.                                                                 |
| 6.  | En la lista, marque la fila seleccionada.                                        |
| 7.  | En el campo Tipo de pedido de trabajo, seleccione "Ubicación de bienes terminados".            |
| 8.  | Haga clic en Agregar.                                                                 |
| 9.  | En la lista, marque la fila seleccionada.                                        |
| 10. | En el campo Tipo de pedido de trabajo, seleccione "Ubicación de coproducto y producto derivado". |
| 11. | Expanda la sección Ubicaciones del inventario.                                    |
| 12. | Haga clic en Agregar.                                                                 |
| 13. | En la lista, marque la fila seleccionada.                                        |
| 14. | En la lista Almacén, especifique “51".                                         |
| 15. | En el campo Ubicación, especifique o seleccione ·"001".                              |
| 16. | Expanda la sección Productos.                                               |
| 17. | En el campo Selección de productos, seleccione "Seleccionado".                         |
| 18. | Haga clic en Agregar.                                                                 |
| 19. | En la lista, marque la fila seleccionada.                                        |
| 20. | En el campo Número de artículo, especifique o seleccione "L0101".                         |
| 21. | Haga clic en Guardar.                                                                |

## <a name="report-a-production-order-as-finished-to-a-location-that-isnt-license-platecontrolled"></a>Informar de una orden de producción como terminada a una ubicación no controlada por matrícula.
Este procedimiento muestra un ejemplo de notificación de producto finalizado a una ubicación no controlada por matrícula. Una directiva aplicable de trabajo es el requisito previo para esta tarea. El procedimiento anterior muestra la configuración de la directiva de trabajo. 

PASOS (25)

<table>
<tbody>
<tr>
<td colspan="3"><strong>Subtarea: configurar una ubicación de salida.</strong></td>
</tr>
<tr>
<td></td>
<td>1.</td>
<td>Vaya a Administración de la organización &gt; Recursos &gt; Grupos de recursos.</td>
</tr>
<tr>
<td></td>
<td>2.</td>
<td>En la lista, seleccione el grupo de recursos "5102".</td>
</tr>
<tr>
<td></td>
<td>3.</td>
<td>Haga clic en Editar.</td>
</tr>
<tr>
<td></td>
<td>4.</td>
<td>En el campo Almacén de salida, especifique "51".</td>
</tr>
<tr>
<td></td>
<td>5.</td>
<td>En el campo Ubicación de salida, especifique "001".</td>
</tr>
<tr>
<td></td>
<td>6.</td>
<td>La ubicación 001 no es una ubicación controlada mediante matrículas de entidad de almacén. Puede configurar una ubicación de salida que no sea de matrículas de entidad de almacén si existe una directiva aplicable de trabajo para la ubicación.</td>
</tr>
<tr>
<td colspan="3"><strong>Subtarea: crear un pedido de producción y notificarlo como terminado.</strong></td>
</tr>
<tr>
<td></td>
<td>1.</td>
<td>Cierre la página.</td>
</tr>
<tr>
<td></td>
<td>2.</td>
<td>Vaya a Control de producción &gt; Pedidos de producción &gt; Todos los pedidos de producción.</td>
</tr>
<tr>
<td></td>
<td>3.</td>
<td>Haga clic en Nuevo pedido de producción.</td>
</tr>
<tr>
<td></td>
<td>4.</td>
<td>En el campo Número de artículo, especifique "L0101".</td>
</tr>
<tr>
<td></td>
<td>5.</td>
<td>Haga clic en Crear.</td>
</tr>
<tr>
<td></td>
<td>6.</td>
<td>En el panel de acciones, haga clic en Pedido de producción.</td>
</tr>
<tr>
<td></td>
<td>7.</td>
<td>Haga clic en Estimación.</td>
</tr>
<tr>
<td></td>
<td>8.</td>
<td>Haga clic en Aceptar</td>
</tr>
<tr>
<td></td>
<td>9.</td>
<td>Haga clic en Inicio.</td>
</tr>
<tr>
<td></td>
<td>10.</td>
<td>Haga clic en la pestaña General.</td>
</tr>
<tr>
<td></td>
<td>11.</td>
<td>En el campo Consumo automático de L. MAT, seleccione "Nunca".</td>
</tr>
<tr>
<td></td>
<td>12.</td>
<td>Haga clic en Aceptar</td>
</tr>
<tr>
<td></td>
<td>13.</td>
<td>Haga clic en Notificar como terminado.</td>
</tr>
<tr>
<td></td>
<td>14.</td>
<td>Haga clic en la pestaña General.</td>
</tr>
<tr>
<td></td>
<td>15.</td>
<td>Seleccione Sí en el campo Aceptar error.</td>
</tr>
<tr>
<td></td>
<td>16.</td>
<td>Haga clic en Aceptar</td>
</tr>
<tr>
<td></td>
<td>17.</td>
<td>En el panel de acciones, haga clic en Almacén.</td>
</tr>
<tr>
<td></td>
<td>18.</td>
<td>Haga clic en Detalles del trabajo.</td>
</tr>
<tr>
<td></td>
<td>19.</td>
<td>Cuando el pedido de producción se ha notificado como finalizado, no se ha generado ningún trabajo para ubicación. Esto ocurre porque se define una directiva de trabajo que impide que el trabajo se genere cuando el producto L0101 se notifique como finalizado para la ubicación 001.</td>
</tr>
</tbody>
</table>



