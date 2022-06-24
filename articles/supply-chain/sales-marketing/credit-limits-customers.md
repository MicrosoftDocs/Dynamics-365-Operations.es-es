---
title: Límites de crédito para clientes
description: Este artículo proporciona información general sobre el funcionamiento de los límites de crédito en Dynamics 365 Supply Chain Management.
author: Henrikan
ms.date: 09/15/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustParameters
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f7f15c0f15302c271fac7199b21b7bcd3dcfe88a
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8903880"
---
# <a name="credit-limits-for-customers"></a>Límites de crédito para clientes

[!include [banner](../includes/banner.md)]

La configuración de un límite de crédito permite especificar el importe máximo de crédito que se puede extender a los clientes. Si se especifica un límite de crédito, se comprobará automáticamente cuando un usuario intente actualizar un documento. Si se supera el límite de crédito, se mostrará un mensaje al usuario. En este artículo se proporciona información general sobre cómo funcionan los límites de crédito, y respuestas a las preguntas siguientes:

-   ¿De qué documentos y procesos puedo comprobar los límites de crédito?

-   ¿Dónde configuro la forma en que se calcula el crédito restante del cliente?

-   ¿Dónde se utiliza la información acerca del crédito restante de un cliente?

-   ¿Dónde especifico si la identificación es necesaria para extender el crédito a un cliente y el importe del límite de crédito que requiere identificación?

-   ¿Dónde especifico si se debe mostrar una advertencia o un error si se supera el límite de crédito?

-   ¿Cómo especifico el límite de crédito para un cliente específico?

-   ¿Cómo compruebo los límites de crédito manualmente en pedidos de ventas?

**¿De qué documentos y procesos puedo comprobar los límites de crédito?**

Use el formulario **Parámetros de clientes** para especificar en qué documentos quiere comprobar los límites de crédito. Debe ser miembro del rol de seguridad Administrador del sistema (-SYSADMIN-) para realizar cambios en este formulario. Puede comprobar los límites de crédito de los siguientes documentos y procesos:

-   Facturas de pedidos de ventas, al registrar facturas

-   Albaranes de pedidos de ventas, al actualizar albaranes

-   Pedidos de ventas, cuando agrega líneas al formulario **Pedido de ventas**

-   Pedidos de ventas, al crearlos mediante un servicio

-   Facturas de texto sin formato, al registrar las facturas

Los límites de crédito se comprueban automáticamente si se define alguna de las opciones siguientes:

-   En el formulario **Parámetros de clientes**, el campo **Tipo de límite de crédito** se configura en cualquier valor que no sea **Ninguno**. Los límites de crédito se comprueban para todos los clientes.

-   En el formulario **Parámetros de clientes**, el campo **Tipo de límite de crédito** se establece en **Ninguno**, pero se selecciona **Límite de crédito obligatorio** para un cliente en el formulario **Clientes**. Los límites de crédito se comprueban solo para clientes específicos.

Para comprobar los límites de crédito de los siguientes documentos, debe especificar opciones adicionales.

|    Documento                                    |    Configuración adicional                                                                                                             |
|------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------|
|    Factura de servicios                         |    En el formulario de parámetros de clientes, en el área Clasificación crediticia, establezca la comprobación de límite de crédito en Factura de servicios.     |
|    Pedido de ventas (introducido manualmente)            |    En el formulario de parámetros de clientes, en el área Clasificación crediticia, establezca la comprobación de límite de crédito en Pedido de ventas.           |
|    Pedido de ventas (recibido electrónicamente)     |    En el formulario de parámetros de clientes, en el área AIF, establezca la comprobación de límite de crédito en Pedido de ventas.                     |

**¿Dónde configuro la forma en que se calcula el crédito restante de un cliente?**

Puede configurar Dynamics 365 para calcular el crédito restante de un cliente de una de las siguientes formas:

-   Compare el límite de crédito con el saldo del cliente.

-   Compare el límite de crédito con los importes del saldo y el albarán del cliente.

-   Compare el límite de crédito con el saldo del cliente y toda la actividad de transacciones abiertas. Se incluyen los importes de albaranes y pedidos de ventas.

Use el formulario **Parámetros de clientes** para especificar la información que se usará para comparar. Debe ser miembro del rol de seguridad Administrador del sistema (-SYSADMIN-) para realizar cambios en este formulario. En el campo **Tipo de límite de crédito**, seleccione si desea realizar comprobaciones de límite de crédito y qué información de transacciones desea incluir al comprobar el límite de crédito. Elija entre las siguientes opciones:

-   **Ninguno**: no se comprueban los límites de crédito. Puede anular esta opción para un cliente específico seleccionando la casilla **Límite de crédito obligatorio** en el formulario **Clientes**. Si lo hace, el límite de crédito se comprueba comparándolo con el saldo del cliente.

-   **Saldo**: el límite de crédito se comprueba con respecto al saldo del cliente.

-   **Saldo + albarán o recepción de producto**: el límite de crédito se comprueba con respecto al saldo del cliente y las entregas.

-   **Saldo+Todo**: el límite de crédito se comprueba con respecto al saldo del cliente, las entregas y los pedidos abiertos.

**¿Dónde se utiliza la información acerca del crédito restante de un cliente?**

La información acerca del saldo y el importe de crédito restante de un cliente se calcula y se almacena al crear una instantánea de vencimientos, y se muestra en el formulario **Cobros**. Es posible que los importes que se muestran en el formulario **Cobros** no incluyan toda la actividad de las transacciones hasta que se cree una nueva instantánea de vencimientos. Para obtener más información, consulte [Cobros y crédito en clientes](/dynamicsax-2012/appuser-itpro/collections-and-credit-in-accounts-receivable).

