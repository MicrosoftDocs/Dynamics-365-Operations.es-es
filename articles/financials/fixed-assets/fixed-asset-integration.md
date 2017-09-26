---
title: "Integración de activos fijos"
description: "Los activos fijos se pueden integrar con el Libro mayor, la Gestión de inventario, los Clientes y los Proveedores. También es posible configurar los activos fijos para que se integren con los pedidos de compra."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AssetTable
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 3501
ms.assetid: f0639053-d99c-432a-8ead-5c26e0d4eaec
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 305010c41aa87222c652f98e6aa2b097606052e8
ms.contentlocale: es-es
ms.lasthandoff: 05/25/2017


---

# <a name="fixed-assets-integration"></a>Integración de activos fijos

[!include[banner](../includes/banner.md)]


Los activos fijos se pueden integrar con el Libro mayor, la Gestión de inventario, los Clientes y los Proveedores. También es posible configurar los activos fijos para que se integren con los pedidos de compra.

<a name="general-ledger"></a>Contabilidad general
--------------

En Contabilidad general, el valor de todos los activos fijos se resume normalmente en varias cuentas principales necesarias para los informes financieros. No obstante, en la página **Activos fijos,** puede crear varios registros de activos fijos. Estos registros pueden incluir información como el precio de adquisición, la depreciación, y la evaluación. Cada vez que registre una transacción de un activo fijo, las cuentas principales adecuadas se actualizarán. Las cuentas principales de los activos fijos siempre muestran el valor actualizado de los activos fijos.

En la página **Perfiles de contabilización de activos fijos** se definen las cuentas principales en las que se han registrado las transacciones del libro de activos fijos. También especifica los tipos de transacciones de activos fijos que se registran en cada cuenta principal. Puede crear varias combinaciones de cuentas principales para activos fijos en función del nivel de detalle que desea para los activos fijos en la contabilidad general. Las cuentas principales se pueden basar en los tipos de transacciones, los libros y las cuentas principales.

## <a name="inventory-management"></a>Gestión del inventario
En el diario de inventario para los activos fijos, puede especificar la adquisición de activos fijos que la entidad jurídica ha producido o construido por sí misma. A continuación puede transferir los artículos de inventario a los activos fijos como adquisición o como parte de una adquisición. 

También puede adquirir los activos mediante los pedidos de compra. Cuando los pedidos de compra contienen artículos de inventario designados como activos fijos, la configuración de la opción **Permitir la adquisición de activos desde Compras** de la página **Parámetros de activos fijos** determina si se registra una adquisición para el activo fijo cuando se registra la factura. El efecto que la adquisición de activos fijos tiene en el inventario depende de la configuración de la entidad jurídica. 

Cuando un artículo de inventario se convierte en una adquisición de activos fijos, mediante el diario de inventario, un pedido de compra o una propuesta de adquisición, se crea una transacción de adquisición de libro de activo fijo. Si una adquisición de libro incluye un libro derivado, también se creará una transacción de adquisición de libro derivado. 

El registro de las normas establecidas en la página **Registro** de la Gestión de inventario controla la disminución en el inventario cuando se registra una adquisición. Sin embargo, no siempre disminuye el inventario cuando se registran las facturas relacionadas con los activos fijos. En algunos casos, podría ser necesario adquirir activos fijos para uso interno. Un ejemplo es un portátil que se compra para el departamento de ventas. Al trabajar con pedidos de compra, puede utilizar artículos configurados tanto para su reventa como para uso interno. 

Si utiliza cuentas de emisión y recepción específicas en los grupos de artículos para activos fijos, puede utilizar el mismo artículo de inventario tanto para compras internas, como para existencias para reventa. 

Los activos fijos que son de uso interno se configuran para que tengan un tipo de cuenta de **Recepción de activo fijo**. Este tipo de cuenta se utiliza para realizar un seguimiento de la recepción del activo fijo. Cuando registre una factura de proveedor, use la cuenta de recepción de activos fijos si alguna de las siguientes condiciones son verdaderas:

-   La línea de factura contiene un activo fijo existente para fines internos.
-   La casilla de verificación de **¿Nuevo activo fijo?** se ha activado para la línea de recepción del producto que se registra.
-   La casilla **Crear un activo fijo** nuevo está seleccionada para la línea de factura del proveedor.

Normalmente, esta cuenta es una cuenta de gastos. Puede configurar el tipo de cuenta **Recepción de activo fijo** para un grupo de artículos o para un artículo individual mediante la ficha de **Pedido de compra** de las páginas de **Grupo de artículos** o **Registro**.

Del mismo modo, los activos fijos que son de uso interno se pueden configurar de modo que tengan un tipo de cuenta de **Emisión de activo fijo**. Este tipo de cuenta se usa para realizar un seguimiento de la emisión del activo fijo al destinatario. La cuenta de emisión del activo fijo se utiliza como cuenta de contrapartida de la cuenta de débito del activo fijo cuando se adquiere un activo mediante un pedido de compra. La adquisición del activo se puede registrar cuando se registra una factura de proveedor o cuando se registra la adquisición del activo en el diario Activos fijos, la mayoría de las veces mediante una propuesta de adquisición. Puede configurar el tipo de cuenta **Emisión de activo fijo** para un grupo de artículos o para un artículo individual mediante la ficha **Inventario** de las páginas **Grupo de artículos** o **Registro de artículos**. 

