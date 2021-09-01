---
title: Gestionar las deducciones utilizando el banco de trabajo de deducciones
description: Este tema describe cómo usar el área de trabajo de deducciones para procesar pagos de cliente que incluyan deducciones.
author: sherry-zheng
ms.date: 08/02/2021
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 04d7c1de85978f7915246fd835a0866cefb6de310bba240ebcadc57089e10521
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6735120"
---
# <a name="manage-deductions-using-the-deduction-workbench"></a>Gestionar las deducciones utilizando el banco de trabajo de deducciones

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]

Este tema describe cómo usar el área de trabajo de deducciones para procesar pagos de cliente que incluyan deducciones.

Un cliente al que se debe una devolución puede decidir no esperar al desembolso de la devolución. En su lugar, el cliente puede enviar un pago que incluya una deducción para el importe de devolución. Para gestionar este tipo de transacción, puede usar el área de trabajo de deducción para conciliar las deducciones para abrir transacciones de crédito, dividir deducciones, denegar deducciones y cancelar deducciones.

> [!NOTE]
> El área de trabajo de deducción ha sido parte de la funcionalidad de ventas y marketing de Microsoft Dynamics 365 Supply Chain Management por mucho tiempo. Sin embargo, ahora se ha mejorado para que también funcione con la versión más nueva del módulo **Gestión de reembolsos**. Este tema describe cómo utilizar las funciones anteriores y las funciones de administración de devoluciones del área de trabajo de deducción. Sin embargo, si no [activó e mídulo **Gestión de devoluciones** para su sistema](rebate-management-enable.md), algunas de las funciones que se describen aquí no estarán disponibles para usted.

## <a name="prerequisites"></a>Requisitos previos

### <a name="set-up-the-old-deduction-management-system"></a>Configurar el antiguo sistema de gestión de deducciones

Puede utilizar el área de trabajo de deducción junto con las antiguas capacidades de gestión de deducción de Supply Chain Management, incluso si no está utilizando el módulo **Gestión de devoluciones**. Sin embargo, primero debe preparar su sistema como se describe en esta sección.

Antes de poder utilizar el área de trabajo de deducciones, debe completar las tareas de configuración que se describen en [Configurar gestión de deducciones](/dynamicsax-2012/appuser-itpro/set-up-deduction-management). También debe tener algún tipo de acuerdo de devolución configurado para el cliente: una devolución de cliente, tal como se describe en [Configurar y mantener devoluciones de clientes](/dynamicsax-2012/appuser-itpro/setting-up-and-maintaining-customer-rebates), o una devolución de concesión de comercialización.

Si está solicitando una deducción para un reembolso de cliente, debe completar estas tareas:

- [Configure sus devoluciones para clientes](/dynamicsax-2012/appuser-itpro/setting-up-and-maintaining-customer-rebates).
- Apruebe y procese la devolución para que pueda utilizar el área de trabajo de deducción.

Si está solicitando una deducción para una devolución de concesión de comercialización, debe completar estas tareas:

- Configurar devoluciones de facturación por uso.
- Solicitar devoluciones de facturación por uso.

### <a name="configure-accounts-receivable-and-deductions"></a><a name="accounts-receivable-deductions"></a>Configurar clientes y deducciones

El sistema registra todos los eventos de deducción en un diario de reclamaciones. Por lo tanto, su sistema debe incluir un diario que se pueda utilizar para este propósito. Si aún no tiene un diario de reclamaciones, configúrelo ahora. Este diario es necesario para crear deducciones directamente en el banco de trabajo de deducción, la liquidación del cliente o la página del cliente.

Para configurar un nuevo diario de reclamaciones para deducciones, siga estos pasos.

1. Vaya a **Contabilidad general \> Configuración de diario \> Nombres de diarios**.
1. Seleccione **Nuevo** y establezca los siguientes campos para el nuevo nombre del diario:

    - **Nombre** – Especifique un nombre único para el diario de reclamaciones.
    - **Descripción** – Proporcione una descripción del nuevo diario.
    - **Tipo de diario** – Seleccione *Diario*.
    - **Serie de cupones** - Asigne una secuencia numérica existente. Alternativamente, cree una nueva secuencia numérica que tenga un alcance de empresa y asígnela al nuevo nombre del diario.

1. Vaya a **Clientes \> Configuración \> Parámetros de clientes**.
1. En la pestaña **Deducciones**, en la ficha desplegable **General**, establezca el campo **Nombre de diario de reclamaciones** con el nombre del diario que acaba de crear.
1. En la ficha desplegable **Pedido de devolución**, configure los siguientes campos:

    - **Crear pedido de devolución** - Configure esta opción para especificar qué debe hacer el sistema cuando se aprueba una declaración basada en la cantidad:

        - *Sí* – Crear un pedido de devolución.
        - *No* - Crear un pedido de ventas negativo.

    - **Creación sin factura adjunta** - Seleccione un valor para especificar qué debe hacer el sistema cuando se aprueba una reclamación basada en la cantidad pero no se adjunta ninguna factura:

        - *Aceptar* – Crea un pedido de devolución.
        - *Advertencia* - Crea un pedido de devolución, pero muestra el siguiente mensaje de advertencia: "La reclamación no está adjunta a una factura".
        - *Error* - No crea un pedido de devolución, pero muestra el siguiente mensaje de advertencia: "La reclamación no está adjunta a una factura". Se ha cancelado la actualización".

    - **Cree un pedido de devolución antes de la aprobación de la deducción** - Establezca esta opción en *Sí* si se pueden crear órdenes de devolución antes de que se apruebe la reclamación. Esta configuración se aplica solo a las reclamaciones basadas en la cantidad donde la opción **Crear pedido de devolución** está configurada en *Sí*.

### <a name="configure-general-ledger-parameters"></a>Configurar parámetros de contabilidad general

Cuando el sistema crea un diario de reclamaciones para una nueva deducción, también crea dos nuevas transacciones de cliente: una para compensar el importe de la reclamación con la factura original y otra para registrar la deuda de un cliente por el importe de la reclamación (porque la reclamación aún no ha sido aprobada). Por lo tanto, debe configurar su sistema para que un solo comprobante pueda tener varias líneas de clientes.

Para permitir que un solo comprobante tenga varias líneas de clientes, siga estos pasos.

1. Vaya a **Contabilidad general \> Configuración de contabilidad \> Parámetros de Contabilidad general**.
1. En la ficha **Libro mayor**, en la ficha desplegable **General**, establezca la opción l **Permitir múltiples transacciones dentro de un cupón** como *Sí*.
1. Si recibe un mensaje de advertencia, seleccione **Cerrar** para aceptar el cambio.

### <a name="create-deduction-reasons"></a><a name="deduction-reasons"></a>Crear motivos de deducción

El sistema requiere que los usuarios especifiquen un motivo para cada deducción que ingresan directamente en el banco de trabajo de deducción, la liquidación del cliente o la página del cliente. El motivo determina cómo se maneja la deducción cuando se aprueba.

