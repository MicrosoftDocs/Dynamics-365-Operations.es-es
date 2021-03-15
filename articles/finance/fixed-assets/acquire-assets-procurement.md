---
title: Adquisición de activos mediante compra
description: Este tema describe la manera de configurar la integración entre Activos fijos y Proveedores para crear automáticamente activos fijos a partir de pedidos de compra o facturas de proveedor, o registrar automáticamente transacciones de adquisición o transacciones de ajuste de adquisición de activos fijos.
author: ShylaThompson
manager: AnnBe
ms.date: 03/05/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetParameters
audience: Application User
ms.reviewer: roschlom
ms.custom: 3481
ms.assetid: d4e73a3f-633b-48b2-b8db-7a4a59a4d7ec
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 27f1bd8e8b001596054e6c427d87a610975c6a3b
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4978723"
---
# <a name="acquire-assets-through-procurement"></a>Adquisición de activos mediante compra

[!include [banner](../includes/banner.md)]

Este tema describe la manera de configurar la integración entre Activos fijos y Proveedores para crear automáticamente activos fijos a partir de pedidos de compra o facturas de proveedor, o registrar automáticamente transacciones de adquisición o transacciones de ajuste de adquisición de activos fijos. Una línea de compra creará un activo, independientemente de la cantidad en la línea de compra. Si necesita crear varios activos fijos, debe crear varias líneas de compra.

 Existen los métodos siguientes para integrar los activos fijos y los proveedores, y se debe utilizar el mismo método para todos los activos fijos:
-   Se crea manualmente un activo fijo, antes de agregar el número de activo fijo a la línea del pedido de compra o de la factura de proveedor. Automáticamente se registra una transacción de adquisición para el activo al registrar la factura de proveedor. Este es el método predeterminado.
-   Se crea manualmente un activo fijo, antes de agregar el número de activo fijo a la línea del pedido de compra o de la factura de proveedor. No se registra una transacción de adquisición para el activo al registrar la factura de proveedor.
-   Se crea un activo fijo automáticamente al registrar una recepción de producto o factura de proveedor que tiene la casilla Crear un activo fijo nuevo activada. Automáticamente se registra una transacción de adquisición para el activo al registrar la factura de proveedor.
-   Se crea un activo fijo automáticamente al registrar una recepción de producto o factura de proveedor que tiene la casilla Crear un activo fijo nuevo activada. No se registra una transacción de adquisición para el activo al registrar la factura de proveedor.

Seleccione uno de los dos primeros métodos si prefiere crear manualmente los activos fijos y asignar después el número de activo fijo al pedido de compra o factura de proveedor. Seleccione uno de los dos últimos métodos si prefiere un acercamiento más flexible: en ocasiones podrá crear activos fijos manualmente, y en ocasiones podrá crear automáticamente un nuevo activo fijo a partir de la información del activo fijo de los detalles de los elementos de líneas. 

Independientemente de sus preferencias respecto a la creación de activos fijos y del método que seleccione, deberá decidir también si las transacciones de adquisición se podrán registrar únicamente en Activos fijos, o se podrán registrar cuando registre una factura de proveedor. Algunas organizaciones prefieren que los usuarios creen manualmente las adquisiciones y las transacciones de adquisición en Activos fijos especificando manualmente las entradas o propuestas en el diario. 

En este tema se proporciona información detallada sobre cada método.

## <a name="methods-for-manually-creating-fixed-assets"></a>Métodos para la creación manual de activos fijos
Cuando se registra una factura de proveedor para la que se ha especificado un número de activo fijo en las líneas de los diarios, si se ha activado la casilla Permite la adquisición de activos desde Compras en la página Parámetros de activos fijos, la adquisición se registrará automáticamente y el estado del activo cambiará a Abierto. 

En caso de que no se pueda registrar la adquisición, podrá especificar manualmente la transacción de la adquisición en Activos fijos o utilizar una propuesta de adquisición del diario Activos fijos para crear varias transacciones de adquisición a la vez.

