---
title: Configuración de cuentas de proveedor
description: Este artículo describe los tipos de información que debe especificar al crear una nueva cuenta de proveedor.
author: GalynaFedorova
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: smmContactPerson, VendBankAccounts, VendTable, VendOnHoldUpdate
audience: Application User
ms.reviewer: kamaybac
ms.custom: 191053
ms.assetid: 06168199-7c54-40e9-a038-4eb274ca958d
ms.search.region: Global
ms.author: gfedorova
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d1ddf126305f39a35f61b9a98da1c6bce29372cf
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8875286"
---
# <a name="set-up-vendor-accounts"></a>Configuración de cuentas de proveedor

[!include [banner](../includes/banner.md)]

Este artículo describe los tipos de información que debe especificar al crear una nueva cuenta de proveedor.

Al crear una cuenta de proveedor, especifique información sobre el proveedor. Esta información se usa para especificar automáticamente datos en documentos y para realizar un seguimiento de la actividad que implica al proveedor. Por ejemplo, puede configurar la siguiente información para un proveedor:

-   Asigne un grupo de proveedores. Todos los proveedores deben asignarse a un grupo de proyectos. Los proveedores de un grupo de proveedores tienen parámetros que comparten. Por ejemplo, pueden tener las mismas condiciones de pago.
-   Configurar el proveedor para la importación de catálogos. Los proveedores pueden proporcionar un archivo que contenga el catálogo de sus artículos y servicios. Este archivo se puede cargar para sus trabajadores puedan realizar pedidos al proveedor.
-   Asigna el proveedor a categorías de compras.
-   Permita que un proveedor existente haga negocios con otra entidad jurídica de su organización.
-   Ponga a un proveedor en espera para los tipos específicos de transacciones.
-   Configure la información bancaria para el proveedor, de manera que pueda enviar pagos electrónicos.
-   Configure los impuestos, la entrega, la factura y la información de pago para el proveedor. De forma predeterminada, esta configuración se copian a los nuevos documentos que cree para el proveedor.
-   Configure las dimensiones financieras predeterminadas que se usan para registrar automáticamente transacciones con el proveedor en las cuentas financieras.

Para acelerar el proceso de creación de cuentas de proveedor, puede crear plantillas. Para crear una plantilla, en la página **Proveedor**, en el panel de acciones, haga clic en **Opciones** &gt; **Información de registro**. A continuación, haga clic en **Plantilla de cuentas de empresa**. Las plantillas de cuenta de empresa se comparten con otros usuarios.  

También puede crear una plantilla de usuario para su propio uso. No puede eliminar un proveedor que esté asociado a otros registros, como contactos o productos.

## <a name="vendor-account-numbers"></a>Números de cuenta de proveedor
El número de cuenta es un identificador único para un proveedor. Puede configurar números de cuenta para que se generen automáticamente cuando cree un proveedor. También puede configurar la secuencia numérica para que los números de cuenta se especifiquen manualmente. Por ejemplo, puede que desee usar el número de teléfono del proveedor como el identificador.

## <a name="vendor-organizations-and-individual-vendors"></a>Organizaciones de proveedores y proveedores individuales
Al crear una nueva cuenta de proveedor, debe seleccionar si el proveedor es una organización o una persona. Su selección afecta a la información que debe completar para el proveedor. Para una persona, esta información incluye el nombre, el apellido y el tratamiento. Para una organización, esta información incluye el número de organización y el número de empleados.

## <a name="addresses"></a>Direcciones
Para cada proveedor, puede definir varias direcciones y cada una de ellas se usa para un fin diferente. Por ejemplo, puede crear una dirección tenga un propósito de **Factura**. O bien, si va a pagar al proveedor mediante cheque, puede configurar una dirección que tenga el propósito **Remitir a**. Si debe especificar una dirección para usarla para transferencias de dinero a bancos extranjeros, el propósito será **SWIFT**.

