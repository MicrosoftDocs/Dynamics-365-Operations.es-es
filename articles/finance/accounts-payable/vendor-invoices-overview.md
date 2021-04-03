---
title: Visión general de facturas de proveedores
description: Este tema ofrece información general relativa a facturas de proveedor.
author: abruer
manager: AnnBe
ms.date: 12/18/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendorInvoiceWorkspace, VendInvoiceInfoListPage
audience: Application User
ms.reviewer: roschlom
ms.custom: 13971
ms.assetid: 0ec4dbc0-2eeb-423b-8592-4b5d37e559d3
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1799fb18a1dd4b7c532259ab198e1ba30a89c09d
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5264140"
---
# <a name="vendor-invoices-overview"></a>Visión general de facturas de proveedores

[!include [banner](../includes/banner.md)]

Este tema ofrece información general relativa a facturas de proveedor. Las facturas de proveedor son solicitudes de pago recibido para productos y servicios. Las facturas de proveedor pueden representar una cuenta para servicios continuos o se pueden basar en pedidos de compra para artículos y servicios específicos.

## <a name="vendor-invoices"></a>Facturas de proveedores

Una factura de proveedor de un pedido de compra es una factura que se produce cuando se reciben productos o servicios de acuerdo con un pedido de compra que se ha configurado con un proveedor. La factura de proveedor contiene un encabezado y una o varias líneas para artículos o servicios. Una factura de proveedor finaliza el ciclo de pedido de compra con la recepción de producto en la factura de proveedor.

Aunque algunas facturas de proveedor están relacionadas con un pedido de compra, las facturas de proveedor también pueden contener las líneas que no se corresponden con las líneas de pedido de compra. También puede crear facturas de proveedor que no estén asociadas a ningún pedido de compra. Estas facturas de proveedor pueden representar servicios continuos, como una factura de servicios públicos. No tiene que hacer referencia a un pedido de compra cuando agregue un servicio continuo.

Hay varias formas de especificar una factura de proveedor:

- El registro de facturas de proveedor le permite especificar rápidamente las facturas que no hacen referencia a un pedido de compra, de modo que puede acumular el gasto. Mediante el diario de aprobación de facturas de proveedor, puede seleccionar dichas facturas y registrarlas al saldo del proveedor para invertir la acumulación.
- El diario de facturas de proveedor le permite especificar rápidamente las facturas que no hacen referencia a un pedido de compra, en un único paso.
- Junto con el grupo de facturas de proveedor, el registro de facturas de proveedor le permite especificar rápidamente facturas para acumular el gasto. Puede abrir los pedidos de compra asociados más tarde para registrar la factura en la cuenta de gastos.
- Las páginas **Facturas de proveedor abiertas** y **Facturas de proveedor pendientes** le permiten crear facturas de proveedor a partir de pedidos de compra confirmados.

La discusión siguiente proporciona más información sobre cómo se usan las páginas **Facturas de proveedor abiertas** o **Facturas de proveedor pendientes** para crear una factura de proveedor a partir de un pedido de compra.

## <a name="understanding-invoice-line-quantities"></a>Comprensión de las cantidades de línea de factura

Cuando abre una factura de proveedor desde un pedido de compra relacionado, el sistema crea líneas de factura a partir del pedido de compra. De forma predeterminada, el sistema obtiene las cantidades de la recepción de producto. Sin embargo, puede usar cualquiera de los comportamientos predeterminados siguientes:

