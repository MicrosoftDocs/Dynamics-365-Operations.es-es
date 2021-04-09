---
title: Reconocer ingresos diferidos
description: En este tema se proporciona información acerca de cómo reconocer ingresos mediante la característica de reconocimiento de ingresos.
author: kweekley
ms.date: 08/24/2018
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: Customer
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 8.0.4
ms.openlocfilehash: 8d9b5e1248497ec74e1c7125b2395c0ed4c825c2
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5820530"
---
# <a name="recognize-deferred-revenue"></a>Reconocer ingresos diferidos

[!include [banner](../includes/banner.md)]

> [!NOTE]
> La característica Reconocimiento de ingresos no se puede activar a través de Administración de características. Actualmente, debe utilizar las claves de configuración para activarla.

En este tema se describe el proceso para reconocer ingresos en la programación de reconocimiento de ingresos. Después de que la factura se haya registrado para un pedido de ventas, se crea una programación de reconocimiento de ingresos para cada línea de pedido de ventas que tiene una programación de ingresos. La programación de ingresos en una línea se usa para determinar si los ingresos de la línea se deben diferir.

## <a name="view-revenue-recognition-schedule-details"></a>Ver detalles de la programación de reconocimiento de ingresos

Hay dos maneras de tener acceso a los detalles de la programación de reconocimiento de ingresos.

- Puede abrir la programación de aprobación de ingresos directamente a partir de un pedido de ventas facturado. En este caso, la información en la programación de ingresos se filtra para mostrar solo los detalles del pedido de ventas seleccionado. Este método resulta útil al validar los detalles de la programación para un pedido de ventas.
- Puede abrir la programación de reconocimiento de ingresos desde la página **Reconocimiento de ingresos \> Tareas periódicas**. Este método se usa a menudo cuando los ingresos se reconocen al final de un período. Cuando se abre la página por primera vez, no se muestra ninguna información. Use los filtros sobre la cuadrícula para definir los criterios de los detalles de la programación que se deben mostrar. Puede filtrar según las fechas de factura introduciendo un intervalo de fechas, un pedido de ventas, un cliente, un id. de proyecto o un estado.

[![Ilustración de la página Programaciones de ingresos](./media/revenue-recognition-schedule-page.png)](./media/revenue-recognition-schedule-page.png)

La ficha desplegable **Dimensión financiera** situada debajo de la cuadrícula muestra las dimensiones financieras de la línea del pedido de ventas. Estas dimensiones se consideraron durante el registro en los ingresos diferidos. También se consideran cuando se reconocen los ingresos. Los valores de dimensión que se utilizan dependen de la estructura contable que se asigna a las cuentas principales de ingresos y de ingresos diferidos.

## <a name="recognize-revenue"></a>Reconocer ingresos

Para reconocer ingresos, ejecute el proceso **Crear diario** en la página **Reconocimiento de ingresos**. Puede abrir esta página desde el pedido de ventas o **Tareas periódicas**. Si el proceso se ejecuta desde el pedido de ventas, este reconoce los ingresos únicamente para el pedido de ventas seleccionado. Normalmente, en su lugar el proceso se ejecuta desde **Tareas periódicas** para que reconozca ingresos de todas las facturas de pedidos de ventas registradas.

Para definir los criterios para seleccionar y registrar los ingresos, seleccione **Crear diario** para abrir el cuadro de diálogo **Crear diario**.

[![Opciones de parámetros de Crear diario](./media/revenue-recognition-create-journal.png)](./media/revenue-recognition-create-journal.png)

En el cuadro de diálogo, utilice las opciones del grupo de campos **Fecha de procesamiento** para definir la fecha de registro que se utilizará cuando se reconozcan los ingresos. Si selecciona **Fecha seleccionada**, puede especificar una fecha de registro en el campo **Fecha de transacción**. Si selecciona **Fecha de programación de ingresos**, no se utiliza la fecha de la transacción. En su lugar, se utiliza el valor del campo **Fecha de reconocimiento** de cada línea de la programación como fecha de registro.

A continuación, en el campo **Fecha inicial**, especifique la fecha “inicial” para reconocer ingresos. Se reconocerán todas las líneas de la programación en las que la fecha de reconocimiento sea igual o anterior a la fecha “inicial”, siempre que no estén en espera.

Una vez que haya terminado de definir las fechas, seleccione **Aceptar** en el cuadro de diálogo para crear el diario. Recibirá un mensaje informativo en el que se muestra el número de transacciones que se han creado y el diario en el que se habían creado. El diario no se registra automáticamente. Por tanto, el administrador de reconocimiento de ingresos tiene tiempo para validar qué líneas de la programación se están reconociendo.