## <a name="vendor-contacts"></a>Contactos de proveedor
Puede almacenar contactos para un proveedor. Estos contactos se pueden utilizar en documentos como pedidos de compra o solicitudes de presupuesto.  

Para agregar contactos para un proveedor, en la página **Todos los proveedores**, en la pestaña **Proveedor**, en el grupo **Configurar**, haga clic en **Contactos** &gt; **Agregar contactos**.  

Puede crear contactos de proveedor desde cero. Como alternativa, puede copiar detalles de otra persona que ya está registrada en Supply Chain Management y editar la información según sea necesario.  

**Nota:** Agregar un contacto para un proveedor no es lo mismo que agregar información de contacto para ese proveedor. Aunque es posible agregar información de contacto general para un proveedor, es posible que también tenga varias personas determinadas que sean contactos en esa empresa y que todas ellas tengan su propia información de contacto.  

No puede eliminar un registro de la persona de contacto si al contacto se hace referencia en un documento. En su lugar, puede desactivar el contacto.  

Puede agregar contactos de proveedor a sus contactos personales de Microsoft 365. Sin embargo, debe configurar primero la sincronización entre Supply Chain Management y Microsoft 365 en la sincronización de Microsoft Exchange Server y en el Asistente de configuración de Microsoft Outlook.

## <a name="vendors-in-different-legal-entities"></a>Proveedores en diferentes entidades jurídicas
Si un proveedor se registra solo para una entidad jurídica de su organización, y otras entidades jurídicas deben registrar el mismo proveedor, puede utilizar la página **Agregar proveedor a otra entidad jurídica** para configurar el proveedor para hacer negocios con otra entidad jurídica. Debe seleccionar un grupo de proveedores, una divisa y un estado de suspensión para el proveedor, en la entidad jurídica seleccionada.  

Si varias entidades jurídicas de la organización trabajan con el mismo proveedor, y cada una de ellas dispone de una cuenta de proveedor independiente para ese proveedor, puede combinar los identificadores de la parte para las cuentas del proveedor. De esta manera, se puede compartir la información como la dirección y el número de empleados, para que deba actualizarla solo en un lugar.  

Para combinar los id. de parte, siga estos pasos.

1.  En la página **Libreta de direcciones global**, seleccione los registros de la libreta de direcciones que representan al proveedor en cada entidad jurídica que se deben incluir en la asignación.
2.  En el panel de acciones, haga clic en **Combinar registros**.

## <a name="agreements"></a>Acuerdos
Al configurar una cuenta de proveedor, también es posible que desee registrar los acuerdos que tiene con el proveedor. Puede configurar los acuerdos de precios y descuentos mediante las acciones en el registro de proveedor. También puede configurar un acuerdo de compra en la página **Acuerdos de compra**.

## <a name="putting-a-vendor-on-hold"></a>Poner a un proveedor en espera
Puede colocar un proveedor en espera para diversos tipos de transacciones. Están disponibles las siguientes opciones:

-   **No**: el proveedor no tiene esperas.
-   **Factura**: no se puede registrar ninguna factura para el proveedor.
-   **Todos**: el proveedor está en espera para todos los tipos de transacción. Estos tipos de transacción incluyen solicitudes de compra, facturas y pagos.
-   **Pago**: no se pueden generar pagos para el proveedor.
-   **Pedido**: las solicitudes de compra no se pueden crear para el proveedor y las líneas de solicitud ya creadas antes de que el proveedor se pusiera en espera no se pueden convertir en un pedido de compra. Las líneas de solicitud para el proveedor se cancelarán si su directiva está establecida para crear pedidos de compra automáticamente.
-   **Nunca**: el proveedor nunca se pone en espera por inactividad.

Cuando coloca un proveedor en espera, también puede especificar un motivo y una fecha en que finalizará el estado en espera. Si no especifica una fecha final, el estado en espera del proveedor dura de forma indefinida.

Puede actualizar masivamente el estado en espera a **Todos** para los proveedores en función de los criterios seleccionados en la página **Desactivación del proveedor** y asignar un motivo por el que el proveedor está en espera.