- **Cantidad que se recibe ahora**: use esta opción para envíos parciales. El sistema establece como valor predeterminado del campo **Cantidad** la cantidad especificada en el campo **Recibir ahora** en el pedido de compra.
- **Cantidad pedida**: use esta opción para envíos completos. El sistema establece como valor predeterminado del campo **Cantidad** la cantidad especificada en el campo **Pedido** en el pedido de compra.
- **Cantidad registrada**: use esta opción si el artículo requiere el registro, según lo especificado en la página **Grupos de modelos de artículo**. El valor predeterminado del campo **Cantidad** es la cantidad física de actualización registrada.
- **Cantidad de la recepción de producto**: use esta opción si una recepción de producto se ha recibido ya para el pedido. El sistema usa el valor predeterminado del campo **Cantidad** de la cantidad total de recepciones de producto disponibles.
- **Cantidad y servicios registrados**: use esta opción si las cantidades se han registrado en los diarios de recepción para los artículos mantenidos en existencias o los artículos que no se encuentran en existencias. Esta opción también incluye servicios, independientemente de si se registran.

Si su entidad jurídica usa la conciliación de facturas, puede ver los resultados de la conciliación de cantidad en la columna **Cantidad de recepciones de producto para asignar**. También puede usar el botón **Detalles coincidentes** en la ficha **Revisar** del panel de acciones para ver los resultados de conciliación de cantidad.

## <a name="adding-a-line-that-wasnt-on-the-purchase-order"></a>Agregar una línea que no estaba en el pedido de compra

Puede agregar una línea que no estaba en el pedido de compra a la factura de proveedor. Debe seleccionar un número de artículo o una categoría de compras. Puede agregar cantidades, precios y los importes a la línea. La línea solo se incluirá en las directivas de conciliación para los totales de factura.

## <a name="submitting-a-vendor-invoice-for-review"></a>Envío de facturas de proveedor para su revisión

La organización puede usar flujos de trabajo para gestionar el proceso de revisión de facturas de proveedor. La revisión de flujo de trabajo puede ser necesaria para el encabezado de factura, la línea de factura, o ambos. Los controles de flujo de trabajo se aplican al encabezado o la línea, en función de dónde está el enfoque al seleccionar el control. En lugar del botón **Registrar**, verá un botón **Enviar** que puede usar para enviar la factura de proveedor a través del proceso de revisión.

### <a name="preventing-invoice-from-being-submitted-to-workflow"></a>Evitar que se envíe la factura al flujo de trabajo 

A continuación se indican varias maneras de impedir que se envíe una factura a un flujo de trabajo.

- **El total de la factura y el total registrado no coinciden.** La persona que envió la factura recibirá una alerta de que los totales no coinciden. La alerta ofrece la oportunidad de corregir los saldos antes de volver a enviar la factura al flujo de trabajo. Esta característica está disponible si el parámetro **Prohibir el envío al flujo de trabajo si el total de la factura y el total de la factura registrada no coinciden** de la página **Administración de características** está activado. 

- **La factura contiene cargos no asignados.** La persona que envió la factura recibirá una alerta que le comunicará que la factura contiene cargos no asignados para que pueda corregir la factura antes de volver a enviarla al flujo de trabajo. Esta característica está disponible si el parámetro **Prohibir el envío al flujo de trabajo si hay cargos no asignados en una factura de proveedor** de la página **Administración de características** está activado.

- **La factura contiene el mismo número de factura que otra factura registrada.** La persona que envió la factura recibirá una alerta que le comunicará que se ha encontrado una factura con un número duplicado para que pueda corregirla antes de volver a enviarla al flujo de trabajo. Esta alerta se mostrará cuando el parámetro **Comprobar el número de factura utilizado** de Proveedores esté establecido en **Rechazar duplicado**. Esta función está disponible si el parámetro **Prohibir el envío al flujo de trabajo si el número de factura ya existe en una factura registrada y su sistema no está configurado para aceptar números de factura duplicados** de la página **Administración de características** está activado.  

## <a name="matching-vendor-invoices-to-product-receipts"></a>Conciliación de facturas de proveedor a recepciones de producto

Puede especificar y guardar la información de facturas de proveedor y asignar líneas de factura a líneas de recepción de producto. También puede conciliar cantidades parciales para una línea.

Puede crear una factura de proveedor basada en los artículos de línea de recepción de producto recibidos hasta la fecha actual, incluso si no se han recibido todos los artículos de un pedido de compra en particular. Por ejemplo, esta opción se podría usar si un proveedor envía una factura al mes que cubre todas las entregas que envía a lo largo del mes. Cada recepción de producto representa una entrega parcial o completa de los artículos del pedido de compra.

