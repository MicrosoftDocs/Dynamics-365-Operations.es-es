---
title: Extractos comerciales
description: Este tema describe cómo se crean y registran los extractos.
author: ashishmsft
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailParameters
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 85183
ms.assetid: df9c62a2-6f13-4a08-bdca-07d041172c1b
ms.search.region: Global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: Retail July 2017 update
ms.openlocfilehash: 9e88a8b22b73aca5c2cee6984ecad3c62e597102
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "1568008"
---
# <a name="retail-statements"></a>Extractos comerciales

[!include [banner](includes/banner.md)]

En Microsoft Dynamics 365 for Retail, el proceso de registro de extractos se utiliza para contabilizar las transacciones que se producen en el punto de venta (POS) o PDV moderno (MPOS) de la nube. El proceso de registro de extractos usa la programación de distribución para extraer un conjunto de transacciones de PDV en el cliente de la central (HQ). Los parámetros definidos en las páginas **Parámetros de ventas al por menor** y **Tiendas** se usan para seleccionar las transacciones que se extraen en extractos individuales.

La siguiente ilustración muestra el proceso de registro de extractos. En este proceso, las transacciones que se registran en el PDV se transmiten al cliente mediante el Programador de tareas Retail. Después de que el cliente reciba las transacciones, puede crear, calcular y registrar el extracto de la transacción para el almacén.

[![Proceso de registro de extractos](./media/retail-statements.png)](./media/retail-statements.png)

## <a name="creating-and-posting-statements"></a>Crear y registrar extractos

Puede crear un extracto manualmente o mediante procesos por lotes que configure para ejecutarse periódicamente en el día. En ambos casos, se usan los pasos siguientes para crear y registrar extractos.

### <a name="create-the-statement"></a>Crear el extracto

Este paso identifica la tienda para la que se ha creado el extracto manualmente. Si configura un proceso por lotes, puede crear automáticamente extractos para todas las tiendas, en función de una programación que defina.

### <a name="calculate-the-statement"></a>Calcular el extracto

En este paso, las líneas de transacción están seleccionadas según los criterios definidos para cada tienda en las páginas **Parámetros comerciales** y **Tiendas**. En estas páginas, puede definir los criterios y especificar cómo se calculan las transacciones. Para ver una lista de las transacciones incluidas en el extracto antes de calcular el extracto, use la página **Transacciones**.

Un cálculo de extracto usa declaraciones de formas de pago de las cajas registradoras como importe contado. También puede escribir el importe contado manualmente. El extracto muestra la diferencia entre el importe de venta de las transacciones y el importe contado real en todos los métodos de pago. El extracto se registra únicamente si esta diferencia es inferior a la diferencia de registro máxima que se ha definido para la tienda.

> [!NOTE]
> El proceso de cálculo de extractos usa la secuencia numérica global.

Al calcular un extracto, el cálculo incluye las tareas siguientes:

- Marque las transacciones que no se incluyeron en un cálculo de extracto anterior para el intervalo de fechas seleccionado.
- Calcule los importes totales especificados como forma de pago en las transacciones seleccionadas. Los resultados se muestran en las líneas de extracto, en función del método de extracto:

    - Si el método de extracto es **Total**, se crea una línea por cada método de pago en las transacciones seleccionadas.
    - Si el método de extracto es **Personal**, se creará una línea para cada método de pago en las transacciones que realice el empleado seleccionado.
    - Si el método de extracto es **Terminal del PDV**, se creará una línea para cada método de pago en las transacciones que se realicen en el registro seleccionado.
    - Si el método de extracto es **Turno**, se creará una línea para cada método de pago en las transacciones que se realicen durante un turno.

Si la casilla **Dividir por método de extracto** está seleccionada en la página **Tiendas**, se crea un extracto independiente en función del valor seleccionado en el campo **Método de extracto** .

Si el horario de operaciones de la tienda se extiende más allá de la medianoche, puede configurar un registro de extractos de modo que se base en el final de la jornada laboral en lugar del final del día de calendario.

En la página **Tiendas**, en la ficha desplegable **Extracto/cierre**, en el campo **Final del día laboral**, especifique la hora en que debe registrarse la última transacción para que se incluya en el extracto del día laboral. Active la casilla **Registrar como día laboral** para registrar las transacciones dentro del mismo día laboral. Cuando se registra el extracto, las transacciones que se registran dentro mismo día laboral se pueden incluir en el mismo pedido de ventas, incluso si algunas transacciones se producen antes de la medianoche y otras después de la medianoche.

#### <a name="example-post-a-statement-for-a-business-day-that-extends-over-two-calendar-days"></a>Ejemplo: registre un extracto para un día laboral que se extienda más de dos días de calendario

Una tienda está abierta entre las 8:00 y las 3:00, y la casilla **Registrar como día laboral** se selecciona en la configuración de la tienda. El 31 de mayo, el almacén registra transacciones entre las 8:00 y la medianoche. El almacén también registra transacciones entre las 00:01 y las 3:00 el 1 de junio.

Si el almacén registra el extracto para el cierre del día laborable, el pedido de ventas que se genera incluye todas las transacciones registradas entre las 8:00 y las 3:00., aunque se hayan realizado transacciones en dos días, el 31 de mayo y el 1 de junio.

Si la casilla **Registrar como día laboral** se desactiva para la misma tienda, se generan pedidos de ventas independientes cuando el almacén registra el extracto para el cierre del día laboral. Un pedido de ventas incluye las transacciones registradas entre las 8:00 y la medianoche del 31 de mayo, y el segundo pedido de ventas incluye las transacciones registradas entre las 00:01 y las 3:00 del 1 de junio.

> [!NOTE]
> Antes de poder crear extractos, debe cerrar los turnos en el período del extracto.

### <a name="post-the-statement"></a>Registrar el extracto

Cuando se registra un extracto, los pedidos de venta y las facturas se crean para las ventas minoristas en el extracto.

- Las ventas al por mayor se agregan en un pedido de ventas y se facturan para el cliente predeterminado asignado a la tienda.
- Las ventas minoristas para las que se ha agregado un cliente a la transacción en Microsoft Dynamics 365 for Retail generan pedidos de venta y facturas independientes, una para cada cliente único.

Los diarios de pago se crean automáticamente para los pagos en el extracto, y el inventario se actualiza para la tienda del PDV.
