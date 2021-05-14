---
title: Los campos de peso en las líneas de carga no coinciden con los campos de peso en la carga
description: Los campos de peso en las líneas de carga no coinciden con los campos de peso en la carga
author: perlynne
ms.date: 04/15/2021
ms.topic: troubleshooting
ms.search.form: WHSShipmentDetails_WHSShipConfirm
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-05-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 639b82a9d46b74f179d6904d2c3b8e7dfb813b58
ms.sourcegitcommit: 5f5afb46431e1abd8fb6e92e0189914b598dc7fd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2021
ms.locfileid: "5924360"
---
# <a name="the-weight-fields-on-load-lines-dont-match-the-weight-fields-on-the-load"></a>Los campos de peso en las líneas de carga no coinciden con los campos de peso en la carga

Códigos de error: WHSLoadWeightOnLinesDoNotMatchLoadWarning

## <a name="symptoms"></a>Síntomas

El sistema muestra el siguiente mensaje de error:

> Los campos de peso en las líneas de carga no coinciden con los campos de peso en la carga %1. Ejecute la comprobación de coherencia del peso de la carga del almacén para volver a calcular los campos de peso.

## <a name="cause"></a>Causa

Los campos **Peso neto** y **Peso muerto** están configurados en *0* (cero) en la línea de carga. Sin embargo, los campos de peso no están configurados en *0* para las medidas de peso del producto. Cuando los campos de peso no están configurados en la línea de carga, cualquier corrección de la cantidad en la línea de carga podría causar un cálculo de peso incorrecto en la carga. Este problema puede ocurrir si se han cambiado los pesos del producto desde que se creó la línea de carga.

## <a name="resolution"></a>Resolución

De forma predeterminada, cuando se crea una línea de carga, los campos de peso del producto se introducen en ella. Si el peso es cero, puede volver a calcularlo utilizando la funcionalidad *Comprobación de la coherencia del peso de la carga del almacén*.

1. Vaya a **Administración del sistema \> Tareas periódicas \> Base de datos \> Comprobación de coherencia**.
1. En el cuadro de diálogo **Comprobación de coherencia**, establezca el campo **Módulo** en *Gestion de almacenes*.
1. Establezca el campo **Comprobar/arreglar** en *Arreglar error*.
1. En la lista de casillas, seleccione la casilla **Comprobación de la coherencia del peso de la carga del almacén** y asegúrese de que solo esté resaltada la fila de esta casilla.
1. En la parte superior de la lista de casillas, seleccione el botón de puntos suspensivos (**...**) y luego seleccione **Diálogo** en el menú.
1. En el cuadro de diálogo **Comprobación de la coherencia del peso de la carga del almacén**, configure los siguientes campos para especificar los criterios para los que se debe ejecutar la comprobación de coherencia:

    - **Id. de carga:** especifique un id. de carga. Deje este espacio en blanco para comprobar todos los id. de carga.
    - **Número de artículo:**: especifique un número de artículo. Deje este espacio en blanco para comprobar todos los artículos.
    - **recalcular siempre el peso de las cargas:** establezca esta opción en *Sí*.
    - **Permitir sobrescribir el peso en las líneas de carga:** establezca esta opción en *Sí*.

1. Seleccione **Aceptar** para cerrar el cuadro de diálogo **Comprobación de coherencia del peso de la carga del almacén**.
1. Seleccione el botón de puntos suspensivos y luego seleccione **Ejecutar** en el menú.

El peso se vuelve a calcular según los criterios que especificó. Seleccione el vínculo **Detalles del mensaje** para ver el resultado de la comprobación de coherencia.