Cuando una factura está en el flujo de trabajo, el aprobador puede actualizar las cantidades de la factura para que coincidan con el valor del campo **Cantidad de recepciones de producto para asignar**. Para ello, seleccione la característica **Actualizar las cantidades de factura para que coincidan con las recibidas de productos en el flujo de trabajo** en el espacio de trabajo **Administración de características** y seleccione **Habilitar**. Si un aprobador del proceso de flujo de trabajo ha eliminado todas las coincidencias de todas las recepciones de productos de la línea de factura, la línea de factura se eliminará. Cuando esta característica no está habilitada, las cantidades de las facturas no se actualizan para las facturas en el flujo de trabajo.

Al registrar la factura, la cantidad de **Recordatorio de factura** de cada artículo se actualiza con el total de las cantidades recibidas de las recepciones de producto seleccionadas. Si las cantidades tanto de **Recordatorio de factura** como de **Pendiente de entrega** para todos los artículos del pedido de compra son 0 (cero), el estado del pedido de compra cambia a **Facturado**. Si la cantidad de **Recordatorio de factura** no es 0, el estado del pedido de compra no cambia y se podrán entrar facturas adicionales para este.

En esta opción se supone que se ha registrado al menos una recepción de producto para el pedido de compra. La factura de proveedor se basa en estas recepciones de producto y refleja sus cantidades. La información financiera de la factura se basa en la información especificada al registrar la factura.

Para obtener más información, consulte [Registrar la factura de proveedor y cuadrarla con la cantidad recibida](../accounts-payable/tasks/record-vendor-invoice-match-against-received-quantity.md)

## <a name="configure-an-automated-task-for-vendor-invoice-workflow-to-post-the-vendor-invoice-using-a-batch-job"></a>Configurar una tarea automatizada para el flujo de trabajo de facturas proveedor con el fin de registrar la factura del proveedor mediante un trabajo por lotes

Puede agregar una tarea de registro automatizada al flujo de trabajo de facturas de proveedor para que las facturas se procesen en un lote. El registro de facturas en un lote permite que el proceso del flujo de trabajo continúe sin tener que esperar a que finalice el registro, lo que mejora el rendimiento global de todas las tareas enviadas al flujo de trabajo.

Para registrar una factura de proveedor en un lote, en la página **Administración de características**, active el parámetro **Registro de lotes de facturas de proveedores**. Los flujos de trabajo de factura de proveedor se configuran en **Proveedores > Configuración> Flujos de trabajo de proveedor**.

Puede ver la tarea **Registrar la factura de proveedor mediante un lote** en el editor de flujo de trabajo, con independencia de si el parámetro de característica **Registro de lote de facturas de proveedor** está habilitado. Cuando el parámetro de característica no está habilitado, una factura que contenga la tarea **Registrar la factura de proveedor mediante una tarea por lotes** no se procesará en el flujo de trabajo hasta que se habilite el parámetro. La tarea **Registrar la factura de proveedor mediante una tarea por lotes** no debe usarse en el mismo flujo de trabajo que la tarea automatiza **Registrar facturas de proveedor**. Además, la tarea **Registrar la factura del proveedor mediante un lote** debe ser el último elemento en la configuración del flujo de trabajo.

Para especificar el número de facturas que se deben incluir en el lote y el número de horas que se deben esperar antes de reprogramar un lote, vaya a **Proveedores > Configuración> Parámetros de proveedores > Factura > Flujo de trabajo de factura**. 

## <a name="working-with-multiple-invoices"></a>Trabajar con múltiples facturas

