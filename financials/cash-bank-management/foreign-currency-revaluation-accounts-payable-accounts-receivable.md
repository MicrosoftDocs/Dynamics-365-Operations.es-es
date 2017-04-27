---
title: "Revalorización de divisa extranjera para clientes y proveedores"
description: "Las fluctuaciones en los tipos de cambio hacen que el valor teórico (valor en los libros) de las transacciones abiertas en divisas extranjeras varíen con el tiempo. Este artículo proporciona información acerca del proceso de revalorización de divisa extranjera que ejecuta para actualizar el valor de las transacciones de proveedores y clientes abiertas."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: CustExchRateAdjustment, VendExchRateAdjustment
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 14211
ms.assetid: defb1ea5-1f3e-4859-87d8-3f9954d3f388
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 44d51807cd6bb64ae2c4bef58d8a445417ffa3a9
ms.openlocfilehash: 69a57cc5a2d652efc2ee14906c64b0dc741da31c
ms.lasthandoff: 03/31/2017


---

# <a name="foreign-currency-revaluation-for-accounts-payable-and-accounts-receivable"></a>Revalorización de divisa extranjera para clientes y proveedores

[!include[banner](../includes/banner.md)]


Las fluctuaciones en los tipos de cambio hacen que el valor teórico (valor en los libros) de las transacciones abiertas en divisas extranjeras varíen con el tiempo. Este artículo proporciona información acerca del proceso de revalorización de divisa extranjera que ejecuta para actualizar el valor de las transacciones de proveedores y clientes abiertas. 

El valor teórico, o valor en los libros, de las transacciones de proveedores abiertas en divisas extranjeras varía con el tiempo debido a las fluctuaciones del tipo de cambio. Para actualizar el valor de las transacciones de proveedores y clientes abiertas, ejecute un proceso de revalorización de divisa extranjera. Puede ejecutarse una revalorización de divisa extranjera tanto para clientes como para proveedores. Este proceso utiliza un nuevo tipo de cambio para revalorizar los importes abiertos o no liquidados en una fecha concreta. Las diferencias entre los importes registrados originales y los importes revalorizados generarán un beneficio no realizado o una pérdida para cada transacción abierta. Los subdiarios contables de proveedores y clientes se actualizarán a continuación para reflejar el beneficio no realizado o la pérdida, y se registrará un asiento en la contabilidad general.

## <a name="simulate-a-foreign-currency-revaluation"></a>Simulación de revalorización de divisa extranjera
Para poder revalorizar importes en divisa extranjera en las transacciones abiertas puede ejecutar un informe de simulación de la revalorización de divisa extranjera para la misma fecha y el mismo método. Para ejecutar el informe de simulación, en la página **Revalorización de divisa extranjera**, haga clic en el botón **Simulación**. El informe proporciona una vista previa del importe de beneficio no realizado o la pérdida, en función de los parámetros definidos para la simulación.

## <a name="process-a-foreign-currency-revaluation"></a>Procesamiento de una revalorización de divisa extranjera
Use la página **Revalorización de divisa extranjera** en **Tareas periódicas** para revalorizar las transacciones abiertas. Puede ejecutar el proceso en tiempo real o programarlo para ejecutarlo mediante un lote. Al definir los parámetros del proceso de revalorización, asegúrese de indicar si desea imprimir un informe con los resultados. El informe de revalorización no se puede volver a imprimir después de completarse el proceso. Si se genera el informe de revalorización de divisa extranjera, este mostrará los distintos saldos en el nivel de cliente o proveedor y el nivel de divisa:

-   Los saldos de clientes o proveedores con transacciones en divisa extranjera que se han revalorizado. Se muestran los saldos siguientes:
    -   El saldo original total en la divisa extranjera.
    -   El importe total de divisa extranjera en la divisa de contabilidad según la revalorización anterior.
    -   El importe total de divisa extranjera en la divisa de contabilidad según la revalorización actual.
    -   La diferencia entre el la revalorización anterior y la actual. Esta diferencia es la ganancia no realizada o la pérdida adicional.
-   El beneficio no realizado o pérdida total para cada divisa.