1. Vaya a **Ventas y marketing \> Derechos comerciales \> Deducciones \> Razones de deducción**.
1. Seleccione **Nuevo** para agregar una fila a la cuadrícula y establezca los campos siguientes:

    - **Motivo de reclamación** – Especifique un nombre único para el motivo.
    - **Descripción** - Introduzca una descripción del motivo para proporcionar más información sobre cómo debe usarse.
    - **Base de reclamación** - Seleccione una base de reclamación por el motivo de la reclamación:

        - *Basado en precio* - Cree un crédito de texto gratuito una vez aprobado.
        - *Basado en cantidad* - Cree una orden de venta negativa o una orden de devolución tras la aprobación.

    - **Código de motivo de devolución** - Seleccione un código de motivo de devolución para aplicar como **Código de motivo de devolución** para la orden de devolución.
    - **Tipo** - Seleccione un tipo de deducción. El valor **Compensación de deducción** para el tipo seleccionado se utilizará para configurar el campo **Compensación de deducción** cuando se crea una deducción o reclamación. Los tipos de deducción se definen en la página **Tipos de deducción** (**Ventas y marketing \> Derechos comerciales \> Deducciones \> Tipos de deducción**).
    - **Cuenta de registro de reclamaciones** - Este campo está disponible solo cuando el campo **Base de reclamación** está configurado en *Basado en precio*. Cuando se aprueba una reclamación basada en el precio, el sistema asigna la cuenta contable que seleccione aquí como **Cuenta principal** para el borrador de nota de crédito de texto libre.

### <a name="set-up-the-settle-approved-deductions-periodic-task"></a>Configurar la tarea periódica liquidar deducciones aprobadas

Para las deducciones que se crean utilizando el comando **Nueva deducción** en el banco de trabajo de deducción, la liquidación del cliente o la página del cliente, puede configurar la tarea periódica *Liquidar deducciones aprobadas* para hacer coincidir automáticamente las deducciones y los créditos que coinciden con los valores e importes de **ID de deducción**.

Para programar esta tarea, vaya a **Ventas y Marketing\> Tareas periódicas\> Liquidar deducciones aprobadas** y configure opciones, filtros y una programación, al igual que para otros tipos de tareas periódicas.

> [!NOTE]
> Si **Liquidación automática** está configurada en *Sí* en la ficha **Liquidación** de la página **Parámetros de clientes** (**Cliente \> Configuración \> Parámetros de cliente**), la tarea periódica *Liquidar deducciones aprobadas* no hará nada, porque el crédito se liquidará automáticamente.

## <a name="create-a-deduction"></a>Crear una deducción

### <a name="create-a-deduction-journal-entry-by-using-the-customer-payment-journal"></a>Cree un movimiento de diario de deducción utilizando el diario de pagos del cliente

Para crear un movimiento de diario de deducción, siga estos pasos.

1. Vaya a **Clientes \> Pagos \> Diario de pagos de clientes**.
1. Seleccione **Nuevo** para agregar una fila a la cuadrícula.
1. En el campo **Nombre** para la nueva fila, seleccione el nombre del diario.
1. En el panel de acciones, seleccione **Líneas**.
1. Especifique la fecha, la cuenta de empresa y el número de cuenta de cliente.
1. En el campo **Factura**, seleccione la factura a la que la deducción está asociada.
1. En el campo **Crédito**, especifique el importe que pagó el cliente.
1. Seleccione **Aceptar** para confirmar que el importe es inferior al total de la transacción marcada.
1. Seleccione el tipo de cuenta de contrapartida y la cuenta de contrapartida.
1. En la barra de herramientas sobre la cuadrícula, seleccione **Deducciones**.
1. En la página **Deducción**, en el panel de acciones, seleccione **Nueva** para agregar una fila a la cuadrícula. El campo **ID de deducción** para la nueva fila se establece automáticamente.
1. En el campo **Tipo**, seleccione el tipo de deducción.
1. En el campo **Importe**, introduzca el importe que se muestra en el campo **Saldo** debajo de la lista de deducciones. Este importe representa el importe que el cliente dedujo del pago.
1. Cierre la página **Deducción**. Volvió a la página **Pagos de clientes**, que ahora muestra una nueva línea para la deducción.
1. En el panel de acciones, seleccione **Validar \> Validar**. Debe recibir el siguiente mensaje: "El diario es correcto”.
1. En el panel de acciones, seleccione **Registrar**.

### <a name="create-a-deduction-by-using-the-deduction-workbench"></a>Crear una deducción utilizando el banco de trabajo de deducciones

Para procesar una deducción nueva en el área de trabajo de deducción, siga estos pasos.

1. Vaya a **Ventas y marketing \> Derechos comerciales \> Deducciones\> Área de trabajo de deducción**.
1. En el panel de acciones, seleccione **Mantener \> Nueva deducción**.

    En el cuadro de diálogo **Nueva deducción**, el campo **ID de deducción** se establece según la secuencia numérica de **ID de deducción** que se define en la página **Parámetros de gestión de derechos comerciales** (**Ventas y marketing \> Configuración \> Derechos comerciales \> Parámetros de gestión de derechos comerciales**).