Por último, las cuentas principales que se usan para registrar están determinadas por las opciones para la integración contable especificadas para el grupo de modelos de artículo. Además, las cuentas principales que se usan varían, en función de si un activo está asignado a la línea de pedido de compra. Las cuentas se derivan del perfil de registro de cada grupo de artículos. 
**Nota:** Si existe una reserva de inventario cuando las recepciones de productos se registran, no puede asignar un activo fijo ni crear un activo fijo desde la línea. 

Las cuentas en las que se registran las transacciones de activos fijos dependen de dos factores: si los activos los compra o los construye la entidad jurídica y del tipo de transacción del activo. 

El tipo de transacción conecta la transacción del inventario al perfil de registro en los activos fijos. Debido a que el perfil de registro en los activos fijos define las cuentas que se van a actualizar, la selección de un tipo de transacción de activos fijos es también, de forma indirecta, la selección de las cuentas principales en las que se registrará la transacción. Para los activos fijos construidos y adquiridos, el tipo de transacción será normalmente o **Adquisición** o **Ajuste de adquisición**.

## <a name="accounts-receivable"></a>Clientes
La integración de activos fijos con clientes usa los perfiles de contabilización que se configuran en activos fijos. Se activan estos perfiles de registro cuando se seleccionan un activo fijo, un libro y un tipo de transacción de activo fijo para una factura de cliente antes de que se registre la factura de cliente. Dado que los activos fijos no son parte de la gestión del inventario, debe utilizar la página **Factura de servicios** cuando venda un activo fijo. 

Si el libro incluye un libro derivado, se creará una transacción de libro derivado al registrar la factura de cliente.

## <a name="accounts-payable"></a>Proveedores
Normalmente, los activos fijos los adquieren los proveedores externos. Puede utilizar la página **Parámetros de activos fijos** para especificar si las adquisiciones de activos deberán registrarse siempre que se registren las facturas de proveedores, o si podrán registrarse solo a partir de los Activos fijos. Si habilita que las adquisiciones de activos se registren a partir de los proveedores, las cuentas de activos fijos se actualizarán siempre que se registre una factura de proveedor de una adquisición de activo fijo. 

Si el sistema se configura para que se registre una adquisición de activos cuando se registra una factura, la transacción se registra de acuerdo con los perfiles de registro que se configuran en los activos fijos para los distintos tipos de transacción de activos fijos. El registro está controlado por el activo fijo, el libro y el tipo de transacción de activos fijos que se seleccionan en la página **Pedido de compra** antes de registrar la factura de proveedor. 

Si el libro incluye un libro derivado, se creará una transacción de libro derivado al registrar la factura de proveedor.

La integración se activa en la ficha **Activos fijos** en la ficha desplegable **Detalles de línea** de la página **Pedido de compra**. Puede enviar un pedido de compra para un activo fijo al proveedor. Sin embargo, se actualizarán los activos fijos y las cuentas principales solo cuando se registra la factura de proveedor después de que se reciba el activo fijo. Dado que los pedidos de compra pueden contener solo los artículos de inventario, el efecto que la adquisición de activos fijos tiene en el inventario depende de la configuración de la entidad jurídica.

## <a name="project-management-and-accounting"></a>Gestión de proyectos y contabilidad
Puede asociar un proyecto con un activo afectado por el proyecto. También puede asociar cada fase, tarea o subproyecto a un activo diferente. Un activo se puede asociar a cada registro del proyecto. Puede crear la asociación al introducir un número de activo fijo en el campo de número de **Activo fijo** de la página **Proyectos**. El tipo de proyecto debe ser **Interno** o **Proyecto de coste**. 

También puede utilizar la página **Proyectos** para ver los detalles de los activos asociados a los proyectos. Para ver el registro de activos fijos, haga clic en el vínculo de activos en la ficha desplegable de **Configuración** para abrir la página **Activos fijos**. A continuación haga clic en **Proyectos** &gt; **Todos los proyectos** para ver los proyectos asociados al activo fijo. 

Normalmente, los activos fijos se asocian a proyectos cuando dichos proyectos están relacionados con trabajos, operaciones de mantenimiento o mejoras realizadas en el activo. Una vez completado el proyecto, un ajuste de revalorización para el activo no se creará automáticamente. Por tanto, si se requiere un ajuste de revalorización, deberá crearlo manualmente. 

Para eliminar una asociación entre un proyecto y un activo, anule el campo **Número de activo fijo** de la página **Proyectos**. 

También puede designar un activo fijo que va a crear o fabricar como parte de un proyecto estimado. Al final de un proyecto estimado, puede registrar automáticamente una transacción de adquisición de activos fijos.

Para obtener más información, consulte [Adquisición de activos mediante compra](acquire-assets-procurement.md)