Se mantiene un registro cada vez que se ejecuta una revalorización de divisa extranjera. Desde la página **Evaluación de divisa extranjera**, seleccione **Transacciones** para ver la lista detallada de transacciones creadas a raíz de la revalorización. Cada transacción de asiento representa la transacción abierta que se volvió a evaluar. Si una transacción abierta se volvió a evaluar más de una vez, verá dos registros que usan el mismo asiento. Un registro será para la inversión del beneficio no realizado o la pérdida anterior, y el otro registro será para el nuevo beneficio no realizado o la pérdida. Para ejecutar el proceso de revalorización, haga clic en el botón **Revalorización de divisa extranjera**. Defina los ajustes oportunos para los parámetros siguientes:

-   **Método**: el método usado en el trabajo de revalorización de divisa extranjera seleccionado:
    -   **Estándar**: los trabajos de revalorización de divisa extranjera se registran, independientemente de si el resultado es una pérdida o una ganancia.
    -   **Mínimo**: los trabajos de revalorizaciones de divisa extranjera se registran solo si el resultado es una pérdida.
    -   **Fecha de factura**: los trabajos de revalorizaciones de divisa extranjera usan el tipo de cambio original de las transacciones, las cuales se reevalúan a su valor original en la divisa de contabilidad. Se cancela el efecto de la revalorización de divisa extranjera anterior que se haya producido.
-   **Fecha considerada**: la fecha en la que se encuentran todas las transacciones que tienen importes abiertos (no liquidados). Los importes en divisa extranjera se revalorizan con los tipos de cambio especificados en la página **Tipos de cambio de divisas** para la fecha considerada. Cuando los importes en divisa extranjera se revalorizan en una fecha considerada, esta fecha pasa a ser la fecha de última revalorización de divisa extranjera para las transacciones que se ajustan. Si decide ejecutar una revalorización de divisa extranjera para una fecha considerada anterior a la última fecha de revalorización de divisa extranjera en transacciones ya ajustadas, el trabajo periódico no ajusta las transacciones abiertas en la primera fecha considerada pero que tienen una fecha de revalorización de divisa extranjera del cambio más reciente.
-   **Fecha del índice**: la fecha que determina el tipo de cambio que se usa en la transacción de revalorización de divisa extranjera.
-   **Utilizar el perfil de contabilización desde**: el perfil de contabilización que se usa para introducir la cuenta predeterminada de cliente o proveedor para los asientos contables de las transacciones de revalorización de divisa extranjera:
    -   **Registro**: se utiliza el perfil de contabilización de la transacción del cliente.
    -   **Seleccionar**: el perfil de contabilización viene determinado por el campo **Perfil de contabilización**.
-   **Perfil de contabilización**: si se ha habilitado **Seleccionar** en el campo **Utilizar el perfil de contabilización desde**, el perfil de contabilización que se indique en este campo determina el perfil de contabilización de las transacciones de revalorización de divisa extranjera.
-   **Dimensiones financieras**: las dimensiones financieras contabilizadas en los asientos contables de las transacciones de revalorización de divisa extranjera:
    -   **Ninguno**: no se contabilizan dimensiones financieras. Si tiene una dimensión financiera necesaria en su estructura contable, el proceso de revalorización se ejecuta y crea los asientos contables sin ninguna dimensión financiera. Recibirá un mensaje de advertencia primero para que pueda cancelar el proceso de revalorización.
    -   **Tabla**: las dimensiones financieras de la cuenta de cliente o de proveedor se contabilizan en las transacciones de revalorización de divisa extranjera.
    -   **Registro**: las dimensiones financieras de la transacción que se está revalorizando se registran en las transacciones de revalorización de divisa extranjera. De forma predeterminada, las dimensiones financieras de la cuenta contable de cliente o proveedor de la transacción original se usarán para la cuenta principal de cliente o proveedor de la transacción de revalorización, y las dimensiones financieras de la cuenta contable de gastos/activos/ingresos de la transacción original se usarán para la cuenta principal de beneficio no realizado y pérdidas de la transacción de revalorización.