1. Establezca los campos siguientes:

    - **Cuenta de cliente** - Seleccione la cuenta de cliente a la que se aplica la deducción.
    - **Número de reclamación externa** - Introduzca la referencia de reclamación del cliente.
    - **Importe de reclamación** - Introduzca el importe de la reclamación con impuestos incluidos. El valor debe ser positivo.
    - **Divisa** - Seleccione la moneda para la deducción. El valor predeterminado es la moneda que se establece para la cuenta de cliente seleccionada.
    - **Base de reclamación** - Seleccione la base de la reclamación. La base de la reclamación determina el tipo de transacción de crédito que se crea después de que se aprueba la deducción o reclamación.

        - *Basado en precio* - Se creará un borrador de factura de servicios.
        - *Basado en cantidad* - Se creará una orden de venta negativa o una orden de devolución negativa.

    - **Fecha de reclamación** - Seleccione la fecha de la reclamación. La fecha actual es el valor predeterminado.
    - **Razón de la reclamación** - Seleccione el código de motivo que se aplica a la deducción actual. La base de reclamación que seleccionó afecta las opciones que se aplican. Para obtener más información sobre cómo crear y configurar los motivos de reclamación que están disponibles para su selección aquí, consulte la sección [Crear motivos de deducción](#deduction-reasons) anterior en este tema.
    - **Notas** - Agregue las notas que correspondan. Cuando se aprueba la reclamación, el aprobador podrá editar o agregar a las notas de la reclamación.
    - **Crear diario de reclamaciones** - Configure esta opción para especificar si el diario de reclamaciones debe crearse cuando se crea la reclamación o la deducción:

        - *Sí* - El sistema creará y publicará un diario general utilizando el diario de reclamaciones que se configura en la página **Parámetros de cliente**. (Para obtener más información, consulte la sección [ Configurar cliente y deducciones](#accounts-receivable-deductions) anterior en este tema.) Cuando se adjunta una factura a la reclamación, el diario de reclamaciones se utiliza para reducir el saldo de la factura correspondiente. Si la reclamación se rechaza posteriormente, el diario de reclamaciones y las liquidaciones (si se adjuntó una factura) se revertirán.
        - *No* - No se crea ningún diario de reclamaciones en este momento. Se creará cuando se apruebe la reclamación. Aún se puede adjuntar una factura a la nueva reclamación, aunque no se cree un diario de reclamaciones. Sin embargo, la liquidación no se puede realizar sin el diario de reclamaciones.

1. Seleccione **Aceptar**.

    Se crea una deducción nueva. Si configura la opción **Crear diario de reclamaciones** como *Sí*, se contabilizan las siguientes transacciones:

    - **Dos transacciones de nuevos clientes** - Una transacción compensa el importe de la reclamación con la factura original. La otra transacción registra la deuda de un cliente por el importe de la reclamación, porque la reclamación aún no ha sido aprobada. La transacción de la factura original y la transacción de reclamación de compensación se marcarán automáticamente para liquidación cuando adjunte la factura seleccionando **Mantener\> Adjuntar factura** en el Panel de acciones.
    - **Dos transacciones de compensación** - Estas transacciones se contabilizan en la cuenta contable de **Compensación de deducción**.
    - **Diario de reclamaciones** - Para ver el diario de reclamaciones para cada deducción que se muestra en el banco de trabajo de deducción, seleccione la ficha **Referencias**. El diario de reclamaciones se muestra en el campo **Número de lote de diario**. También puede ver el diario de reclamaciones en la ficha **Eventos de deducción**. Allí, tendrá un valor de **Tipo de actualización** de *Coincidencia*.

### <a name="create-a-deduction-from-a-customer-settlement"></a>Crear una deducción de la liquidación de un cliente

El proceso de creación de una deducción de la liquidación de un cliente se asemeja al proceso de creación de una deducción a través del banco de trabajo de deducción. Sin embargo, el cliente y la moneda de la factura se establecen automáticamente y se adjunta la factura. No tiene que seleccionar **Mantener \> Adjuntar factura** en el Panel de acciones cuando crea una reclamación o una deducción a través de la página de liquidación del cliente.

1. Vaya a **Clientes \> Clientes \> Todos los clientes**.
1. Seleccione el cliente para el que desea crear una deducción.
1. En el panel de acciones, en la ficha **Cobrar**, en el grupo **Liquidar**, seleccione **Liquidar transacciones**.
1. En el cuadro de diálogo **Configuración de transacciones**, en la ficha **Visión general**, seleccione la factura para crear la deducción.
1. En la barra de herramientas, seleccione **Deducciones \> Nueva deducción**.

    En el cuadro de diálogo **Nueva deducción**, el campo **ID de deducción** se establece según la secuencia numérica de **ID de deducción** que se define en la página **Parámetros de gestión de derechos comerciales** (**Ventas y marketing \> Configuración \> Derechos comerciales \> Parámetros de gestión de derechos comerciales**). El campo **Cuenta de cliente** se establece con la cuenta de cliente a la que se aplica la deducción.

1. Establezca los campos siguientes:

    - **Número de reclamación externa** - Introduzca la referencia de reclamación del cliente.
    - **Importe de reclamación** - Introduzca el importe de la reclamación con impuestos incluidos. El valor debe ser positivo.
    - **Divisa** - Seleccione la moneda para la deducción. El valor predeterminado es la moneda que se establece para la cuenta de cliente seleccionada.
    - **Base de reclamación** - Seleccione la base de la reclamación. La base de la reclamación determina el tipo de transacción de crédito que se crea después de que se aprueba la deducción o reclamación.

        - *Basado en precio* - Se creará un borrador de factura de servicios.
        - *Basado en cantidad* - Se creará una orden de venta negativa o una orden de devolución negativa.

    - **Fecha de reclamación** - Seleccione la fecha de la reclamación. La fecha actual es el valor predeterminado.
    - **Razón de la reclamación** - Seleccione el código de motivo que se aplica a la deducción actual. La base de reclamación que seleccionó afecta las opciones que se aplican. Para obtener más información sobre cómo crear y configurar los motivos de reclamación que están disponibles para su selección aquí, consulte la sección [Crear motivos de deducción](#deduction-reasons) anterior en este tema.
    - **Notas** - Agregue las notas que correspondan. Cuando se aprueba la reclamación, el aprobador podrá editar o agregar a las notas de la reclamación.
    - **Crear diario de reclamaciones** - Configure esta opción para especificar si el diario de reclamaciones debe crearse cuando se crea la reclamación o la deducción:

        - *Sí* - El sistema creará y publicará un diario general utilizando el diario de reclamaciones que se configura en la página **Parámetros de cliente**. (Para obtener más información, consulte la sección [ Configurar cliente y deducciones](#accounts-receivable-deductions) anterior en este tema.) Cuando se adjunta una factura a la reclamación, el diario de reclamaciones se utiliza para reducir el saldo de la factura correspondiente. Si la reclamación se rechaza posteriormente, el diario de reclamaciones y las liquidaciones (si se adjuntó una factura) se revertirán.
        - *No* - No se crea ningún diario de reclamaciones en este momento. Se creará cuando se apruebe la reclamación. Aún se puede adjuntar una factura a la nueva reclamación, aunque no se cree un diario de reclamaciones. Sin embargo, la liquidación no se puede realizar sin el diario de reclamaciones.

1. Seleccione **Aceptar**.

    Se crea una deducción nueva. Si configura la opción **Crear diario de reclamaciones** como *Sí*, se contabilizan las siguientes transacciones:

    - **Dos transacciones de nuevos clientes** - Una transacción compensa el importe de la reclamación con la factura original. La otra transacción registra la deuda de un cliente por el importe de la reclamación, porque la reclamación aún no ha sido aprobada. La transacción de la factura original y la transacción de reclamación de compensación se marcarán automáticamente para liquidación cuando adjunte la factura seleccionando **Mantener\> Adjuntar factura** en el Panel de acciones.
    - **Dos transacciones de compensación** - Estas transacciones se contabilizan en la cuenta contable de **Compensación de deducción**.
    - **Diario de reclamaciones** - Para ver el diario de reclamaciones para cada deducción que se muestra en el banco de trabajo de deducción, seleccione la ficha **Referencias**. El diario de reclamaciones se muestra en el campo **Número de lote de diario**. También puede ver el diario de reclamaciones en la ficha **Eventos de deducción**. Allí, tendrá un valor de **Tipo de actualización** de *Coincidencia*.

    Volvió a la página **Liquidar transacciones**, que ahora muestra la factura seleccionada como marcada. El botón **Contabilizar** está disponible solo si configura la opción **Crear diario de reclamaciones** como *Sí*. Si está disponible, seleccione **Contabilizar** para reducir el saldo en la factura por el valor de **Importe de reclamación**.

### <a name="create-a-deduction-from-a-customer-page"></a>Crear una deducción desde la página de un cliente

El proceso de creación de una deducción de la liquidación desde la página de un cliente se asemeja al proceso de creación de una deducción a través del banco de trabajo de deducción. Sin embargo, el cliente se configura automáticamente.

1. Vaya a **Clientes \> Clientes \> Todos los clientes**.
1. Seleccione el cliente para el que desea crear una deducción.
1. En el Panel de acciones, en la ficha **Cobro**, en el grupo **Deducciones**, seleccione **Crear deducciones**.

    En el cuadro de diálogo **Nueva deducción**, el campo **ID de deducción** se establece según la secuencia numérica de **ID de deducción** que se define en la página **Parámetros de gestión de derechos comerciales** (**Ventas y marketing \> Configuración \> Derechos comerciales \> Parámetros de gestión de derechos comerciales**). El campo **Cuenta de cliente** se establece con la cuenta de cliente a la que se aplica la deducción.

1. Establezca los campos siguientes:

    - **Número de reclamación externa** - Introduzca la referencia de reclamación del cliente.
    - **Importe de reclamación** - Introduzca el importe de la reclamación con impuestos incluidos. El valor debe ser positivo.
    - **Divisa** - Seleccione la moneda para la deducción. El valor predeterminado es la moneda que se establece para la cuenta de cliente seleccionada.
    - **Base de reclamación** - Seleccione la base de la reclamación. La base de la reclamación determina el tipo de transacción de crédito que se crea después de que se aprueba la deducción o reclamación.

        - *Basado en precio* - Se creará un borrador de factura de servicios.
        - *Basado en cantidad* - Se creará una orden de venta negativa o una orden de devolución negativa.

    - **Fecha de reclamación** - Seleccione la fecha de la reclamación. La fecha actual es el valor predeterminado.
    - **Razón de la reclamación** - Seleccione el código de motivo que se aplica a la deducción actual. La base de reclamación que seleccionó afecta las opciones que se aplican. Para obtener más información sobre cómo crear y configurar los motivos de reclamación que están disponibles para su selección aquí, consulte la sección [Crear motivos de deducción](#deduction-reasons) anterior en este tema.
    - **Notas** - Agregue las notas que correspondan. Cuando se aprueba la reclamación, el aprobador podrá editar o agregar a las notas de la reclamación.
    - **Crear diario de reclamaciones** - Configure esta opción para especificar si el diario de reclamaciones debe crearse cuando se crea la reclamación o la deducción:

        - *Sí* - El sistema creará y publicará un diario general utilizando el diario de reclamaciones que se configura en la página **Parámetros de cliente**. (Para obtener más información, consulte la sección [ Configurar cliente y deducciones](#accounts-receivable-deductions) anterior en este tema.) Cuando se adjunta una factura a la reclamación, el diario de reclamaciones se utiliza para reducir el saldo de la factura correspondiente. Si la reclamación se rechaza posteriormente, el diario de reclamaciones y las liquidaciones (si se adjuntó una factura) se revertirán.
        - *No* - No se crea ningún diario de reclamaciones en este momento. Se creará cuando se apruebe la reclamación. Aún se puede adjuntar una factura a la nueva reclamación, aunque no se cree un diario de reclamaciones. Sin embargo, la liquidación no se puede realizar sin el diario de reclamaciones.

1. Seleccione **Aceptar**.

    Se crea una deducción nueva. Si configura la opción **Crear diario de reclamaciones** como *Sí*, se contabilizan las siguientes transacciones:

    - **Dos transacciones de nuevos clientes** - Una transacción compensa el importe de la reclamación con la factura original. La otra transacción registra la deuda de un cliente por el importe de la reclamación, porque la reclamación aún no ha sido aprobada. La transacción de la factura original y la transacción de reclamación de compensación se marcarán automáticamente para liquidación cuando adjunte la factura seleccionando **Mantener\> Adjuntar factura** en el Panel de acciones.
    - **Dos transacciones de compensación** - Estas transacciones se contabilizan en la cuenta contable de **Compensación de deducción**.
    - **Diario de reclamaciones** - Para ver el diario de reclamaciones para cada deducción que se muestra en el banco de trabajo de deducción, seleccione la ficha **Referencias**. El diario de reclamaciones se muestra en el campo **Número de lote de diario**. También puede ver el diario de reclamaciones en la ficha **Eventos de deducción**. Allí, tendrá un valor de **Tipo de actualización** de *Coincidencia*.

## <a name="create-a-credit-note-for-a-customer"></a>Crear una nota de abono para un cliente

Si una devolución aprobada existe para un cliente, puede crear una nota de abono en la cuenta de cliente para representar la devolución. A continuación, el crédito aparece en el área de trabajo de la deducción, donde se puede asignar a una deducción.

Para crear una nota de abono, siga los siguientes pasos.

1. Vaya a **Ventas y marketing \> Clientes \> Todos los clientes**.
1. Seleccione el cliente.
1. En el panel de acciones, en la ficha **Cobrar**, en el grupo **Liquidar**, seleccione **Liquidar transacciones**.
1. En el cuadro de diálogo **Liquidar transacciones**, seleccione la transacción a la que se aplicó la devolución.
1. En la barra de herramientas, en el menú **Funciones**, seleccione el tipo de programa de devolución que corresponda.
1. En la página **Devolución**, en la ficha **Visión general**, seleccione la casilla **Marcar** junto al ID de devolución correspondiente.
1. En el panel de acciones, seleccione **Funciones\> Crear nota de crédito**.

## <a name="process-a-deduction-on-the-deduction-workbench"></a>Procesar una deducción en el área de trabajo de deducción

En el área de trabajo de deducción, puede conciliar deducciones con transacciones de crédito abiertas, así como dividir, denegar y cancelar deducciones.

En función de cómo desea que se procese la deducción, complete uno o más de los siguientes procedimientos en la siguientes subsecciones: Puede combinar los procedimientos como sea necesario. Por ejemplo, puede dividir una deducción en dos partes y, a continuación hacer coincidir una parte con un crédito pero dejar la parte restante en el área de trabajo para que coincida con otro crédito más adelante. También puede hacer coincidir una deducción con un crédito que sea menor que el importe de deducción, y después denegar o cancelar el saldo restante de la deducción.

### <a name="match-a-deduction-to-a-credit"></a>Hacer coincidir una deducción con un crédito

Para hacer coincidir una deducción con un crédito, siga estos pasos.

1. Vaya a **Ventas y marketing \> Derechos comerciales \> Deducciones\> Área de trabajo de deducción**.
1. Active la casilla **Marcar** de la deducción que se procesará.
1. En la sección **Transacciones abiertas**, seleccione la casilla **Marcar** para que el crédito coincida con la deducción. Si se muestran varios créditos, puede seleccionar más de un crédito para asociarlo a la deducción. Si desea que el sistema seleccione automáticamente créditos que coincidan con el importe de la deducción, en la barra de herramientas, seleccione una opción adecuada en el menú **Seleccionar importe de deducción**.
1. En el panel de acciones, seleccione **Mantener  \>Asignar**. El sistema hace coincidir la deducción con el crédito. Si queda un saldo en la deducción, se muestra en el campo **Importe restante** en la ficha **Deducciones**.

    > [!NOTE]
    > Para las deducciones que se crearon utilizando el comando **Nueva deducción** en el banco de trabajo de deducción, la liquidación del cliente o la página del cliente, el comando **Mantener \>Coincidencia** está disponible solo si el campo **Estado de la reclamación** está configurado en *Aceptado*. Este comando se puede utilizar para hacer coincidir manualmente la transacción basada en el precio o en la cantidad con el crédito asociado en la sección **Transacciones abiertas**. Este crédito se crea cuando se aprueba la deducción (utilizando el comando **Mantener\> Aprobar la deducción**), o cuando se adjunta a un crédito existente como se describe en la sección [Créditos creados fuera del proceso de aprobación de deducción](#credits-outside-approval) más adelante en este tema. La tarea periódica *Liquidar deducciones aprobadas* (**Ventas y Marketing \> Tareas periódicas \> Liquidar deducciones aprobadas**) también se puede utilizar para hacer coincidir automáticamente las deducciones y los créditos que tienen valores y cantidades de **ID de deducción** coincidentes.

### <a name="split-a-deduction"></a>Dividir una deducción

Para dividir una deducción, siga estos pasos.

1. Vaya a **Ventas y marketing \> Derechos comerciales \> Deducciones\> Área de trabajo de deducción**.
1. Active la casilla **Marcar** de la deducción que se procesará.
1. En el panel de acciones, seleccione **Mantener  \>Dividir**.
1. En el cuadro de diálogo **Dividir**, en el campo **Dividir importe**, introduzca la cantidad a dividir de la deducción principal. A continuación seleccione **Aceptar**.
1. En la ficha **Deducciones**, observe que aparece un registro nuevo para el importe dividido. El registro original de deducción contiene el resto de saldos de deducción. Ahora puede gestionar las dos partes de la devolución original de manera independiente.
1. Seleccione el registro de deducción original y luego seleccione la ficha **Referencias**. El campo **Dividir importe** muestra la cantidad que se separó de la cantidad original.

### <a name="attach-an-invoice-to-a-deduction"></a>Adjuntar una factura a una deducción

Puede adjuntar una factura a una deducción si la deducción se creó utilizando el comando **Nueva deducción** en el banco de trabajo de deducción, la liquidación del cliente o la página del cliente, y si actualmente no hay ninguna factura adjunta (es decir, la columna **Factura** está en blanco).

Para adjuntar una factura a una deducción, siga estos pasos.

1. Vaya a **Ventas y marketing \> Derechos comerciales \> Deducciones\> Área de trabajo de deducción**.
1. Active la casilla **Marcar** de la deducción que se procesará.
1. En el panel de acciones, seleccione **Mantener \> Adjuntar factura**.
1. En el cuadro de diálogo **Adjuntar factura**, seleccione una factura y luego seleccione **OK**.
1. En el cuadro de diálogo **Liquidar transacciones**, siga uno de estos pasos, dependiendo de si se registró un diario de reclamaciones cuando se creó la deducción:

    - Si se registró un diario de reclamaciones, la factura que seleccionó y la transacción de crédito del cliente del diario de reclamaciones muestran una marca de verificación en la columna **Marcar**. Seleccione **Registrar**. El saldo restante de la factura adjunta se reduce por el importe de la reclamación.
    - Si no se registró un diario de reclamaciones, ninguna transacción muestra una marca de verificación en la columna **Marcar**. Debido a que no puede compensar con un diario de reclamaciones hasta que se apruebe la deducción, seleccione **Cancelar**.

### <a name="detach-an-invoice-from-a-deduction"></a>Separar una factura de una deducción

Puede separar una factura de una deducción si la deducción se creó utilizando el comando **Nueva deducción** en el banco de trabajo de deducción, la liquidación del cliente o la página del cliente, y si actualmente hay unafactura adjunta (es decir, la columna **Factura** muestra un número de factura) y el campo **Estado de reclamación** está establecido en *Abierto*. Puede completar esta tarea porque se adjuntó una factura incorrecta. La factura se elimina de la deducción y su saldo restante se actualiza si se redujo cuando se adjuntó la factura.

Para separar una propuesta de factura, siga estos pasos.

1. Vaya a **Ventas y marketing \> Derechos comerciales \> Deducciones\> Área de trabajo de deducción**.
1. Active la casilla **Marcar** de la deducción que se procesará.
1. En el panel de acciones, seleccione **Mantener \> Separar factura**.

### <a name="approve-a-deduction"></a>Aprobar una deducción

Puede aprobar las deducciones que se crearon mediante el comando **Nueva deducción** en el banco de trabajo de deducción, la liquidación del cliente o la página del cliente. Sin embargo, solo puede aprobar las deducciones cuando el campo **Estado de la reclamación** está configurado como *Abierto*.

Para aprobar una deducción, siga estos pasos.

1. Vaya a **Ventas y marketing \> Derechos comerciales \> Deducciones\> Área de trabajo de deducción**.
1. Active la casilla **Marcar** de la deducción que se procesará.
1. En el panel de acciones, seleccione **Mantener \> Aprobar deducción**.
1. En el cuadro de diálogo **Aprobar deducción**, edite o agregue información en el valor **Nota** según sea necesario.
1. Si la deducción se basa en el precio y no se le ha adjuntado una factura, seleccione un grupo de impuestos sobre las ventas de artículos. Normalmente, el grupo de artículos de impuestos se establece en la factura. Por lo tanto, el código de artículo de impuestos debe especificarse cuando no está adjunto a una factura.
1. Seleccione **Aceptar**.

    En este punto, no se pueden realizar más cambios a la deducción. Si la opción **Crear diario de reclamaciones** se configuró en *No* cuando se creó la deducción, el diario de reclamaciones se crea y se contabiliza cuando se aprueba la deducción. Una vez aprobada la deducción, el crédito se crea y abre automáticamente. El tipo depende del valor **Base de reclamación** de la deducción:

    - *Basado en precio* - Si la deducción se basa en el precio, se crea una factura de servicios para la cuenta del cliente. Puede agregar una descripción y contabilizar el crédito. Los siguientes campos se completan con la deducción cuando se crea el borrador:

        - **ID de deducción** - Este campo se agrega al encabezado para permitir la trazabilidad hasta la deducción.
        - **Cuenta principal** - El valor está determinado por el valor de **Cuenta de contabilización de reclamaciones** que se establece por el motivo de la deducción que se asigna a la deducción.
        - **Grupo de impuestos sobre las ventas de artículos** - El valor está determinado por la factura adjunta o por el valor que seleccionó cuando aprobó la deducción.
        - **Precio unitario** - El valor es el crédito del importe de la reclamación de la deducción.
        - **Texto de la factura** - De forma predeterminada, este campo se establece con el valor de **Notas** de la deducción.

    - *Basado en cantidad* - Si la deducción se basa en la cantidad, se crea un pedido de cliente abierto o un pedido de devolución. El valor de **Crear orden de devolución** de la página **[Parámetros de cliente](#accounts-receivable-deductions)** determina si se crea una orden de venta o una orden de devolución cuando se aprueba la deducción. Se muestra la página **Copiar pedidos** y se filtra para mostrar las filas donde el campo **Cuenta de facturas** se establece en la cuenta de cliente de la deducción. Siga estos pasos:

        1. En la ficha desplegable **Facturas**, la sección **Encabezados** muestra facturas de venta donde el valor de **Cuenta de facturas** coincide con la cuenta de cliente de la deducción. Seleccione una factura de venta aplicable.
        1. La sección **Líneas** muestra las líneas de la factura de venta seleccionada. Seleccione la casilla **Seleccionar** para cada línea que desea copiar. Alternativamente, en la sección **Encabezados**, seleccione la casilla **Seleccionar todo** de la orden de venta para seleccionar todas sus líneas.
        1. Ajuste el valor de **Cantidad** para una o más líneas según sea necesario.

            Todas las líneas que ha seleccionado hasta ahora se enumeran en la ficha desplegable **Líneas seleccionadas o encabezado para copiar**.

        1. Repita los dos pasos anteriores según sea necesario hasta que todas las líneas requeridas se enumeren en la ficha desplegable **Líneas seleccionadas o encabezado para copiar**.
        1. Seleccione **Aceptar**.

            Se abre la nueva orden de devolución y se configuran automáticamente los siguientes campos:

            - **ID de deducción** - Este campo se agrega al encabezado para permitir la trazabilidad hasta la deducción.
            - **Código de motivo de devolución** - De forma predeterminada, este campo se establece en el valor de **Código de motivo de devolución** que se establece para el motivo de la deducción que se asigna a la deducción.

Una vez facturado el crédito, aparece en la sección **Transacciones abiertas** del banco de trabajo de deducción contra el correspondiente valor de **ID de deducción** y su campo de **Tipo de reclamación** se establece en *Otros creditos*. El crédito estará disponible hasta que se liquide con la deducción de una de las siguientes formas:

- Lo liquida manualmente seleccionando **Mantener\> Coincidencia** en el Panel de acciones.
- Se liquida automáticamente mediante la tarea periódica *Liquidar reclamaciones aprobadas* (**Ventas y marketing\> Tareas periódicas\> Liquidar reclamaciones aprobadas**).
- Se liquida automáticamente porque la opción **Liquidación automática** de la ficha **Liquidación** de la página **Parámetros de cliente** está configurada como *Sí*.

Para ver el crédito que se crea cuando se aprueba la deducción, también puede usar el botón **Crédito abierto** de la sección **Transacciones abiertas** del banco de trabajo de deducción.

### <a name="create-a-return-order"></a>Crear un pedido de devolución

Puede crear una orden de devolución para deducciones que se crearon mediante el comando **Nueva deducción** en el banco de trabajo de deducción, la liquidación del cliente o la página del cliente. Sin embargo, se deben cumplir todas las condiciones siguientes:

- El campo **Base de reclamación** está configurado en *Basado en cantidad*.
- El campo **Estado de reclamación** está configurado en *Abierto*.
- La opción **Crear orden de devolución** de la ficha **Deducciones** de la página **[ Parámetros de cliente](#accounts-receivable-deductions)** está configurada como *Sí*.
- La opción **Crear orden de devolución antes de la aprobación de la deducción** de la ficha **Deducciones** de la página **[ Parámetros de cliente](#accounts-receivable-deductions)** está configurada como *Sí*.

Para crear una orden de devolución, siga estos pasos.

1. Vaya a **Ventas y marketing \> Derechos comerciales \> Deducciones\> Área de trabajo de deducción**.
1. Active la casilla **Marcar** de la deducción que se procesará.
1. En el panel de acciones, seleccione **Mantener \> Crear orden de devolución**.
1. En el cuadro de diálogo **Aprobar deducción**, edite o agregue información en el valor existente de **Notas** según sea necesario y seleccione **Aceptar**.
1. En el cuadro de diálogo **Copiar órdenes**, en la ficha desplegable **Facturas**, la sección **Encabezados** muestra facturas de venta donde el valor de **Cuenta de facturas** coincide con la cuenta de cliente de la deducción. Seleccione una factura de venta aplicable.
1. La sección **Líneas** muestra las líneas de la factura de venta seleccionada. Seleccione la casilla **Seleccionar** para cada línea que desea copiar. Alternativamente, en la sección **Encabezados**, seleccione la casilla **Seleccionar todo** de la orden de venta para seleccionar todas sus líneas.
1. Ajuste el valor de **Cantidad** para una o más líneas según sea necesario.

    Todas las líneas que ha seleccionado hasta ahora se enumeran en la ficha desplegable **Líneas seleccionadas o encabezado para copiar**.

1. Repita los dos pasos anteriores según sea necesario hasta que todas las líneas requeridas se enumeren en la ficha desplegable **Líneas seleccionadas o encabezado para copiar**.
1. Seleccione **Aceptar**.

    Se abre la nueva orden de devolución y se configuran automáticamente los siguientes campos:

    - **ID de deducción** - Este campo se agrega al encabezado para permitir la trazabilidad hasta la deducción.
    - **Código de motivo de devolución** - De forma predeterminada, este campo se establece en el valor de **Código de motivo de devolución** que se establece para el motivo de la deducción que se asigna a la deducción.

### <a name="deny-a-deduction"></a>Denegar una deducción

Para denegar una deducción, siga estos pasos.

1. Vaya a **Ventas y marketing \> Derechos comerciales \> Deducciones\> Área de trabajo de deducción**.
1. Active la casilla **Marcar** de la deducción que se procesará.
1. En el panel de acciones, seleccione **Mantener  \>Denegar**.
1. En el cuadro de diálogo **Denegar**, seleccione el código de motivo de la denegación y luego seleccione **OK**.
1. En el campo **Mostrar** debajo del Panel de acciones, seleccione *Cerrado*.

    La ficha **Deducciones** muestra la deducción denegada y el campo **Importe restante** se establece en *0,00*.

    Para deducciones que se crearon mediante el comando **Nueva deducción** en el banco de trabajo de deducción, la liquidación del cliente o la página del cliente, se producen los siguientes eventos:

    - En la ficha **Referencias**, los campos de la sección **Denegación** se actualizan.
    - Si seleccionó crear el diario de reclamaciones cuando se creó la deducción, y si se adjuntó una factura a la deducción que redujo el saldo de la factura, la factura se separa y el saldo restante de la factura adjunta anteriormente se incrementa por el importe de la reclamación rechazada.
    - El campo **Estado** de la deducción se establece en *Cerrado*.
    - El campo **Estado de reclamación** de la deducción se establece en *Rechazado*.

Para revertir una denegación, siga estos pasos.

1. En la ficha **Deducciones**, seleccione una deducción denegada.
1. En el panel de acciones, seleccione **Revertir denegación**.

    Para deducciones que se crearon mediante el comando **Nueva deducción** en el banco de trabajo de deducción, la liquidación del cliente o la página del cliente, se producen los siguientes eventos:

    - En la ficha **Referencias**, los campos de la sección **Denegación** se actualizan.
    - El campo **Estado** de la deducción se establece en *Abierto*.
    - El campo **Estado de reclamación** de la deducción se establece en *Abierto*.

### <a name="write-off-a-deduction"></a>Cancelar una deducción

Para cancelar una deducción, siga estos pasos.

1. Vaya a **Ventas y marketing \> Derechos comerciales \> Deducciones\> Área de trabajo de deducción**.
1. Active la casilla **Marcar** de la deducción que se procesará.
1. En el panel de acciones, seleccione **Mantener  \>Cancelar**.
1. En el cuadro de diálogo **Cancelar**, seleccione el código de motivo de la cancelación y luego seleccione **OK**.
1. En el campo **Mostrar**, seleccione *Cerrado*.

    La ficha **Deducciones** muestra la deducción cancelada y el campo **Importe restante** se establece en *0,00*.

    Para deducciones que se crearon mediante el comando **Nueva deducción** en el banco de trabajo de deducción, la liquidación del cliente o la página del cliente, se producen los siguientes eventos:

    - En la ficha **Referencias**, los campos de la sección **Cancelar** se actualizan.
    - Si creó el diario de reclamaciones cuando se creó la deducción, se contabiliza un diario de reclamaciones en el código de motivo de cancelación de la deducción. Puede ver esta entrada en la ficha **Eventos de deducción**, donde tiene un valor de **Tipo de actualización** de *Cancelar*.
    - El campo **Estado** de la deducción se establece en *Cerrado*
    - El campo **Estado de reclamación** de la deducción se establece en *Cancelado*.

Para revertir una cancelación, siga estos pasos.

1. En la ficha **Deducciones**, seleccione una deducción denegada.
1. En el panel de acciones, seleccione **Revertir cancelación**.

    Para deducciones que se crearon mediante el comando **Nueva deducción** en el banco de trabajo de deducción, la liquidación del cliente o la página del cliente, se producen los siguientes eventos:

    - En la ficha **Referencias**, los campos de la sección **Cancelar** se actualizan.
    - Si creó el diario de reclamaciones cuando se creó la deducción, se contabiliza un diario de reclamaciones en el código de motivo de cancelación de la deducción. Puede ver esta entrada en la ficha **Eventos de deducción**, donde tiene un valor de **Tipo de actualización** de *Revertir cancelación*.
    - El campo **Estado** de la deducción se establece en *Abierto*.
    - El campo **Estado de reclamación** de la deducción se establece en *Abierto*.

## <a name="credits-created-outside-the-approve-deduction-process"></a><a name="credits-outside-approval"></a>Créditos creados fuera del proceso de aprobar deducción

Esta sección solo se aplica a deducciones que se crearon mediante el comando **Nueva deducción** en el banco de trabajo de deducción, la liquidación del cliente o la página del cliente.

Es posible que diferentes usuarios ya hayan creado una factura de servicios, una orden de devolución o una orden de venta negativa para la reclamación de un cliente fuera del proceso **Aprobar la deducción**. Cuando se aprueba la deducción existente en el banco de trabajo de deducción, el sistema crea automáticamente otra factura de servicios, orden de devolución u orden de venta negativa. Esta sección describe cómo adjuntar los créditos existentes a una deducción antes de que se apruebe la deducción, para ayudar a evitar la duplicación de créditos.

### <a name="attach-a-credit-to-deduction"></a>Adjuntar un crédito a una deducción

Esta sección describe cómo puede adjuntar un crédito a una deducción del crédito.

Después de adjuntar un crédito a la deducción, puede verlo con el botón **Crédito abierto** de la barra de herramientas, en la sección **Transacciones abiertas** del banco de trabajo de deducción.

Una vez facturado el crédito y aprobada la deducción, el crédito aparece en la sección **Transacciones abiertas** del banco de trabajo de deducción contra el correspondiente valor de **ID de deducción** y su campo de **Tipo de reclamación** se establece en *Otros creditos*.

#### <a name="attach-a-free-text-invoice-to-a-deduction"></a>Adjuntar una factura de servicios a una deducción

Para adjuntar una factura de servicios a una deducción, siga estos pasos.

1. Vaya a **Clientes \> Facturas \> Todas las facturas de servicios**.
1. Seleccione la factura aplicable.
1. En el panel de acciones, en la pestaña **Factura**, seleccione **Adjuntar crédito a deducción**. Este botón solo está disponible si el campo **ID de deducción** de la factura de servicios está en blanco. Un campo en blanco indica que la factura de servicios no está ya adjunta a una deducción.
1. En la página **Adjuntar crédito a deducción**, puede seleccionar *una* deducción. Solo se pueden seleccionar deducciones abiertas *basadas en precio*.
1. Seleccione **Aceptar**. El campo **ID de deducción** se establece en el encabezado de la factura de servicios.

#### <a name="attach-a-return-order-to-a-deduction"></a>Adjuntar una orden de devolución a una deducción

Para adjuntar una orden de devolución a una deducción, siga estos pasos.

1. Vaya a **Clientes \> Pedidos \> Todos los pedidos de devolución**.
1. Seleccione el número correspondiente de autorización de devolución de mercancía (RMA) recibida o abierta.
1. En el panel de acciones, en la pestaña **Orden de devolución**, seleccione **Adjuntar crédito a deducción**. Este botón solo está disponible si el campo **ID de deducción** de la orden de devolución está en blanco. Un campo en blanco indica que la orden de devolución no está ya adjunta a una deducción.
1. En la página **Adjuntar crédito a deducción**, puede seleccionar *una* deducción. Solo se pueden seleccionar deducciones abiertas *basadas en cantidad*.
1. Seleccione **Aceptar**. El campo **ID de deducción** se establece en el encabezado de la orden de devolución.

#### <a name="attach-a-sales-order-to-a-deduction"></a>Adjuntar un pedido de ventas a una deducción

Para adjuntar un pedido de ventas a una deducción, siga estos pasos.

1. Vaya a **Clientes \> Pedidos \> Todos los pedidos de venta**.
1. Seleccione el pedido de ventas abierto, entregado o facturado correspondiente.
1. En el panel de acciones, en la pestaña **Factura**, seleccione **Adjuntar crédito a deducción**. Este botón solo está disponible si el campo **ID de deducción** del pedido de ventas está en blanco. Un campo en blanco indica que el pedido de ventas no está ya adjunto a una deducción.
1. En la página **Adjuntar deducción**, puede seleccionar *una* deducción. Solo se pueden seleccionar deducciones abiertas *basadas en cantidad*.
1. Seleccione **Aceptar**. El campo **ID de deducción** se establece en el encabezado del pedido de ventas.

#### <a name="detach-a-deduction-from-a-credit"></a>Separar una deducción de un crédito

Si se ha adjuntado la deducción incorrecta, puede desvincularla del crédito. Sin embargo, se deben cumplir todas las condiciones siguientes:

- Se adjunta un crédito a la deducción.
- El campo **Estado de reclamación** está configurado en *Abierto*.

Para separar una deducción de un crédito, siga uno de estos pasos, según el tipo de crédito:

- **Facturas de servicios:** en la página **Todas las facturas de servicios**, seleccione una factura. Luego, en el panel de acciones, en la ficha **Factura**, seleccione **Separar crédito de deducción**.
- **Órdenes de devolución:** en la página **Todas las órdenes de devolución**, seleccione una orden. Luego, en el panel de acciones, en la ficha **Orden de devolución**, seleccione **Separar crédito de deducción**.
- **Pedidos de ventas:** en la página **Todos los pedidos de ventas**, seleccione una orden. Luego, en el panel de acciones, en la ficha **Factura**, seleccione **Separar crédito de deducción**.

### <a name="attach-a-deduction-to-a-credit"></a>Adjuntar una deducción a un crédito

Esta sección describe cómo puede adjuntar una deducción a un crédito desde la deducción.

#### <a name="attach-a-deduction-to-a-free-text-return-order-or-sales-order-credit"></a>Adjunte una deducción a un crédito de texto sin formato, orden de devolución o pedido de venta

Para adjuntar una deducción a un crédito de texto sin formato, orden de devolución o pedido de venta, siga estos pasos.

1. Vaya a **Ventas y marketing \> Derechos comerciales \> Deducciones\> Área de trabajo de deducción**.
1. Seleccione la deducción abierta aplicable.
1. En el panel de acciones, seleccione **Mantener \> Adjuntar deducción a crédito**. Este botón está disponible solo si el campo **Estado de la reclamación** está configurado en *Abierto*.
1. En la página **Adjuntar crédito**, puede seleccionar *un* crédito. El tipo de créditos que se muestra depende del valor de **Base de reclamación** de la deducción:

    - *Basado en precio* - La página muestra facturas de servicio para la cuenta del cliente donde el campo **ID de deducción** está en blanco. Las solicitudes de clientes también se muestran porque es posible que la factura de servicios no esté contabilizada. Por lo tanto, es posible que no tenga un número al que se pueda hacer referencia.
    - *Basado en cantidad* - El tipo de créditos que se muestra depende de la configuración de la opción **Crear orden de devolución** de la página **[ Parámetros de cliente](#accounts-receivable-deductions)**:

        - *Sí* - La página muestra órdenes de devoluciones para la cuenta del cliente donde el campo **ID de deducción** está en blanco.
        - *No* - La página muestra pedidos de venta para la cuenta del cliente donde el campo **ID de deducción** está en blanco.

1. Seleccione **Aceptar**. El campo **ID de deducción** se establece en el encabezado del crédito.

Después de adjuntar un crédito a la deducción, puede verlo con el botón **Crédito abierto** de la barra de herramientas, en la sección **Transacciones abiertas** del banco de trabajo de deducción.

Una vez facturado el crédito y aprobada la deducción, el crédito aparece en la sección **Transacciones abiertas** del banco de trabajo de deducción contra el correspondiente valor de **ID de deducción** y su campo de **Tipo de reclamación** se establece en *Otros creditos*.

#### <a name="detach-a-credit-from-the-deduction"></a>Separar un crédito de la deducción

Si se ha adjuntado el crédito incorrecto, puede desvincularlo de la deducción. En el panel de acciones, en el grupo **Mantener**, seleccione **Separar deducción de crédito**. El valor de **ID de deducción** se elimina del crédito.

El botón **Separar deducción del crédito** solo está disponible si se cumplen las siguientes condiciones:

- Se adjunta un crédito a la deducción.
- El campo **Estado de reclamación** está configurado en *Abierto*.

## <a name="create-a-one-time-promotion"></a>Crear una promoción única

En ocasiones, es posible que no tenga una devolución aprobada que pueda asignar a una deducción. En este caso, puede usar la característica *promoción única* para que la deducción coincida con una concesión de comercialización que esté asociada al cliente. La característica de *promoción única* crea un nuevo acuerdo de concesión de comercialización y un evento de comercialización de la suma total. A continuación, la característica hace coincidir la suma total con la deducción y realiza los registros necesarios para cerrar la deducción.

Esta función resulta útil si usa concesiones de comercialización. Para obtener más información sobre las asignaciones comerciales, consulte [Gestión de concesiones comerciales](../sales-marketing/trade-allowance.md).

En primer lugar, debe configurar una plantilla que se pueda usar para crear el nuevo acuerdo de concesión de comercialización. Para configurar una plantilla, siga estos pasos.

1. Vaya a **Ventas y marketing\> Derechos comerciales\> Plantillas**.
1. En el panel de acciones, haga clic en **Nueva**.
1. En los campos, introduzca la información que debe aparecer en los acuerdos que se crean de la plantilla.
1. En la ficha desplegable **Clientes**, en el campo **Jerarquía**, seleccione un nivel de jerarquía.
1. En la lista de jerarquía, seleccione el cliente que tiene una deducción sin asignar y luego seleccione el botón de flecha hacia la derecha (**\>**). El cliente se agrega a la lista **Clientes de acuerdos de concesión comercial**.
1. Configure los campos restantes como necesite y luego cierre la página.
1. Vaya a **Ventas y marketing\> Configuración\> Asignación comercial\> Parámetros de gestión de derechos comerciales**.
1. En la ficha **Visión general**, en el campo **Plantilla de promoción única**, seleccione el nombre de la plantilla que se utilizará para crear promociones únicas.

A continuación, puede crear una promoción única en el área de trabajo de deducción. Para crear una promoción única, siga estaos pasos.

1. Vaya a **Ventas y marketing \> Derechos comerciales \> Deducciones\> Área de trabajo de deducción**.
1. Active la casilla **Marcar** de la deducción que se procesará.
1. En el panel de acciones, seleccione **Mantener \> Liquidar la deducción como una promoción única**.
1. En el cuadro de diálogo **Promoción única**, siga estos pasos para asociar la deducción con uno o más fondos:

    1. Seleccione **Nuevo** y, a continuación, en el campo **ID de fondo**, seleccione un ID de fondo. Repita este paso para agregar tantos fondos como sea necesario.
    1. En el campo **Porcentaje** situado junto a cada ID de fondo, especifique el porcentaje de la deducción para asignar el fondo. Los importes que especifica en los campos de **Porcentaje** deben ascender en total al 100 %.

1. Seleccione **Aceptar**. El sistema crea un nuevo acuerdo de concesión de comercialización con un evento de marketing de la suma total que hace coincidir la suma total con la deducción.

## <a name="do-a-mass-update-of-deductions"></a>Realice una actualización masiva de deducciones

Si tiene que realizar el mismo cambio a varias deducciones, puede seleccionar esas deducciones y realizar una actualización masiva de los campos.

Para realizar una actualización masiva, siga estos pasos.

1. Vaya a **Ventas y marketing \> Derechos comerciales \> Deducciones\> Área de trabajo de deducción**.
1. En el campo **Mostrar** debajo del Panel de acciones, seleccione el tipo de deducciones que desea visualizar.
1. Active la casilla situada junto a cada deducción que desee actualizar. En el panel de acciones, seleccione **Mantener \>Actualización masiva**.
1. El cuadro de diálogo **Actualización masiva** muestra las deducciones seleccionadas. Actualice los campos según sus necesidades y luego seleccione **OK** para aceptar los cambios.