Una vez que se ejecute el proceso, las líneas de la programación que se han transferido al diario se marcan como **Procesado**. El indicador **Procesado** indica que las líneas se han transferido al diario, pero se pueden registrar o no registrar. Una vez registrado el diario de reconocimiento de ingresos, el indicador **Procesado** se mantiene. Si se elimina el diario de reconocimiento de ingresos, o si se elimina una línea, se quita el indicador **Procesado**. De esa manera, la línea se podrá reconocer cuando el proceso **Crear diario** se ejecute de nuevo.

[![Página de programaciones de reconocimiento de ingresos](./media/revenue-recognition-rev-recog-schedule-02.png)](./media/revenue-recognition-rev-recog-schedule-02.png)

En la página **Diario de reconocimiento de ingresos** (**Reconocimiento de ingresos \> Entradas del diario \> Diario de reconocimiento de ingresos**), abra **Líneas** para ver los detalles de lo que se está reconociendo. Se creará siempre una transacción independiente para cada línea de la programación que se está reconociendo, incluso si todas las líneas se registran en la misma fecha mediante el uso de las mismas cuentas contables.

[![Página Asiento del diario](./media/revenue-recognition-journal-voucher.png)](./media/revenue-recognition-journal-voucher.png)

La columna **Cuenta** muestra la cuenta contable de ingresos diferidos. Esta cuenta contable no se puede editar. Esta restricción ayuda a garantizar que se libera la cuenta contable correcta de ingresos diferidos. Esta cuenta contable no se valida con la estructura contable, porque es posible que haya cambiado desde que se produjo por última vez el registro en la cuenta contable de los ingresos diferidos.

La columna **Cuenta de contrapartida** muestra la cuenta contable de ingresos. De forma predeterminada, la cuenta contable de ingresos se obtiene de perfiles de contabilización de inventario y las dimensiones financieras se obtienen de la línea de pedido de ventas. Esta cuenta contable se valida con la estructura contable actual. Sin embargo, puede editarse si la estructura contable ha cambiado y requiere dimensiones financieras adicionales.

El importe predeterminado procede de la línea correspondiente de la programación y no se puede modificar.

De forma predeterminada, si el pedido de ventas es un pedido de ventas de varias divisas, el tipo de cambio se establece en el tipo de cambio de la factura. Este comportamiento ayuda a garantizar que los importes de la divisa de contabilidad y de la divisa de notificación se liberen completamente. Debido al redondeo, el tipo de cambio de la última línea de la programación podría ser ligeramente diferente del tipo de la factura.

Una vez se ha registrado el diario de reconocimiento de ingresos, el asiento se especifica en la programación. Si hay más de un asiento para la misma línea de la programación, aparece un asterisco (\*) en la línea. Para ver los asientos que se han registrado para esa línea, seleccione **Transacciones de asiento**.

## <a name="modify-the-revenue-recognition-schedule-details"></a>Modificar los detalles de la programación de reconocimiento de ingresos

La mayoría de los datos de los detalles de la programación de ingresos no se puede editar. No se pueden agregar nuevas líneas y las líneas existentes no se pueden eliminar. Los detalles de la programación de ingresos para cada línea de pedido de ventas se deben mantener para ayudar a garantizar que, con el paso del tiempo, una organización reconoce el mismo importe que se ha diferido.

### <a name="edit-schedule-lines"></a>Editar líneas de programación

Se permiten algunas ediciones en las líneas de la programación. Los siguientes campos se pueden cambiar en las líneas:

- **En espera**: este indicador se puede establecer o quitar antes de que se procese la línea. Para borrar el indicador, seleccione la fila y, a continuación, seleccione **Eliminar retención**. Los ingresos no se pueden reconocer en las líneas que están en espera. Las líneas se pueden colocar automáticamente en espera si la programación de ingresos se configura para retenciones automáticas.

    [![Programaciones de ingresos: editar líneas de la programación](./media/revenue-recognition-rev-revenue-schedules.png)](./media/revenue-recognition-rev-revenue-schedules.png)