Puede trabajar con varias facturas a la vez y registrarlas todas a la vez. Si necesita crear varias facturas, use la página **Facturas de proveedor pendientes**. Si debe registrar e imprimir varias facturas de proveedor, utilice el diario de aprobación de facturas. Si usa el diario de aprobación de facturas, debe registrarse al menos una recepción de producto para el pedido de compra y debe registrarse una factura del pedido de compra en un registro de facturas. La información financiera de la factura proviene de la factura registrada en el registro.

## <a name="recovering-vendor-invoices-that-are-being-used"></a>Recuperar facturas de proveedor que se están usando

Mientras se está utilizando una factura de proveedor, esta no puede editarse por otro usuario. Sin embargo, el estado de una factura puede indicar a veces que la factura se está utilizando, aunque no se esté editando activamente. Por ejemplo, la aplicación puede haber detenido la respuesta mientras la factura estaba siendo editada o un usuario puede haber dejado de forma inadvertida la factura abierta en la aplicación.

Puede usar la página **Recuperar facturas de proveedor** para recuperar o para liberar las facturas de proveedores que se han llevan usándose más de cuatro horas, para que se puedan editar. Puede abrir esta página desde la navegación **Tarea periódica** o una sección en el espacio de trabajo **Entrada de la factura de proveedor**. Después de que se recupera una factura, ésta estará disponible para editarse en la página **Factura de proveedor**.

Puede obtener acceso a la página **Recuperar las facturas de proveedor** solo si tiene asignados derecho y privilegio de seguridad **Recuperar las facturas de proveedor en uso**. Además, el parámetro **Permitir recupear de la factura de proveedor** de la página **Parámetros de proveedores** se debe activar.

## <a name="resetting-the-workflow-status-for-vendor-invoices-from-unrecoverable-to-draft"></a>Restablecer el estado del flujo de trabajo para las facturas de proveedor desde irrecuperable a borrador

Una instancia de flujo de trabajo que se ha detenido debido a un error irrecuperable tendrá un estado flujo trabajo **Irrecuperable**. Cuando el estado de un flujo de trabajo de facturas de proveedor es **Irrecuperable**, puede restablecerlo a **Borrador** seleccionando **Recuperar**. Entonces podrá editar la factura de proveedor. Esta característica solo está disponible si el parámetro **Restablecer el estado del flujo de trabajo de facturas de proveedores de Irrecuperable a Borrador** de la página **Administración de características** está activado.

Puede usar la página **Historial del flujo de trabajo** para restablecer el estado del flujo de trabajo a **Borrador**. Puede abrir esta página **Factura de proveedor** o si navega a **Común > Consultas > Flujo de trabajo**. Para restablecer el estado del flujo de trabajo en **Borrador**, seleccione **Recuperar**. También puede restablecer el estado del flujo de trabajo a Borrador seleccionando la acción **Recuperar** en **Factura de proveedor** o **Facturas de proveedor pendientes**. Una vez que el estado de flujo de trabajo se establece a **Borrador**, quedará disponible para editar en la página **Factura de proveedor**.

## <a name="viewing-the-invoice-total-on-the-pending-vendor-invoices-page"></a>Ver el total de la factura en la página de Facturas de proveedores pendientes
Puede ver el total de la factura en la página **Facturas de proveedores pendientes** habilitando el parámetro **Mostrar el total de la factura en la lista de facturas de proveedores pendientes**, en la página **Parámetros de proveedores**. 



## <a name="additional-resources"></a>Recursos adicionales

- [Configurar directivas de factura de proveedor](../accounts-receivable/tasks/set-up-vendor-invoice-policies.md)
- [Datos clave en el sistema de proveedores mediante factura de proveedor](tasks/key-invoice-data-ap-system-vendor-invoice.md)
- [Introducir datos de factura en el sistema de proveedores mediante un diario de aprobación](tasks/key-invoice-data-into-ap-system-approval-journal.md)
- [Introducir datos de factura en el sistema de proveedores mediante un grupo de facturas](tasks/key-invoice-data-into-ap-system-invoice-pool.md)
- [Registrar una factura de proveedor en el diario de facturas](tasks/record-vendor-invoice-invoice-journal.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]