---
title: Actualmente se utilizan procesos de gestión de almacenes
description: Al reservar o liberar trabajo, es posible que reciba un mensaje de que los procesos de gestión de almacenes se están utilizando actualmente. Solucione el problema con uno de estos pasos.
author: SmithaNataraj
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: bfda2fae824cdc64d722310d20cf16e6306d766c
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477476"
---
# <a name="cant-reserve-or-release-work-because-processes-are-currently-being-used"></a>No se puede reservar ni liberar trabajo porque los procesos se están utilizando actualmente

## <a name="symptoms"></a>Síntomas

Mientras trabaja con fabricación discreta, recibe el siguiente error:

> Actualmente se utilizan procesos de gestión de almacenes. Si las líneas de trabajo aún no están registradas, puede cancelar el trabajo creado y cualquier línea de carga o envío, y luego continuar con el proceso de selección o envío.

## <a name="cause"></a>Causa

Este problema ocurre si intenta reservar o liberar trabajo para una línea, pero la transacción de inventario tiene un estado *Escogido*, que indica que el material ha sido recogido.

## <a name="resolution"></a>Resolución

Para arreglar este problema, siga uno de estos pasos.

- Cambiar el estado de la orden de producción a *Estimado* o *Liberado*.
- Abra la página de detalles del pedido de producción pertinente. En el panel de acciones, en la pesetaña **Almacén**, en el grupo **Detener**, seleccione **Detener y cancelar selección** para anular todas las transacciones seleccionadas. Luego seleccione **Quitar parada** para procesar la orden de producción.

Aquí hay una explicación de las funciones *Cancelar selección* y *Detener*:
  
- **Anular selección** - Esta función invierte el estado de las transacciones de inventario para las líneas de lista de materiales (L. MAT.) y las líneas de fórmula que tienen un estado de *Seleccionado* pasando por *En orden*. Cuando se completa el trabajo para el picking de materia prima, el estado de las líneas se establece en *Seleccionado*. Este estado evita que la orden de producción se restablezca a estado *Creado*. En este caso, puede utilizar la función *Anular selección* función para revertir las transacciones de estado *Seleccionado* y luego restablecer la orden de producción a estado *Creado*.
- **Detener** - Esta función establece un indicador **Detenido** en la orden de producción para evitar cualquier actualización de estado en la orden. Puede encontrar el indicador **Detenido** en la ficha desplegable **Almacén** de la página de detalles de la orden de producción.

> [!NOTE]
>
> - Los botones están visibles solo cuando se crea la orden de producción para los artículos que están habilitados para los procesos de almacén.
> - El grupo **Detener** es visible solo en la pestaña **Almacén** del Panel de acciones de la página de detalles de la orden de producción. No es visible en la ficha desplegable **Almacén** de la página de lista **Órdenes de producción**.