En función de los documentos seleccionados, la información sobre el saldo y el importe de crédito restante de un cliente se calcula cuando los pedidos de ventas, los albaranes y las facturas del cliente se actualizan. Si el importe del documento con el que está trabajando hará que se supere el límite de crédito, aparecerá un mensaje.

**¿Dónde especifico si la identificación es necesaria para extender el crédito a un cliente y límite de crédito que requiere identificación?**

Use el formulario **Parámetros de clientes** para especificar si debe solicitarse la identificación y el importe del límite de crédito que requiere la identificación.
Debe ser miembro del rol de seguridad Administrador del sistema (-SYSADMIN-) para realizar cambios en este formulario.

|    Campo                                    |    Descripción                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
|---------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|    Requerir identificación con crédito     |    Permite seleccionar el tipo de identificación que se debe especificar para los clientes a los que la entidad jurídica amplía el crédito. La opción que seleccione en este campo determinará cuándo y qué tipo de información se solicitará en los campos de identificación gubernamental del formulario Clientes: No: no se requiere ninguna identificación gubernamental, independientemente del límite de crédito del cliente.     Sí: se requiere un número de licencia u otra identificación gubernamental si el límite de crédito del cliente es igual o mayor que cero.     Límite mínimo: se requiere un número de licencia u otra identificación gubernamental si el límite de crédito del cliente es igual o mayor que el límite especificado en el campo Límite de este formulario.        |
|    Límite                                    |    Especificar el límite de crédito a partir del cual se requiere un número de licencia u otra identificación gubernamental para los clientes.    Por ejemplo, escriba 2000 para solicitar que se especifique un número de identificación, como el número del permiso de conducir, para los clientes que tengan un límite de crédito igual o mayor que 2.000.    Este campo está disponible si se ha seleccionado Límite mínimo en el campo Requerir identificación con crédito.                                                                                                                                                                                                                                                                                                                                                                                                                                         |

**¿Dónde especifico si se debe mostrar una advertencia o un error si se supera el límite de crédito?**

Use el formulario **Parámetros de clientes** para especificar si se debe mostrar una advertencia o un error si se supera el límite de crédito. La advertencia o el error se muestran cuando un usuario introduce o registra información, o bien se incluye en un registro si los documentos se procesan mediante un servicio electrónico. Debe ser miembro del rol de seguridad Administrador del sistema (-SYSADMIN-) para realizar cambios en este formulario.

|    Campo                                                               |    Descripción                                                                                                                                                                                                                                                                                                                                                                                        |
|------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|    Mensaje que aparece al exceder el límite de crédito (en el área de clasificación crediticia)     |    Seleccione cómo se muestran a los usuarios los mensajes sobre un exceso del límite de crédito. Elija entre las siguientes opciones:        Error: se mostrará un mensaje de error. Esta acción suele detener la operación actual y el conflicto debe resolverse para poder continuar con el proceso.     Advertencia: se muestra un mensaje de advertencia pero se puede continuar con el proceso.                     |
|    Mensaje que aparece al exceder el límite de crédito (en el área AIF)               |    Seleccione cómo se entregan en un registro los mensajes sobre un exceso del límite de crédito. Seleccione alguna de las siguientes opciones: Error: aparece un mensaje de error en el formulario Excepciones y el documento no se procesa hasta que este se resuelve.     Aviso: aparece un mensaje de advertencia en el formulario Excepciones, pero el proceso puede continuar.        |

**¿Cómo especifico el importe del límite de crédito para un cliente específico?**

Use el formulario **Clientes** para especificar el importe del límite de crédito para un cliente específico. Debe ser miembro de un rol de seguridad que tenga el arancel Mantener el maestro de cliente (CustCustomersMaintain) asignado al realizar cambios en este formulario.

1.  Haga clic en **Clientes** \> **Común** \> **Clientes** \> **Todos los clientes**. Haga doble clic en una cuenta de cliente.

2.  En el formulario **Clientes**, en el panel de acciones, haga clic en **Editar**.

3.  Especifique el importe en la divisa de la transacción en el campo **Límite de crédito**. Este valor debe ser mayor que cero (0) y se usará como el importe del límite de crédito.

4.  Si es necesario, especifique el número de licencia u otra identificación gubernamental en el campo **Identificación gubernamental**.

> [!NOTE]
> En el formulario **Parámetros de clientes**, normalmente se selecciona un tipo de límite de crédito. Sin embargo, si el tipo de límite de crédito está definido en **Ninguno**, también debe activar la casilla **Límite de crédito obligatorio** en el formulario **Clientes** para poder comprobar el límite de crédito del cliente comparado con su saldo. Para obtener más información acerca de los tipos de límite de crédito, consulte “¿De qué documentos y procesos puedo comprobar los límites de crédito?” en este artículo. 

**¿Cómo compruebo manualmente los límites de crédito en pedidos de ventas?**

En ocasiones, es posible que deba comprobar manualmente el límite de crédito de un cliente. Por ejemplo, puede comprobar manualmente el límite de crédito de un cliente antes de comenzar a introducir un pedido de ventas. Puede usar el formulario **Pedido de ventas** para comprobar manualmente los límites de crédito. Debe ser miembro de un rol de seguridad que tenga el arancel Mantener el pedido de ventas (SalesOrderMaintain) asignado al realizar cambios en este formulario.

1.  Haga clic en **Ventas y marketing** \> **Común** \> **Pedidos de ventas** \> **Todos los pedidos de ventas**. Haga doble clic en un pedido de ventas.

2.  En el formulario **Pedido de ventas** del panel de acciones en la ficha **Administrar**, seleccione **Comprobar el límite de crédito**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]