Los siguientes criterios se usan para incluir proveedores que ha estado inactivos en un período, incluir o excluir proveedores que son empleados y excluir proveedores que están en un período de gracia antes de la próxima suspensión.

- En función del número de días que especifique en el campo **Período en actividad** dela página **Desactivación del proveedor** , la aplicación calcula la última fecha en la que el proveedor puede tener cualquier actividad que se considera inactiva. Es decir, la fecha actual menos el número de días que especifique. Si existe una o más facturas para el proveedor en la que la fecha es posterior a la última fecha calculada, el proveedor será excluido de la desactivación. Esto también se valida si el proveedor tiene pagos después de esa fecha, solicitudes de compra abiertas, pedidos de compra abiertos, solicitudes de presupuestos o respuestas.
- El número de días en el campo **Período de gracia antes de la próxima suspensión** se usa para calcular la última fecha de gracia. Es decir, la fecha actual menos los días que especifique. Esto solo se aplica a los proveedores que han sido desactivados previamente. En caso de una desactivación anterior, la aplicación verifica el historial de otras repeticiones de desactivación del proveedor y comprueba si la última desactivación se produjo antes de la última fecha de gracia. Si éste es el caso, el proveedor se incluirá en el proceso de desactivación.
- El parámetro **Incluir empleados** hace referencia a los proveedores que se vinculan a un empleado. Puede establecer si desea incluir a estos empleados.

Este proceso siempre excluirá a proveedores en el que el valor del campo **Retención de proveedor** es **Nunca**.

Los proveedores que aprueban las validaciones se ponen en espera, lo que establece el valor del campo **Retención de proveedor** a **Todos** y el **Motivo** por el que se ha seleccionado. Se crea un registro en el historial en espera para el proveedor.

## <a name="vendor-invoice-account"></a>Cuenta de facturas del proveedor
Si más de un proveedor tiene la misma dirección de facturación, o si se factura a un proveedor a través de un tercero, puede especificar una cuenta de factura en el registro de proveedor. La cuenta de facturación es la cuenta en la que se abona el importe de la factura cuando crea una factura del proveedor desde un pedido de compra. Si no especifica ninguna cuenta de facturación en el registro del proveedor, la cuenta del proveedor se utilizará como cuenta de facturación.

## <a name="vendor-bank-accounts"></a>Cuentas bancarias del proveedor
Si debe realizar pagos en una cuenta bancaria de proveedor, puede especificar información sobre el banco del proveedor y cuentas bancarias en la página **Cuentas bancarias del proveedor**. También puede escribir información acerca de la validación y los pagos de la cuenta bancaria. Por ejemplo, puede agregar validaciones de cuentas a las cuentas bancarias de proveedor. Estas validaciones de cuentas se pueden usar para comprobar la precisión de los datos de la cuenta, como los números de enrutamiento y los números de cuenta. Debe especificar una cuenta predeterminada para pagos al proveedor. Sin embargo, al realizar un pago real, puede cambiar esta cuenta a una de las demás cuentas del proveedor.

## <a name="ledger-accounts"></a>Cuentas contables
Puede especificar las cuentas predeterminadas que aparecen automáticamente en los diarios de facturas de proveedor para el proveedor especificado. Esta funcionalidad puede ser de utilidad si paga normalmente los mismos tipos de elementos o servicios de los mismos proveedores en el transcurso del tiempo. Al especificar una cuenta predeterminada, puede especificar de forma rápida y eficaz entradas de diario en el diario de facturas. Las cuentas predeterminadas que especifica no se usan para los pedidos de ventas o para facturas de proveedor que se especifican en la página **Factura de proveedor**.  

Puede seleccionar cuentas predeterminadas en la página **Configuración de cuenta predeterminada**, que puede abrir en la pestaña **Factura** del registro de proveedor. Las cuentas que selecciona aquí aparecen en la lista filtrada de cuentas para la cuenta de proveedor cuando especifica una entrada de diario. Puede establecer una de las cuentas como cuenta predeterminada.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]