> [!NOTE]                                                                                                                              
> Si los activos fijos están configurados para restringir el registro de transacciones de adquisición para un grupo de usuarios específico, deberá ser un miembro de dicho grupo de usuarios para registrar las transacciones de adquisición a partir de las facturas.

## <a name="methods-for-automatically-creating-fixed-assets"></a> Métodos para la creación automática de activos fijos
Cuando se registra una recepción de producto que tiene activada la opción Crear un activo fijo nuevo para una línea, se creará un nuevo activo fijo con el estado No adquirido todavía. Posteriormente, cuando registre una factura de proveedor con un nuevo activo fijo, se registrará la transacción de adquisición para el nuevo activo y el estado del activo cambiará a Abierto, siempre y cuando los activos fijos se hayan configurado para permitir adquisiciones de activos desde Proveedores y usted sea un miembro de un grupo de usuarios autorizado para registrar transacciones de adquisiciones. 

Si no se ha activado la opción ¿Nuevo activo fijo? en la línea de compra cuando se registra la recepción de producto, pero se activa cuando se registra la factura de proveedor, se creará y adquirirá el nuevo activo fijo con el estado Abierto, siempre y cuando los activos fijos se hayan configurado para permitir la creación y adquisición. No se creará un activo adicional cuando se registra una factura de proveedor que ya se creó en el momento de registrarse la recepción de producto.

### <a name="capitalization-threshold"></a>Umbral de capitalización

Cuando se utiliza un método que permite la creación y adquisición automática de activos, puede configurar el sistema para verificar si el importe de compra del activo fijo cumple los requisitos del umbral de capitalización de depreciación de activos. En dicho caso, la opción de Depreciación deberá estar activada en los libros para el activo cuando se crea dicho activo desde Cuentas de proveedores. 

El umbral de capitalización es un importe de divisa en función del cual se determina si los activos están sujetos a depreciación en relación con el importe especificado. Por ejemplo, si adquiere un activo y el importe de compra es inferior al umbral de capitalización, el activo se anotará como activo no sujeto a depreciación; si el importe de compra equivale o es superior al importe de capitalización, el activo se anotará como activo sujeto a depreciación. 

Puede configurar el umbral de capitalización en la página Grupos de activos fijos.

## <a name="scenario"></a>Situación
En el siguiente escenario se presenta un ciclo completo de una integración de Activos fijos y Proveedores. Se muestra una configuración de ejemplo y se describe el uso de propuestas de adquisición. 

En este escenario, el sistema está configurado de la forma siguiente:

-   Los activos se crean automáticamente durante el registro de la recepción de producto o la factura de proveedor, pero los activos fijos están configurados para impedir que se registren transacciones de adquisición desde Proveedores.
-   Las cuentas se especifican en el campo Tipo de cuenta para los tipos de cuenta de recepción y de emisión de activos fijos en la página Grupos de artículos.
-   El umbral de capitalización especificado para el grupo de equipos informáticos (COMP) es 1.500.
-   Su tarea consistirá en especificar un pedido de compra del nuevo portátil que utilizará un empleado, registrar el pedido de compra, verificar que el empleado encargado del envío registra la recepción del producto y la factura de proveedor correspondientes y, por último, verificar que el responsable de contabilidad actualiza el activo del portátil con el estado Abierto.

Para ello, utilizará la página Pedido de compra para especificar los detalles del portátil, cuyo coste asciende a 1.600. A continuación, deberá activar la opción ¿Nuevo activo fijo? en la ficha desplegable Activos fijos de las líneas del pedido de compra, deberá seleccionar COMP como grupo de activos fijos y, por último, deberá guardar el pedido de compra. 

En el momento en que se reciba el portátil, el responsable del envío especificará y registrará una recepción de producto para registrar la recepción del portátil. El activo del portátil se creará con el estado No adquirido todavía. El importe supera el umbral de capitalización. Por tanto, la opción de Depreciación se activará en los libros para el activo del portátil. Se han llevado a cabo las siguientes transacciones.

| Descripción                               | Cuenta             | Débito    | Crédito   |
|-------------------------------------------|---------------------|----------|----------|
| Compra, compra de recepción de producto        | Recibos no facturados | 1.600,00 |          |
| Compra, contrapartida de compra de recepción de producto | Compras acumuladas   |          | 1.600,00 |

