---
title: Recuento cíclico
description: Este artículo describe cómo puede usar el recuento cíclico con la solución de almacenamiento que está disponible en Gestión de almacenes. Este artículo no se aplica a la solución de almacenamiento que está disponible en Gestión de inventarios.
author: Mirzaab
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSCycleCountPlan, WHSCycleCountPlanListPage, WHSCycleCountThreshold, WHSWorkTableListPage, SalesShipmentDeviation, WHSRFMenuItemCycleCount, WHSWorkLineCycleCount
audience: Application User
ms.reviewer: kamaybac
ms.custom: 50671
ms.assetid: 49f5c431-b043-4170-aa24-b7d5d1ee063e
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: da7aef93cf994c40410598ab9c4ff2b21f4750e7
ms.sourcegitcommit: 28a726b3b0726ecac7620b5736f5457bc75a5f84
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/29/2022
ms.locfileid: "9065940"
---
# <a name="cycle-counting"></a>Recuento cíclico

[!include [banner](../includes/banner.md)]

Este artículo describe cómo puede usar el recuento cíclico con la solución de almacenamiento que está disponible en Gestión de almacenes. Este artículo no se aplica a la solución de almacenamiento que está disponible en Gestión de inventarios.

La cuenta de ciclo es un proceso de almacén que puede usar para revisar artículos de inventario disponibles. El proceso del recuento cíclico se puede describir en tres pasos:

1.  **Crear un trabajo de recuento cíclico**: el trabajo recuento cíclico se pueden crear automáticamente en función de los parámetros de umbral para artículos o mediante un plan de recuento cíclico. También puede crear manualmente trabajos de recuento cíclico mediante los parámetros de almacén o de artículo en las páginas **Trabajo de recuento cíclico por artículo** o **Trabajo de recuento cíclico por ubicación**.
2.  **Procesar el recuento cíclico**: una vez creado el trabajo de recuento cíclico, realice el trabajo de recuento cíclico contando los artículos de una ubicación de almacén y usando a continuación un dispositivo móvil para especificar el resultado en Dynamics 365 Supply Chain Management. Como alternativa, puede contar los artículos de una ubicación de almacén sin crear el trabajo de recuento cíclico. Este proceso se denomina *recuento cíclico puntual*.
3.  **Resolver diferencias en el valor de recuento**: tras un recuento cíclico, todos los artículos que tengan diferencias en el valor del recuento tendrán un estado de trabajo de **Revisión pendiente** en la página **Todo el trabajo**. Puede resolver estas diferencias en la página **Revisión pendiente del trabajo de recuento cíclico**.

En la ilustración siguiente se muestra el proceso de recuento cíclico. ![Flujo del proceso de recuento cíclico.](./media/performcyclecountinginawarehouselocation.jpg)

