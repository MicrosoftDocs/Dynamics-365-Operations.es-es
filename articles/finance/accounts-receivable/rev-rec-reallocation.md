---
title: Reasignación de reconocimiento de ingresos
description: Este tema proporciona información sobre la reasignación, que permite a las organizaciones volver a calcular los precios de los ingresos cuando se modifican los términos de una venta contractual. Incluye vínculos a otros temas que describen cómo reconocer los ingresos en múltiples escenarios.
author: kweekley
ms.date: 09/09/2021
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: Customer
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2020-12-21
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 7528202ed140dc2c0a7fc8c595178f155c3c1f75
ms.sourcegitcommit: 631d2cea52590af15f208e9af584446e85540fcf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2022
ms.locfileid: "8726138"
---
# <a name="revenue-recognition-reallocation"></a>Reasignación de reconocimiento de ingresos

[!include [banner](../includes/banner.md)]

La reasignación permite a las organizaciones volver a calcular los precios de los ingresos cuando se modifican los términos de una venta contractual. A efectos del reconocimiento de ingresos, los documentos del pedido de ventas se consideran el contrato.

Su organización debe determinar por sí misma si es necesaria la reasignación. Agregar una nueva línea a un pedido de ventas o agregar un nuevo pedido de ventas para un cliente podría no constituir un cambio en el contrato. Estos son los escenarios que podrían requerir una reasignación:

- Un cliente agrega o elimina artículos en un pedido de ventas después de que se ha facturado total o parcialmente.
- Se introdujeron varios pedidos de ventas, en estado confirmado o facturado, para el mismo contrato negociado.
- Un cliente devuelve o recibe un crédito por un artículo después de que el pedido de ventas original se ha facturado total o parcialmente.

Existen algunas limitaciones importantes en el proceso de reasignación:

- El proceso solo se puede ejecutar una vez. Por lo tanto, es importante que lo ejecute solo una vez que han finalizado todos los cambios.

    - Esta limitación se elimina en la versión 10.0.17 y posteriores.

- El proceso no se puede ejecutar en pedidos de ventas de proyectos.

    - Esta limitación se elimina en la versión 10.0.17 y posteriores.

- Si hay varios pedidos de ventas implicados, deben ser para la misma cuenta de cliente.
- Todos los pedidos de ventas que se reasignan deben estar en la misma divisa de transacción.
- El proceso no se puede revertir ni deshacer una vez ejecutado.

    - Esta limitación se elimina en la versión 10.0.17 y posteriores.

- La reasignación solo se puede realizar para pedidos de venta o para proyectos de pedidos de venta. No se puede realizar para una combinación de pedidos de venta y pedidos de venta de proyecto.

    - Esta limitación se elimina en la versión 10.0.17 y posteriores.

## <a name="set-up-reallocation"></a>Configuración de la reasignación

Hay un parámetro que afecta al proceso de reasignación.

Debido a que la reasignación se puede realizar en un pedido de ventas que se factura total o parcialmente, cualquier asiento contable anterior de la factura debe corregirse utilizando los nuevos precios de ingresos reasignados. Esta corrección se realiza mediante la inversión del asiento contable de la factura original y la contabilización de un nuevo asiento basado en los precios de los ingresos reasignados.