A continuación, deberá registrar la factura de proveedor del portátil. El estado del portátil no ha cambiado porque los activos fijos están configurados para impedir que se registren transacciones de adquisición de activos al registrarse una factura de proveedor. Se seleccionó la opción Crear un activo fijo nuevo cuando se registró la factura de proveedor. Por lo tanto, se usó la cuenta de recepción de activos fijos. No se ha utilizado la cuenta Emisión de activo fijo porque no se ha registrado ninguna adquisición; esta cuenta se utilizará después, cuando los responsables de contabilidad de su organización registren las transacciones de adquisición en Activos fijos mediante propuestas de adquisición. 

Se realizan las siguientes transacciones.

| Descripción                               | Cuenta             | Débito    | Crédito   |
|-------------------------------------------|---------------------|----------|----------|
| Compra, contrapartida de compra de recepción de producto | Compras acumuladas   | 1.600,00 |          |
| Saldo del proveedor                            | Proveedores    |          | 1.600,00 |
| Compra, recibo del activo fijo             | Gastos del equipo informático    | 1.600,00 |          |
| Compra, compra de recepción de producto        | Recibos no facturados |          | 1.600,00 |

Por último, el contable revisa todos los activos fijos con estado No adquirido todavía. Por lo tanto, se revisará el activo del nuevo portátil. El contable abre la página Propuesta de adquisición desde las líneas del diario Activos fijos y, a continuación, crea transacciones de adquisición de todos los activos para los que se ha registrado una factura pero que siguen teniendo el estado No adquirido todavía. Una vez registrado el diario, el estado del activo del portátil cambia a Abierto. Se adeudará la cuenta de adquisición del activo y se abonará la cuenta de emisión de activos fijos. 

A continuación se muestran algunas variaciones de este escenario:

-   Si los activos fijos están configurados para permitir que se registren transacciones de adquisición cuando se registran las facturas de proveedor, el responsable de contabilidad no necesitará utilizar las propuestas de adquisición de Activos fijos debido a que ya se habrá creado la transacción de adquisición. Asimismo, cuando se registre la factura de proveedor se actualizarán las distintas cuentas. En lugar del gasto de equipo informático, se adeuda la cuenta de inventario de recepción de activos fijos y se generan otras dos transacciones: la cuenta de adquisición del activo se adeuda y se abona la cuenta de inventario de emisión de activos fijos.
-   Si no se ha seleccionado la opción Crear un activo fijo nuevo cuando se registra la recepción del producto, no se creará ningún activo en ese momento. Si selecciona la opción Crear un activo fijo nuevo antes de registrar la factura de proveedor, el activo se creará con el estado No adquirido todavía o con el estado Abierto si registra también las transacciones de adquisición cuando se registran las facturas de proveedor.
-   Si el coste del portátil es 1.400 en lugar de 1.600, el umbral de capitalización no se ha superado. Por tanto, se crea el activo y se anula la selección de la opción Depreciación.
-   Si se utiliza un registro de facturas, deberá utilizar la página Diario de aprobación de facturas después de registrar el registro de la factura para recuperar el asiento, vincular el pedido de compra a la factura de proveedor, seleccionar la opción Crear un activo fijo nuevo y, por último, registrar la factura de proveedor. Si es miembro de un grupo de usuarios autorizado para crear transacciones de adquisición, se creará la adquisición y el activo con el estado Abierto.
-   Si solo se recibe una cantidad parcial, no se creará ninguna adquisición del activo para la primera factura de proveedor debido a las restricciones de grupos de usuarios. El único modo de poder registrar una adquisición para la segunda factura de proveedor que complete la cantidad solicitada es que ya se haya especificado una transacción de adquisición para la primera factura de proveedor y sea usted miembro de un grupo de usuarios con permiso para registrar adquisiciones.


Para obtener más información, consulte [Integración de activos fijos](fixed-asset-integration.md).





[!INCLUDE[footer-include](../../includes/footer-banner.md)]