- **Fecha de reconocimiento**: la fecha de reconocimiento se puede cambiar antes que se procese la línea. Cuando se ejecuta el proceso que crea el diario para reconocer ingresos, se especifica una fecha en el campo **Reconocimiento de ingresos a partir de la fecha**. Esa fecha se compara con la fecha en el campo **Fecha de reconocimiento** para determinar qué líneas se deben reconocer.
- **Importe para liberar**: el importe que se liberará se puede modificar antes de que se procese la línea. Puede reducir el importe de los ingresos que se va a reconocer, pero no puede aumentarlo. Este campo permite a una organización reconocer parte de los ingresos en la fecha de reconocimiento. Si se cambia el importe, el importe del campo **Importe restante** muestra cuántos ingresos se deben seguir reconociendo.
- **Cantidad que se va a liberar**: si la programación de los ingresos se configura para una repetición o un mes, el campo **Cantidad que se va a liberar** muestra la cantidad para la línea de pedido de ventas. Este campo también se puede editar y proporciona otro modo de reconocer parte de los ingresos. Por ejemplo, si la cantidad de la línea es 5, puede anular la cantidad para que sea inferior a 5. El importe en el campo **Importe que se va a liberar** se actualiza proporcionalmente.

### <a name="update-contract-terms"></a>Actualizar condiciones del contrato

Los detalles de la programación de ingresos se crean según la programación de ingresos que se asigna a la línea de pedido de ventas cuando se registra la factura. Si la programación de ingresos en la línea de pedido de ventas es incorrecta, no se puede modificar en el pedido de ventas tras facturar el pedido de ventas. En su lugar, debe usar el botón **Actualizar condiciones del contrato** para cambiar la programación de ingresos. La programación de ingresos se puede cambiar antes o después de que se hayan reconocido ingresos.

Para cambiar la programación, seleccione cualquier línea de programación para el artículo que esté cambiando. En la siguiente ilustración está seleccionada la línea para el artículo S0008 que se ha registrado mediante una programación de ingresos de doce meses. Cuando se selecciona **Actualizar condiciones del contrato**, un cuadro de diálogo muestra las fechas iniciales y finales del contrato y la programación de ingresos.

[![Fechas iniciales y finales del contrato](./media/revenue-recognition-rev-revenue-schedule-update-cntrct-dates-schedule.png)](./media/revenue-recognition-rev-revenue-schedule-update-cntrct-dates-schedule.png)

Cambie las fechas iniciales y finales del contrato para que reflejen el intervalo de fechas correcto. Cuando cambia el intervalo de fechas, el valor del campo **Número de repeticiones** debe coincidir con una programación de ingresos que se ha definido en el sistema. En este ejemplo, puesto que el contrato se cambió a un contrato de 24 meses, se debe configurar una programación de ingresos de 24 meses. Puesto que existe la programación de ingresos de 24 meses, se especifica de forma predeterminada y el contrato se puede modificar. Si no existe una programación de ingresos con un número coincidente de repeticiones, no se podrá modificar el contrato. Una vez que haya terminado de actualizar las condiciones del contrato y la programación de ingresos como sea necesario, seleccione **Aceptar** en el cuadro de diálogo para guardar los cambios.

[![Intervalo de fechas del contrato actualizado](./media/revenue-recognition-rev-revenue-schedule-update-cntrct-dates-schedule-02.png)](./media/revenue-recognition-rev-revenue-schedule-update-cntrct-dates-schedule-02.png)

Los cambios del contrato tienen los efectos siguientes en los detalles de la programación de ingresos:

- Si no se ha reconocido ningún ingreso para el producto, todos los detalles anteriores de la programación se eliminan y se reemplazan con los nuevos detalles de la programación de ingresos. Por ejemplo, el artículo S0008 tenía originalmente 12 líneas en los detalles de la programación. Esas 12 líneas se eliminan y se reemplazan por 24 líneas, en función de la nueva programación de ingresos.
- Si se han reconocido los ingresos para el producto, algunos ingresos se han reconocido incorrectamente porque el reconocimiento se basaba en la programación incorrecta de ingresos. Esas líneas se deben invertir y reconocer de nuevo, en función de la nueva programación. En esta situación, se crean nuevas líneas de la programación de ingresos con importes negativos en la fecha de reconocimiento original. A continuación, se crean las nuevas líneas para reconocer los importes basados en la nueva programación de ingresos. Por ejemplo, el 8 de agosto de 2019, se reconocen los ingresos para $10.53. El 8 de septiembre de 2019, se reconocen los ingresos para $13.16. Por lo tanto, se crean dos nuevas líneas en las mismas fechas. Una línea es para -$10.53 y la otra línea es para -$13.16. A continuación, se crean veinticuatro nuevas líneas y los ingresos diferidos totales de $160.61 se asignan entre ellas. Para registrar las líneas de inversión, ejecute el proceso **Crear diario**.

[![Programación de reconocimiento de ingresos](./media/revenue-recognition-rev-recog-schedule-03.png)](./media/revenue-recognition-rev-recog-schedule-03.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]