## <a name="cycle-counting-prerequisites"></a>Requisitos previos de recuento cíclico
La tabla siguiente muestra los requisitos previos que deben cumplirse para poder usar el recuento cíclico.
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Requisito previo</th>
<th>Descripción</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Artículo</td>
<td>El artículo se debe habilitar para procesos de administración de almacenes (WMS).</td>
</tr>
<tr class="even">
<td>Almacén</td>
<td>El almacén se debe habilitar para procesos de administración de almacenes (WMS). Para habilitar el almacén para WMS, en la página <strong>Almacenes</strong>, seleccione el almacén y, a continuación, seleccione la opción <strong>Usar procesos de gestión de almacenes</strong>. Para permitir que los trabajadores muevan pallets durante un recuento cíclico, en la ficha desplegable <strong>Administración de almacenes</strong>, seleccione la opción <strong>Permitir movimientos de pallet durante el recuento cíclico</strong>.</td>
</tr>
<tr class="odd">
<td>Grupos de trabajo</td>
<td>Opcional: Crear un grupo de trabajo para segregar el trabajo del almacén, en función del tipo de trabajo (en este caso, el trabajo de recuento cíclico).</td>
</tr>
<tr class="even">
<td>Ubicaciones</td>
<td>Habilitar el recuento cíclico de ubicaciones. Para permitir el recuento cíclico para una ubicación de almacén, en la página <strong>Perfiles de ubicación</strong>, seleccione la opción <strong>Permitir recuento cíclico</strong>.</td>
</tr>
<tr class="odd">
<td>Parámetros de gestión de almacenes</td>
<td>Configurar parámetros para el recuento cíclico. En la página <strong>Parámetros de gestión de almacenes</strong>, especifique el código del tipo de ajuste predeterminado, el id. de clase de trabajo y la prioridad de trabajo para el recuento cíclico.</td>
</tr>
<tr class="even">
<td>Dispositivo móvil</td>
<td><ul>
<li>Cree un elemento de menú para uno de los siguientes métodos en la página <strong>Elementos de menú del dispositivo móvil</strong>:
<ul>
<li>Recuento cíclico dirigido por el usuario</li>
<li>Recuento cíclico dirigido por el sistema</li>
<li>Agrupación de recuentos cíclicos</li>
<li>Recuento cíclicos puntual</li>
</ul>
</li>
<li>Configure un menú para el dispositivo móvil.</li>
<li>Cree una cuenta de usuario de trabajo y asigne un menú de dispositivo móvil al id. de usuario de trabajo.</li>
</ul></td>
</tr>
<tr class="odd">
<td>Tarea de configuración relacionada</td>
<td>Configurar un plan de recuento cíclico para una ubicación de almacén.</td>
</tr>
</tbody>
</table>

## <a name="automatically-create-cycle-counting-work"></a>Crear automáticamente el trabajo de recuento cíclico
Existen dos formas de programar la creación recurrente del trabajo de recuento cíclico: configurar umbrales de recuento cíclico o configurar planes de recuento cíclico.

-   Un umbral de recuento cíclico indica el límite de cantidad o porcentaje de los artículos de inventario. El trabajo de recuento cíclico se crea automáticamente cuando se alcance el límite de umbral.
-   El plan de recuento cíclico crea trabajo de recuento cíclico inmediatamente o periódicamente a través de una trabajo por lotes. Cuando se crea el trabajo de recuento cíclico, la línea de trabajo de recuento incluye información acerca de la ubicación que se contará. El inventario disponible asociado a esta ubicación no se bloquea y está por lo tanto disponible para el proceso de reserva y de salida aunque exista un trabajo de recuento abierto.

### <a name="create-cycle-counting-work-based-on-threshold-parameters-for-items"></a>Crear un trabajo de recuento cíclico basado en parámetros de umbral para artículos

El trabajo de recuento cíclico se puede crear cuando el número de artículos está por debajo de un valor de umbral específico en una ubicación. Por ejemplo, hay 60 artículos en una ubicación que tiene un umbral del recuento cíclico de 40. Durante una transacción de pedido de ventas, 25 artículos se seleccionan de la ubicación y se colocan en una ubicación provisional. Dado que el nuevo recuento de artículos, 35, es inferior a la cantidad umbral, el trabajo de recuento cíclico se crea automáticamente para la ubicación.

### <a name="schedule-cycle-counting-work"></a>Trabajo de recuento cíclico de programación

Puede programar los planes de recuento cíclico para crear trabajo de recuento cíclico inmediatamente o periódicamente. Al configurar planes de recuento cíclico, puede controlar el grupo de trabajo para el que se crea el trabajo de recuento cíclico, el número máximo de recuentos cíclicos que se crean para artículos en distintas ubicaciones y el número de días antes de que una ubicación de almacén se cuente de nuevo. Por ejemplo, un artículo está disponible en tres ubicaciones del almacén y el número máximo de recuentos cíclicos se establece en **2**. En este caso, al ejecutar el plan de recuento cíclico, se crean dos recuentos cíclico para las dos ubicaciones en las que está presente el artículo. Como otro ejemplo, establece el número de días entre recuentos cíclicos en **5**. En este caso, el trabajo de recuento cíclico se crea cada cinco días. Sin embargo, si el trabajo de recuento cíclico se procesa el día 3, el siguiente trabajo de recuento cíclico se creará cinco días después del último recuento cíclico procesado, el día 8.