Cada organización debe decidir si la corrección debe actualizar solo la contabilidad general o si también debe actualizar los clientes. La decisión que se tome determina la configuración adecuada de la **Registrar correcciones de factura en clientes** en la pestaña **Reconocimiento de ingresos** de la página **Parámetros de Contabilidad general** (**Reconocimiento de ingresos \> Configuración \> Parámetros de Contabilidad general**). La configuración adecuada depende de cada escenario específico. Para obtener más información sobre posibles escenarios, utilice los vínculos de la sección [Escenarios de reasignación](#scenarios-for-reallocation) más adelante en este tema.

[![Pestaña Reconocimiento de ingresos en la página Parámetros de Contabilidad general.](./media/01_RevRecScenarios.png)](./media/01_RevRecScenarios.png)

Si la opción **Registrar correcciones de factura en clientes** se establece en **Sí**, el proceso de reasignación genera el siguiente resultado:

- Se crea un documento de crédito en clientes para revertir la factura que requiere corrección.

    - El documento de crédito reutiliza el número de factura original, pero se le agrega "-1" al final.
    - El documento de crédito se liquida automáticamente con la factura original. Si la factura original ya se liquidó con otro documento de crédito o pago, esa liquidación se revierte automáticamente.
    - El documento de crédito se contabiliza en la contabilidad general para revertir el asiento contable que se registró en la factura original. Sin embargo, las entradas de transacciones de Inventario y Coste de bienes vendidos (COGS) no se revierten.

- Se crea una nueva factura basada en los nuevos importes de precios reasignados en Clientes.

    - La nueva factura reutiliza el número de factura original, pero se le agrega "-2" al final.
    - La nueva factura se liquida automáticamente con cualquier documento de crédito o pago que se haya liquidado previamente con la factura original.
    - La nueva factura se contabiliza en la contabilidad general utilizando los nuevos importes de precios de ingresos reasignados. No se registra en las cuentas de Inventario y COGS nuevamente, porque esas entradas se mantienen en el asiento contable de la factura original.

Si la opción **Registrar correcciones de factura en clientes** se establece en **No**, el proceso de reasignación genera el siguiente resultado:

- Un asiento contable de inversión se contabiliza solo en la contabilidad general. Se invierte toda la contabilidad de la factura original, excepto los asientos de Inventario y COGS.
- Solo se registra un nuevo asiento contable en la contabilidad general, según los nuevos precios de ingresos reasignados. No se registra en las cuentas de Inventario y COGS nuevamente, porque esas entradas se mantienen en el asiento contable de la factura original.
- La factura de la página **Transacciones del cliente** no se ve afectada ni modificada, pero aún refleja la entrada contable original. No hay referencia a la reversión o nuevos asientos contables.

Como se ha mencionado, solo puede actualizar la contabilidad general, o bien puede actualizar tanto la contabilidad general como clientes. Ambos enfoques tienen sus pros y sus contras. Le recomendamos que evalúe los requisitos de su organización para determinar qué opción debe utilizar. Si actualiza tanto la contabilidad general como clientes, los asientos contables correctos se mostrarán en la nueva factura y se podrán ver en el documento de la página **Transacciones del cliente**. Además, el proceso de liquidación utilizará los asientos contables actualizados para registrar los descuentos por pronto pago y las ganancias o pérdidas. Por otro lado, el documento de crédito y la nueva factura aparecerán en los extractos de los clientes y los informes de antigüedad, al igual que otros documentos de crédito y facturas de clientes. La descripción de esos documentos indicará que se crearon mediante una corrección contable.

## <a name="run-the-reallocation-process"></a>Ejecución del proceso de reasignación

Para iniciar el proceso de reasignación, seleccione **Reasignar precio con nuevas líneas de pedido** en cualquier pedido de ventas que deba reasignar. Alternativamente, vaya a **Reconocimiento de ingresos \> Tareas periódicas \> Reasignar precio con nuevas líneas de pedido** y luego introduzca los filtros apropiados, como la cuenta del cliente.

[![Página Reasignar precio con nuevas líneas de pedido.](./media/02_RevRecScenarios.png)](./media/02_RevRecScenarios.png)

La cuadrícula superior de la página **Reasignar precio con nuevas líneas de pedido** se llama **Ventas**. Enumera los pedidos de ventas del cliente. Seleccione los pedidos de ventas que deben reasignarse. Si un pedido de ventas tiene un identificador de reasignación, ya se ha marcado para reasignación por otro usuario. Si uno o más pedidos de ventas se reasignaron anteriormente y deben incluirse en otra reasignación, primero se debe deshacer la reasignación de esos pedidos de ventas. Luego se puede incluir en una nueva reasignación. Para obtener información más detallada, consulte las secciones [Deshacer una reasignación](#undo-a-reallocation) y [Reasignar varias veces](#reallocate-multiple-times) más adelante en este tema.

La cuadrícula inferior de la página se llama **Líneas**. Al seleccionar uno o más pedidos de ventas en la cuadrícula **Ventas**, la cuadrícula **Líneas** muestra las líneas correspondientes a esos pedidos. Seleccione las líneas de pedidos de ventas que deben reasignarse. Si seleccionó un solo pedido de ventas, se deben reasignar las líneas del mismo pedido de ventas. Esta situación puede darse cuando una de las líneas se facturó previamente y luego se agregó una nueva línea o se eliminó o canceló una línea existente. Si se eliminó una línea, no aparecerá en la cuadrícula. Por lo tanto, no se puede seleccionar. Sin embargo, aún se tendrá en cuenta cuando se ejecute el proceso de reasignación.

Una vez que haya terminado de seleccionar las líneas de pedido de ventas necesarias, utilice los botones del Panel de acciones tal como se describe aquí:

- **Actualizar reasignación**: calcula los nuevos importes de precios de ingresos para las líneas de pedido de ventas seleccionadas. Si se eliminó o canceló una línea, la reasignación se realizará solo para las líneas existentes que seleccionó. En la siguiente ilustración se muestra un ejemplo de líneas de pedido de ventas antes de actualizarse la reasignación.

    [![Líneas de pedido de ventas antes de que se actualice la reasignación.](./media/03_RevRecScenarios.png)](./media/03_RevRecScenarios.png)

    Los nuevos importes de precios de ingresos se muestran en la columna **Importe reasignado** de la cuadrícula **Líneas**. En este punto, la reasignación se ha procesado pero aún no se ha calculado. En la siguiente ilustración se muestra un ejemplo de líneas de pedido de ventas después de actualizarse la reasignación.

    [![Líneas de pedido de ventas después de que se actualice la reasignación.](./media/04_RevRecScenarios.png)](./media/04_RevRecScenarios.png)

- **Procesar**: procesa o registra los precios de ingresos reasignados. Después de seleccionar este botón, no hay forma de revertir la reasignación. Si no seleccionó **Actualizar reasignación** antes de seleccionar **Procesar**, la reasignación se ejecuta automáticamente.

    - Si no se ha facturado ninguna línea de pedido de ventas, los importes de los precios de ingresos se actualizan en los pedidos de ventas que se seleccionaron para la reasignación.
    - Si se ha facturado una o más líneas de pedido de ventas, se registran los asientos contables de corrección y se corrigen los detalles del programa de ingresos que se crearon para la línea de pedido de ventas facturada.

- **Asiento esperado**: muestra una vista previa de los asientos contables que se han creado para cualquier línea de pedido de ventas que se haya facturado. Si no se han facturado líneas, no se muestra nada. Si no seleccionó **Actualizar reasignación** antes de seleccionar **Asiento esperado**, la reasignación se ejecuta automáticamente.
- **Reasignación de ingresos**: abre una página que muestra la asignación de precios de ingresos para todas las líneas seleccionadas. No puede cambiar la información de la página. Muestra los importes de línea que se utilizaron para realizar la reasignación.

    [![Importes de línea que se utilizaron para la reasignación.](./media/05_RevRecScenarios.png)](./media/05_RevRecScenarios.png)

- **Restablecer datos para el cliente seleccionado**: si el proceso de reasignación se inició pero no se completó, borra los datos de la tabla de reasignación solo para el cliente seleccionado. Suponga, por ejemplo, que marca varias líneas de pedido de ventas para reasignarlas, deja la página abierta sin seleccionar **Procesar** y se agota el tiempo de espera de la página. En este caso, las líneas de pedido de ventas permanecerán marcadas y no estarán disponibles para que otro usuario complete el proceso de reasignación. La página puede incluso estar en blanco cuando se abre. En este caso, se puede utilizar el botón **Restablecer datos para el cliente seleccionado** para borrar los pedidos de ventas no procesados de modo que otro usuario pueda completar el proceso de reasignación.

## <a name="undo-a-reallocation"></a>Deshacer una reasignación

Una reasignación se deshace ejecutando otra reasignación. La reasignación se vuelve a realizar y el usuario selecciona diferentes líneas de pedidos de venta para incluirlas en el segundo proceso de reasignación.

Si se ha realizado una reasignación en dos o más pedidos de venta independientes, se puede deshacer seleccionando **Reasignar precio con nuevas líneas de pedido** de cualquier pedido de ventas incluido en la reasignación. No puede ir a **Reconocimiento de ingresos \> Tareas periódicas \> Reasignar precio con nuevas líneas de pedido** para deshacer la reasignación, porque la página que se abre de esta manera muestra solo los pedidos de venta que no tienen id. de reasignación. El id. de reasignación se asigna después de que se haya reasignado el documento.

En la página **Reasignar precio con nuevas líneas de pedido**, desmarque los pedidos de ventas que deban excluirse del acuerdo contractual. Utilice los botones adecuados en el panel de acciones, como **Actualizar reasignación** y **Procesar**, para procesar la reasignación. Si todos los pedidos de ventas, excepto el pedido de ventas activo, no están marcados, el id. de reasignación se eliminará cuando se procese el cambio.

Si se ha realizado una reasignación agregando una nueva línea a un pedido de ventas total o parcialmente facturado, la reasignación solo se puede deshacer eliminando esa línea del pedido de ventas y volviendo a ejecutar la reasignación luego. La línea de pedido de ventas debe eliminarse porque se supone que todas las líneas de un pedido de ventas forman parte del mismo contrato. No puede desmarcar una línea de pedido de ventas mientras se encuentra en la página **Reasignar precio con nuevas líneas de pedido**.

## <a name="reallocate-multiple-times"></a>Reasignar varias veces

Se pueden realizar varias reasignaciones con el mismo pedido de ventas si se han realizado varios cambios en el contrato. Cada reasignación desencadena la asignación de un id. de reasignación al pedido de ventas o grupo de pedidos de venta, para agrupar los cambios. Si se realizan varias reasignaciones, cada reasignación adicional utiliza el mismo id. de reasignación que la primera reasignación.

Por ejemplo, se introduce el pedido de ventas 00045 y tiene varias líneas. Una vez que el pedido de ventas se ha facturado por completo, se le agrega una nueva línea de pedido de venta. A continuación, la reasignación se ejecuta abriendo la página **Reasignar precio con nuevas líneas de pedido** ya sea desde el pedido de ventas 00045 o yendo a **Reconocimiento de ingresos \> Tareas periódicas \> Reasignar precio con nuevas líneas de pedido**. El id. de reasignación **Reall000001** se asigna al pedido de ventas.

Se crea un segundo pedido de ventas, 00052, para el mismo contrato. La reasignación se puede ejecutar de nuevo abriendo la página **Reasignar precio con nuevas líneas de pedido** del pedido de venta 00045, pero no del pedido de ventas 00052. Si abre la página **Reasignar precio con nuevas líneas de pedido** del pedido de ventas, 00052, el pedido de ventas 00045 no se mostrará porque se le ha asignado un id. de reasignación. La página solo muestra los pedidos de ventas que no tienen id. de reasignación.

Hay dos formas de realizar la segunda reasignación. Puede deshacer la reasignación del pedido de ventas 00045. En este caso, se elimina el id. de reasignación y, a continuación, puede realizar la reasignación desde el pedido de ventas 00045 o desde el pedido de ventas 00052. Como alternativa, puede abrir la página **Reasignar precio con nuevas líneas de pedido** del pedido de ventas 00045 y agregar el segundo pedido de ventas. Cuando se procese la reasignación, se asignará el id. de reasignación **Reall000001** tanto al pedido de ventas 00045 como al pedido de ventas 00052.

## <a name="scenarios-for-reallocation"></a>Escenarios de reasignación

En los siguientes temas se tratan varios escenarios de reconocimiento de ingresos:

- [Reasignación de reconocimiento de ingresos: escenario 1](rev-rec-reallocation-scenario-1.md): se introducen dos pedidos de ventas, pero solo se confirman. El mismo escenario producirá resultados similares si más de dos pedidos de ventas se encuentran en estado confirmado.
- [Reasignación de reconocimiento de ingresos: escenario 2](rev-rec-reallocation-scenario-2.md): se introducen dos pedidos de ventas y luego el cliente agrega un artículo al contrato después de facturar el primer pedido de ventas.
- [Reasignación de reconocimiento de ingresos: escenario 3](rev-rec-reallocation-scenario-3.md): se agrega una nueva línea a un pedido de ventas existente ya facturado.
- [Reasignación de reconocimiento de ingresos: escenario 4](rev-rec-reallocation-scenario-4.md): se elimina una línea de un pedido de ventas existente parcialmente facturado.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
