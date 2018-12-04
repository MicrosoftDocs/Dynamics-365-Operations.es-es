---
title: Cierre de inventario
description: "Como parte del proceso para liquidar transacciones de emisión con transacciones de recepción, también puede elegir actualizar la contabilidad general para reflejar los ajustes realizados."
author: AndersGirke
manager: AnnBe
ms.date: 10/24/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventClosing
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 61973
ms.assetid: c210c882-6849-4704-b78c-a777dd6cfdb6
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: shylaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: dfb6b9c2f4bad95c165a8d8a1e888e7a67e66c69
ms.contentlocale: es-es
ms.lasthandoff: 11/03/2017

---

# <a name="inventory-close"></a>Cierre de inventario

[!include [banner](../includes/banner.md)]

Como parte del proceso para liquidar transacciones de emisión con transacciones de recepción, también puede elegir actualizar la contabilidad general para reflejar los ajustes realizados.

El proceso de cierre de inventario de liquida las transacciones de emisión con las transacciones de recepción en función del método de valoración de inventario seleccionado en el grupo de modelos del artículo. Como parte del proceso de liquidación, puede especificar que la contabilidad general se debe actualizar, de modo que refleje los ajustes realizados. No obstante, hasta el momento en que se ha ejecutado el cierre de inventario o el nuevo cálculo, las transacciones de emisión se registran con el precio de coste promedio móvil calculado. 

Tras el cierre de inventario, ya no podrá registrar en períodos anteriores a la fecha de cierre del inventario definida, a no ser que invierta el proceso de cierre de inventario completado. Por ejemplo, si se ejecuta el cierre de inventario para el período que finaliza el 31 de enero, no podrá registrar transacciones con una fecha anterior al 31 de enero. 

Los artículos de inventario se asignan a uno de dos tipos de inventario: artículo o servicio. El cierre de inventario realiza las mismas funciones para ambos tipos. Sin embargo, para los artículos de servicio, el cierre de inventario todavía liquidará las emisiones con las recepciones. 

La frecuencia con la que se ejecuta el proceso de cierre de inventario varía según la empresa. Sin embargo, el volumen de la transacción debe ayudar a determinar la frecuencia con la que decide ejecutar el cierre de inventario. Generalmente, las empresas ejecutan el cierre de inventario como parte del cierre de fin de mes y de los procedimientos de conciliación.

## <a name="inventory-recalculation-and-the-general-ledger"></a>Nuevo cálculo de inventario y contabilidad general
Si es necesario realizar ajustes en el inventario y en la contabilidad general durante un mes o durante otro período del inventario, puede ejecutar un nuevo cálculo del inventario en lugar del cierre de inventario. El nuevo cálculo de inventario realiza ajustes, pero no liquidaciones, en las transacciones del inventario. 

Durante el nuevo cálculo de inventario, se ajustan el inventario disponible y las transacciones de inventario, y se ejecutan los nuevos cálculos de inventario y los cierres de inventario. Estas tareas afectan a toda cuenta contable vinculada a la transacción de inventario original. 

**Ejemplo** 

Al crear un pedido de ventas a partir de un pedido de compra, se actualizarán las cuentas contables generales utilizadas en el pedido de ventas original. Incluso si las cuentas contables del grupo de artículos asignado al artículo se han modificado después del registro del pedido de ventas, y si un nuevo cálculo de inventario ha creado un importe de ajuste, este importe seguirá registrado en las cuentas contables originales. El importe ajustado no se registra en las nuevas cuentas contables asignadas al artículo. 

Una vez completada la actualización, podrá revisar el asiento contable que se ha registrado como resultado de una de estas tareas.

1.  En la página **Cierre y ajuste**, en la ficha **Visión general**, seleccione la actualización que se revisará.
2.  Haga clic en **Detalles** y, a continuación, seleccione **Asiento**.