## <a name="create-cycle-counting-work-manually"></a>Crear un trabajo de recuento cíclico manualmente
Para crear el trabajo de recuento cíclico manualmente, puede usar las páginas **Trabajo de recuento cíclico por artículo** o **Trabajo de recuento cíclico por ubicación**. Puede especificar el número máximo de recuentos cíclicos que se deben crear. Por ejemplo, si el encargado de almacén especifica un valor de **5**, se crea un trabajo de recuento cíclico para cinco ubicaciones aunque el artículo esté presente en 10 ubicaciones. También puede seleccionar un id. de grupo de trabajo para el que se crean los id. de trabajo de recuento cíclico. Cuando se procesa un id. de grupo de trabajo para el recuento cíclico, los id. de trabajo de recuento cíclico que se asignan al grupo de trabajo se procesan como un grupo.

## <a name="perform-a-cycle-count-by-using-a-mobile-device"></a>Realizar un recuento cíclico mediante un dispositivo móvil
Hay varios métodos para procesar un trabajo de recuento cíclico mediante Supply Chain Management en un dispositivo móvil:

-   **Dirigido por el usuario**: el trabajador puede especificar un id. de trabajo de recuento cíclico que tiene el estado de **Abierto**.
-   **Dirigido por el sistema**: Supply Chain Management asigna al trabajador un identificador de trabajo de recuento cíclico.
-   **Agrupación de recuentos cíclicos**: el trabajador puede agrupar los id. de trabajo de recuento cíclico que son específicos de una ubicación, un área o a un grupo de trabajo en particular.
-   **Recuento cíclico puntual**: el trabajador puede contar los artículos de una ubicación de almacén en cualquier momento, sin crear el trabajo de recuento cíclico. Para realizar el recuento cíclico puntual en una ubicación, el trabajador especifica el id. de ubicación.

En el siguiente ejemplo se muestra cómo puede realizar un recuento cíclico puntual mediante un dispositivo móvil. Las instrucciones que ve el trabajador en el dispositivo varían, en función de la configuración del elemento de menú para el recuento cíclico puntual.

1.  En el dispositivo móvil, seleccione el elemento de menú para procesar el trabajo de recuento cíclico puntual.
2.  Registre la ubicación para la que desea realizar el recuento cíclico puntual.
3.  Registre y confirme el número de artículo y la cantidad contada del artículo. **Nota:** El estado del trabajo de recuento cíclico se actualiza como **Revisión pendiente** o como **Cerrado** en la página **Todo el trabajo**, en función de los parámetros establecidos en la página **Trabajador**.
4.  Opcional: repita el paso 3 para los artículos restantes de la ubicación y confirme que no haya artículos adicionales disponibles para contar.

## <a name="resolve-cycle-counting-differences"></a>Resolver diferencia de recuento cíclico
Se produce una diferencia de recuento cíclico en los siguientes escenarios si la opción **Es un supervisor de recuentos cíclicos** se establece en **No** para un identificador de usuario de trabajo:

-   El valor de recuento no se encuentra dentro de los límites de desviación que se especifican en los campos **Límite de porcentaje máximo** o **Límite de la cantidad máxima** en la página **Usuarios de trabajo**. Por ejemplo, la cantidad de inventario disponible en una ubicación es de 50 y el límite de desviación del usuario de trabajo es de 10. Si el usuario de trabajo especifica un valor que no está entre 40 y 60, se produce una diferencia.
-   El valor de recuento cíclico difiere de la cantidad de inventario disponible y no se establecen límites de desviación.

Puede ajustar diferencias en el valor de recuento y aceptar a continuación el valor de recuento en la página **Revisión pendiente del trabajo de recuento cíclico**. Puede comprobar el recuento modificado de la cantidad del artículo en la página **Inventario disponible por ubicación**. El valor de recuento se rechaza si no se puede aprobar la diferencia.

## <a name="additional-resources"></a>Recursos adicionales
[Configurar dispositivos móviles para el trabajo de almacén](configure-mobile-devices-warehouse.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]