## <a name="effects-of-the-inventory-close-process-on-the-general-ledger"></a>Efectos del proceso de cierre de inventario en la contabilidad general
Algunas de las tareas que se pueden llevar a cabo en la página **Cierre y ajuste** producen una actualización en la contabilidad general. Por ejemplo, la contabilidad general se actualiza al realizar ajustes en el inventario disponible, realizar ajustes en la transacción de inventario, ejecutar el nuevo cálculo del inventario y ejecutar el cierre del inventario. 

Las cuentas contables que se actualizan debido a estas tareas se vinculan a la transacción de inventario original. Por ejemplo, si se liquida un pedido de ventas a un pedido de compra, se ajustan las cuentas contables que se usaron para el pedido de ventas original. Este comportamiento se produce incluso si las cuentas contables del grupo de artículos que se asigna al artículo han cambiado desde que se registró el pedido de ventas. Después de que el cierre de inventario cree un importe de liquidación, este último aún se registrará en las cuentas contables originales, no en las nuevas cuentas contables que se asignan al artículo. Es posible que la contabilidad general también se actualice si invierte un cierre de inventario. 

**Notas:**

-   El cierre de inventario no es necesario si usa el método de valoración de costes estándar.
-   Antes de ejecutar el procedimiento de cierre, puede consultar una lista de artículos que no se pueden liquidar durante la actualización.
-   Se recomienda ejecutar el cierre de inventario durante las horas de menor actividad empresarial para lograr una distribución más uniforme de los recursos informáticos.

## <a name="the-inventory-close-log"></a> El registro de cierre del inventario
Una vez finalizado el procedimiento de cierre de inventario, es posible que un mensaje en el centro de mensajes informe de que un precio de coste unitario es incorrecto porque una transacción no se ha podido liquidar completamente. 

Antes de que se muestre este mensaje, el sistema informa sobre el número de artículo y la transacción afectada. El mensaje informa de que el importe de coste que se usa para esta transacción no se ha actualizado debido al cierre de inventario. Este mensaje aparece cuando no se puede liquidar una transacción del tipo de emisión. 

Durante el proceso de cierre de inventario, el sistema comprueba cada dimensión financiera para saber si hay más emisiones que recepciones hasta la fecha de cierre especificada. Este tipo de desequilibrio se puede deber a que no se ha registrado financieramente por completo una transacción de inventario a partir de un pedido de compra, porque la factura del proveedor aún no se ha recibido, o debido a que no se han registrado financieramente los componentes de la lista de materiales (L. MAT) incluidos en una producción a un nivel superior (No se ha calculado el coste de la subproducción). En este caso, el cierre subsiguiente no ajustará todas las emisiones al precio de coste correcto, porque no hay suficiente información de recepción disponible. 

Para cada ejecución del procedimiento de cierre, el sistema indica si se ha almacenado un registro que contiene las advertencias y si se puede consultar. 

Si recibe muchos mensajes de advertencia en el mensaje, se recomienda realizar las acciones siguientes:

-   Actualice las recepciones financieramente.
-   Avance la fecha de cierre.
-   Reevalúe los procedimientos empresariales.

En algunas circunstancias es posible que no pueda hacer nada en relación con las advertencias. Por ejemplo, si se usan marcas y el pedido de compra seleccionado tiene una fecha financiera posterior a la fecha de cierre, la fecha de cierre no se podrá modificar.

## <a name="reversing-a-completed-inventory-close"></a>Reversión de un cierre de inventario completado
En ocasiones, puede ser necesario invertir un cierre de inventario completado para devolver las liquidaciones al estado que tenían antes de realizarse los ajustes. Cuando se invierte un cierre de inventario completado, se abrirá también el inventario de forma que puedan introducirse los registros en el período aplicable al cierre de inventario. También se pueden realizar los cambios relacionados en la contabilidad general. Una vez haya terminado de realizar los ajustes, puede volver a ejecutar el cierre de inventario para el período en el que está trabajando. 

**Nota:** Solo se puede volver a abrir el período correspondiente al último cierre de inventario. Para invertir un cierre anterior del inventario, debe invertir cada cierre posterior de inventario uno a uno, comenzando por el cierre más reciente.




